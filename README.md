# isatest

This lampstack is created from wordpress cloudformation template. 
Due to time constraints i had to keep it simple.
This design is not fully secure. Note: Port 80 redirection to 443 is not configured. Also there are no WAF policies applied (can use Cloudflare free edition).

Suggestion/s to consider for cost effiency:
- Solution could have leveraged EBS and run php app in container with Aurora DB (Primary Replica) in Muli-AZ.
- The same could be done using ECS and or EKS services. 

Things that are done Manual:

- VPC, Subnets
- IAM Role for S3 bucket (Cloudformation Template).
- RDS DB Groups. 
- RDS Security Group for myaurora/postgress

Tools to consider for Design and auto code generation:
 - Cloudforma
 - Cloudformation Designer
 
