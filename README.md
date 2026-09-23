# AWS High-Availability Application Load Balancer Architecture

This repository demonstrates the end-to-end configuration and verification of a highly available, fault-tolerant **AWS Application Load Balancer (ALB)** setup. The load balancer receives HTTP traffic on Port 80 and distributes requests across multiple Amazon EC2 backend instances host in different Availability Zones within an Amazon VPC.

---

## Architecture Overview

```text
                           +----------------------------------+
                           |       Client / Web Browser       |
                           +----------------------------------+
                                            |
                                            | HTTP (Port 80)
                                            v
                           +----------------------------------+
                           |  AWS Application Load Balancer   |
                           |           'loadcloud'            |
                           |   (AZs: us-east-1a, 1b, 1c)      |
                           +----------------------------------+
                                            |
                        +-------------------+-------------------+
                        |                                       |
                        v                                       v
         +-----------------------------+         +-----------------------------+
         | EC2 Instance 1              |         | EC2 Instance 2              |
         | Name: loadbalancer1         |         | Name: loadbalancer2         |
         | Subnet: us-east-1f          |         | Subnet: us-east-1f          |
         | Target Group: 'lb'          |         | Target Group: 'lb'          |
         | Content: WEBSITE1 (AWS)     |         | Content: WEBSITE2 (AZURE)   |
         +-----------------------------+         +-----------------------------+
```
[Configuration & Environment Specifications](Configuration.md)
[Deployment Steps](Deploymentsteps.md)
[Output & Verification](Output&verify.md)



