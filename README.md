# Lift-and-Shift Application Workload on AWS

## Project Overview

This project demonstrates a **Lift-and-Shift migration of an application workload to AWS**.

The existing application architecture is moved to AWS with minimal changes to the application itself. The project uses AWS components for networking, load balancing, scaling, DNS, storage, and supporting backend services.

## Architecture

![Lift-and-Shift AWS Architecture](lift%20and%20shift%20application%20workload.png)





## Application Flow

```text
Users
   |
   v
Route 53 / DNS
   |
   v
Application Load Balancer (ALB)
   |
   v
Target Group
   |
   v
Tomcat Application Instances
   |
   +-------------------+-------------------+
   |                   |                   |
   v                   v                   v
 MySQL             Memcached           RabbitMQ

                S3
        Object / File Storage
```

## AWS Services and Components

- Amazon EC2
- Apache Tomcat
- Application Load Balancer
- Target Group
- Auto Scaling Group
- Amazon VPC
- Security Groups
- Amazon Route 53
- Amazon S3
- MySQL
- RabbitMQ
- Memcached

## How the Architecture Works

1. Users access the application through a DNS name.
2. Route 53 handles DNS resolution.
3. The request reaches the Application Load Balancer.
4. The ALB forwards traffic to healthy application servers through the Target Group.
5. Tomcat instances run the application.
6. The application communicates with MySQL for database operations.
7. Memcached provides a caching layer for frequently accessed data.
8. RabbitMQ provides message-queue functionality between components.
9. S3 provides object/file storage.
10. Security Groups and private networking control communication between layers.
11. Auto Scaling manages the application instances according to configured capacity and scaling requirements.

## Key Learning Outcomes

- AWS multi-tier application architecture
- EC2-based application deployment
- Application Load Balancer and Target Groups
- Auto Scaling
- VPC and Security Groups
- Route 53 DNS
- S3 object storage
- Database, caching and messaging layers
- Lift-and-Shift cloud migration

## Project Status

**Completed and tested on AWS.**

The AWS resources were deleted after completion to avoid unnecessary ongoing cloud charges. Therefore, this repository is a **documentation and portfolio record of the completed project**, not a currently live deployment.

## Security Note

No AWS access keys, secret keys, passwords, `.pem` files, or other credentials are included in this repository.
