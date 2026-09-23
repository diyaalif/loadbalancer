# Output & Verification
When navigating to the ALB DNS Endpoint (loadcloud-1878240458.us-east-1.elb.amazonaws.com), traffic is successfully load balanced between both targets:

Request 1: Renders WEBSITE1 (Introduction to AWS)

Request 2 (Refresh): Renders WEBSITE2 (Introduction to AZURE)
## Project Structure
├── README.md
├── website1/
│   └── index.html       # Landing page for Instance 1 (AWS Topic)
└── website2/
    └── index.html       # Landing page for Instance 2 (Azure Topic)
