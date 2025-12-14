Platform: Aws

A 3-tier application architecture separates an application into three logical layers: 

* Web tier/Presentation Tier (user interface)
* Application/Business Logic Tier (processing)
* Data Tier (database)

Infra:

* A Vpc has created
* Inside Vpc 6 subnets will created in 2 Az's for high availability.
* Subnets - 2 Public (Presentation tier), 2 Private (Application tier), 2 Private (Data tier)
* In one of the private subnet, multi Az Rds mysql will setup
* In another Az's private subnet standby Rds mysql will be setup
* Application will be deployed through ASG in 2 diffrent Az's private subnets
* In 2 rest of the public subnet a nginx web server along with to host React JS application
* A bastion host will be setup outside ASG to control instances in private subnets
* An application LB will be setup for scalability and performance
* Route 53 - Manage domain name resolution and ensure secure communication 
* ACM - to estabilish secure https connections setup aws certificate manager for ssl certificates
* Cloud Front - This certificate will be integrate with CF to encrpt data and content delivery for end users
* Cloud Watch - application logs will be managed by cloud watch, alarm will trigger auto scaling group 

<img width="1915" height="1060" alt="image" src="https://github.com/user-attachments/assets/2b075b03-f8e8-43f8-8b0a-4bf6924cf55f" />




