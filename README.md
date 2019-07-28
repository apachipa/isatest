# isatest

This lampstack is created from wordpress cloudformation template. 
Due to time constraints i had to keep it simple.
This design is not fully secure. Note: Port 80 redirection to 443 is not configured. Also there are no WAF policies applied (can use Cloudflare free edition).

Environment Information:
- VPC with 3 subnets (one subnet in each Zone) in Sydney Region.
- 3 Amazon Linux Instances with Apache, PHP and MySQL ( RDS) installed and configured.
- ELB with listener post and Target host group configured.
- Autoscaling group to scale up to 3 instances (this is test environment and kept maximum as 3 with 3 deployed in 3 AZ sydney region)
- Route 53 with A record (testcode.experimentbox.net) pointing to ELB. 
- S3 bucket which holds cloudformation template with IAM Role set on it.
- Required Security Groups between External connectivity to Web Servers, Web Servers to MYSQL DB (RDS) 

Things that are done Manual:

- VPC, Subnets
- IAM Role for S3 bucket (Cloudformation Template).
- RDS DB Groups. 
- RDS Security Group for MySQL.

Suggestion/s to consider for cost effiency:
- Solution could have leveraged EBS and run php app in container with Aurora DB (Primary Replica) in Muli-AZ.
- The same could be done using ECS and or EKS services or Lambda functions. 

Tools to consider for Design and auto code generation:
 - Cloudformer
 - Cloudformation Designer

There are two templates, One for Wordpress which is in .json format and the other is simple php app which is in yml. 
