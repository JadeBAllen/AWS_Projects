# Highly Available Web App (AWS)

A web app running on two servers in private subnets across two Availability Zones, behind an Application Load Balancer. Auto Scaling replaces failed servers automatically.

## What I built!
<img width="822" height="360" alt="VPC Plan" src="https://github.com/user-attachments/assets/7ba20078-a04e-4031-bca9-61c2a06cedf5" />

- VPC with public and private subnets in two AZs, plus a NAT gateway
- Security groups: servers only accept traffic from the load balancer
  
<img width="1285" height="337" alt="Web Firewall inbound rules" src="https://github.com/user-attachments/assets/d11103a0-590d-495c-9245-09a002cee43b" />

- Launch template with a startup script that installs nginx
- Application Load Balancer and an Auto Scaling group (2–4 servers)
- Server access through Session Manager (no SSH)

## Proof it works
<img width="693" height="122" alt="NGinX working" src="https://github.com/user-attachments/assets/7a7d0103-fb38-48a7-8743-2025c19dd2a1" />

## Problem I solved
One target was unhealthy in us-east-1b. The Auto Scaling group had launched it into a public subnet with no public IP, so it couldn't download nginx.
<img width="1153" height="286" alt="Target group issue" src="https://github.com/user-attachments/assets/5f75e74e-1dad-411b-b8a3-9425a3221e3f" />


<img width="1288" height="222" alt="Registered target issue" src="https://github.com/user-attachments/assets/530aebc2-4ea7-47c4-a211-8b5482cfe0fb" />

I switched the group to the private subnet and replaced the instance.
<img width="962" height="138" alt="Private subnet correction" src="https://github.com/user-attachments/assets/038638ba-377d-4369-a788-a6a151c268d3" />

After the unhealthy instance was replaced, another took its spot with a mere refresh of the page.
<img width="717" height="209" alt="2 Healthy targets" src="https://github.com/user-attachments/assets/3e5544c1-6c57-47ec-9e73-0da2af48f09e" />

## Cleanup
Deleted the Auto Scaling group, load balancer, target group, NAT gateway, Elastic IP and VPC.
