# isatest

This lampstack is created from wordpress cloudformation template. 
Due to time constraints i had to keep it simple and had to secure. 
Although this design is not fully secure.

This to consider for cost effiency:
- Solution could have leveraged EBS and run php app in container with Aurora DB (Primary Replica) in Muli-AZ.
- The same could be done using ECS and or EKS services. 

Things that are done Manual:

- VPC, Subnets
- RDS DB Groups. 
