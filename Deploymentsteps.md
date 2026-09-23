# Deployment Steps
Step 1: Provision EC2 Instances
Launch two Amazon Linux 2023 EC2 instances in your VPC and ensure the attached Security Group allows inbound traffic on HTTP (Port 80) and SSH (Port 22).

Step 2: Configure Target Group & Register Instances
Navigate to EC2 Console -> Target Groups.

Create target group lb selecting target type as Instances and protocol HTTP:80.

Register instances loadbalancer1 and loadbalancer2 on port 80.

Step 3: Create the Application Load Balancer
Navigate to EC2 Console -> Load Balancers and create an Application Load Balancer named loadcloud.

Map networking across multi-AZ subnets (us-east-1a, us-east-1b, us-east-1c).

Set the listener to HTTP:80 with a default routing rule to forward traffic to Target Group lb.

Step 4: Web Server Setup
On each instance, install Apache HTTPD and serve unique landing pages to verify round-robin traffic routing.

Server 1 Setup (loadbalancer1):
```bash
sudo dnf update -y
sudo dnf install httpd -y
sudo systemctl enable --now httpd
## Deploy WEBSITE1 HTML code to /var/www/html/index.html
```
Server 2 Setup (loadbalancer2):
```bash
sudo dnf update -y
sudo dnf install httpd -y
sudo systemctl enable --now httpd
# Deploy WEBSITE2 HTML code to /var/www/html/index.html
```
