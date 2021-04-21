# Cloud Computing Basics

Six Major Advantages:

- Less need for upfront capital, you pay for what you use
- Share the costs with other customers, and benefit from that scale
- No need to guess capacity
- Launch resources in minutes
- Maintaining and running data centers is a thing of the past.
- Go global in minutes

"Let's See Nelly Loofah Massive Goats"

# Setup

1) Navigate to new account page and fill in information (AWS account name can be changed later on)
2) If you so choose, navigate to IAM and modify the sign-in link to something a bit more user-friendly
3) (optional) Set up billing alerts as needed in account preferences and CloudWatch
4) Enable MFA for the account
5) Setup individual users in IAM: Mgmt console should be enough for non-programmers or services that don't use the CLI, SDK, etc. 

# Organizations 

- This feature allows you to manage billing, access, compliance, security, and share resources amongst your accounts. 

# Terms

**Amazon Connect**: A virtual call center. Records calls, manages queues, route callers.

**ALB**: Application Load Balancer

**ASG**: Auto-Scaling Groups

**CAPEX**: Capital Expenditure

**CFN**: Cloud Formation, which is Infrastrcuture as code, automates provisioning of AWS services

**Cloud Trail**: logs API calls between AWS Services

**EBS**: Elastic Block Storage

**EC2**: Elastic Cloud Compute

**ECR**: Elastic Container Respository

**ECS**: Elastic Container Service, think Docker as a Service

**EFS**: Elastic File Storage

**EKS**: Kubernetes service

**Elastic Beanstalk**: Like Heroku, for deploying web applications

**EMR**: Elastic MapReduce

**Fargate**: Microservices where you don't think about the infrastructure

**Internet Gateway**: enables access to the internet for your VPC

**MQ**: Amazon ActiveMQ

**MSK**: Managed Kafka Service

**NACLS**: Network Access Control Lists, acts as a firewall at the subnet level

**NLB**: Network Load Balancer

**OPEX**: Operational Expenditure

**Route Tables**: determines where network traffic from your subnets are directed.

**Security Groups**: Acts as a firewall at the instance level.

**SNS**: Simple Notification Service

**SQS**: Simple Queue Service

**SSM**: Simple Systems Manager

**Storage Gateway**: Enables on-premises applications to use AWS cloud storage.

**Subnets**: a logical partition of an IP Network into multiple, smaller network segments

  - Public subnets are generally used for placing resources which are accessible on the internet
  - Private subnets are used when you need resources to be more secured and only accessible through tightly filtered traffic into the subnet

**SWF**: Simple Workflow Service

**TAM**: Technical Account Manager

**TCO**: Total Cost of Ownership are the factors that go into deciding whether to go On-Premises or Cloud or some mix in-between for your particular org.

**VPC**: Virtual Private Cloud, a logically isolated section of the AWS Cloud where you can launch AWS resources

**WAF**: Web Application Firewall









