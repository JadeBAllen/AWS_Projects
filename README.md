# AWS_Projects
A collection of AWS projects as a burgeoning Cloud Security Architect
Hands-on AWS projects covering secure networking, access control, monitoring and recovery. Each folder has the setup, screenshots and a short write-up.

Project	Skills
01 – Highly available web app	VPC, load balancer, Auto Scaling
02 – Access control and encryption	IAM, ABAC, KMS, S3 policies
03 – Audit logging and PII discovery	CloudTrail, Config, Macie, Athena
04 – Monitoring and disaster recovery	CloudWatch, AWS Backup

Projects
#	Project	What it shows	Status
## 01--DONE
[Highly available web application](https://github.com/JadeBAllen/AWS_Projects/tree/Highly-Available-Web-Services)	VPC across two Availability Zones, public/private subnets, NAT gateway, Application Load Balancer, Auto Scaling, self-healing test

## 02	
Least-privilege access and encryption	Tag-based access control (ABAC), permission boundaries, KMS customer-managed keys, HTTPS-only bucket policy, expiring share links

## 03
Audit logging and sensitive-data discovery	CloudTrail with data events, Object Lock, AWS Config compliance rules, Macie PII detection, email alerts, Athena audit queries

## 04	
Monitoring, backup and disaster recovery	CloudWatch alarms and dashboards, AWS Backup with tag-based protection, tested restore with measured recovery time

## 05	
Infrastructure as code with Terraform	Project 01 rebuilt in Terraform: plan/apply/destroy, state, drift detection

## 06	
Secure AI training-data pipeline	Lake Formation column-level access, SageMaker network isolation, VPC-only data access, dataset lineage
