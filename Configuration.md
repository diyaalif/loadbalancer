# Configuration & Environment Specifications

1. Target Group Details
Name: lb

Target Type: Instances (IPv4)

Protocol & Port: HTTP:80

Registered Targets:

loadbalancer1 (i-0d998269c07130d0c) — Zone: us-east-1f

loadbalancer2 (i-02e3af0d991fdf3e1) — Zone: us-east-1f

VPC: vpc-062e75279363ad7f0

2. Application Load Balancer Details
Name: loadcloud

Scheme: Internet-facing

IP Address Type: IPv4

Availability Zones: us-east-1a, us-east-1b, us-east-1c

Listeners: HTTP:80 (Forwards 100% traffic to Target Group lb)

Endpoint DNS: loadcloud-1878240458.us-east-1.elb.amazonaws.com
