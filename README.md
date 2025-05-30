# ACF-MST-Notes


## Chapter 1:
- **Cloud computing definition:** On-demand delivery of computer power, database, storage, applications, and other IT resources via the internet with pay as you go pricing 
- **Stop thinking of your infrastructure as hardware, think and use as software**

### Hardware:
Require space etc ,long procurement hours, Need guess theoretical max peaks

### Cloud computing:
- **IaaS:** highest level of flexibility and management control over your IT resources
- **PaaS:** reduce the need for you to manage the underlying infrastructure
- **SaaS:** provided as a complete product, application is web-based, do not have to think abt how service is maintained or how underlying infrastructure is managed

- **Cloud deployment models:** cloud, hybrid, on-premise(private cloud) IMPORTANT

### Advantages of cloud:
1. Massive economies of scale
2. Trade capital expense for variable expense
3. Stop guess capacity
4. Increase speed and agility
5. Stop spending money on running and maintaining data center (hardware)
6. Go global in minutes

- **EC2:** complete control over your AWS computing resources
- **Elastic Beanstalk:** You want a service that deploys, manages, and scales your web applications for you
- **Outposts:** You want to run AWS infrastructure in your on-premises data center

### 3 Ways to interact:
- **AWS Management console:** provides a rich graphical interface to a majority of the features
- **CMD line interface (AWS CLI):** provides a suite of utilities that can be launched from a command script
- **Software Dev kits (SDKs):** provides packages that enable accessing AWS in a variety of popular programming languages.

- **AWS Cloud Adoption Framework (AWS CAF):** provides guidance and best practices to help organizations  
6 perspectives: Business, People, Governance, Platform, Security, Operations

## Chapter 2:
- **Compute:** per hr
- **Storage:** per GB
- **Data transfer:** outbound charged per GB, inbound no charge (unless not same region)

### How do you pay?
- Pay for what you use
- Pay less when you reserve (AURI, NURI, PURI)
- Pay less when use more and AWS grows

### AWS Free tier:
Help new customer to help them to get started using services with no charge
1. VPC
2. Elastic Beanstalk
3. IAM

### Total cost of ownership:
Financial estimate to help identify direct and indirect cost of system

### Why?
Compare cost of running entire infrastructure env or specific workload and to budget and build business case

### AWS pricing calc:
To estimate monthly cost and find opportunities to reduce cost, explore price points, decide instance types and contract to meet needs

### Hard benefits:
- Reduce spending, hardware and operational cost (money)

### Soft benefits:
- Increased productivity
- Improved customer satisfaction
- More agile business processes

### AWS Organization:
Management service that enables you to consolidate multiple AWS accounts into an organization

### Main benefits:
- Centrally manage access
- Controlled access to AWS services
- Automated AWS account creation and management
- Consolidated billing

### Security:
- IAM
- SCPs

### Accessing AWS Organization:
- Management Console
- AWS CLI
- SDKs
- HTTPs Query (API)

### Billing and cost management:
- AWS budgets
- AWS cost and usage report
- AWS cost explorer

### AWS support:
- Experiment
- Production use
- Business-critical use
- **AWS Trusted Advisor:** Online resource that checks for opportunity to reduce expenses and increase productivity

### Support plans (in order of price):
- Basic 
- Development
- Business
- Enterprise: Critical case, response time - 15 mins or less

## Chapter 3:
### AWS regions:
- Data replication, Communication using backbone
- Consist of two or more Availability zone
- Regions are fault isolated

### Selecting a region:
- Data governance, legal requirements
- Proximity to customers (latency)
- Services available within the region
- Cost that vary by Region

### Availability zones:
- Full redundancy (Backup generator so-called) and connection to network
- Fault isolated
- Made out of discrete data centers

### AWS data centers:
- Designed for security
- Redundant power, networking and connectivity

### Points of presence:
- **Edge location:** High speed delivery
- **Regional edge caches**

### AWS infrastructure features:
- Elasticity and scalability
- High Fault-tolerance
- High availability: Minimized downtime

### Storage service category:
- **S3:** websites, mobile apps, backup and restore, archive
- **EBS:** EC2 for both throughput(efficiency) and transaction intensive workloads. Relational and non-relational databases
- **EFS:** For file storage
- **S3 Glacier:** For data archiving and long-term backup (storage)

### AWS compute:
- **EC2 IS IMPORTANT**
- **Auto Scaling:** Add or remove EC2 instances automatically
- **Containerization**
- **Lambda:** serverless computing
- **ECS**
- **ECR**
- **EKS**
- **Fargate**

### Database:
- **RDS:** Resizable capacity, automate admin tasks
- **Aurora:** (almost same as RDS just faster)
- **Redshift:** For data analytics
- **DynamoDB:** (almost same as RDS and Aurora but a lot faster)

### Content delivery:
- **VPC**
- **CloudFront:** Content delivery network (CDN)
- **Route 53:** DNS web service

### Security service category:
- **Cognito:** Add user signup, sign-in and access control to web
- **Artifact:** Library for compliance report
- **AWS key management service:** create and manage keys
- **AWS Shield:** Distributed Denial of Service (DDoS)

### Managing Governance:
- **Management Console**
- **Config:** Helps track resource
- **CloudWatch:** monitor resources and applications
- **Auto scaling:** allow you to scale resources
- **Trusted Advisor:** helps optimize performance and security
- **CLI:** Automate task
- **CloudTrials:** tracks user activity and API usage

## Chapter 4:
### Shared responsibility:
Responsibility of:
- **AWS:** Operates, manages and controls component, physical security of the facilities, protect infrastructure including hardware and software(OS)
- **Customer:** Encryption of data at rest and data in transit, configure for security, security credentials and logins are managed safely, configuration of local OS (Updates and security patches)

### IaaS:
- **EC2, EBS, VPC:** Customer more flexibility, responsible for managing more aspects of security

### PaaS:
- **Lambda, RDS, Elastic beanstalk**

### Service characteristics:
Customers do not need to manage the infrastructure that supports that service

### AWS IAM:
To manage access to AWS  
Define fine-grained access rights
- Who can access
- Which resources to access
- How to access

### IAM: Essential components
- **User:** person or application
- **Group:** collection of IAM users
- **Policy:** level of access, which resources can be accessed
- **Role:** Grant set of permission, temporary access

### Types of access:
- **Programmatic access:** using access key ID and Secret access key
- **Management console access:** using 12 digit ID, username and password

### MFA:
Increase security

### Authorization:
Process of determining what permissions a user, service or application should be granted  
Determine which resources and operations  
All permissions are implicitly denied by default  
Principle of least privilege 

### IAM policies:
- **Identity-based**
  - User, group or role
  - Managed policies - AWS created
  - Incline policies - Own self created
- **Resource-based**
  - Attached to resource (no human)
  - Policies are in JSON format

### IAM groups:
User can belong to multiple groups  
Groups cannot be nested

### IAM roles:
Role provides temporary security credentials

### Securing new AWS account:
- Stop using root account asap
- Enable MFA
- AWS CloudTrial
- Enable a billing report

## Chapter 5:
### CIDR calculate IMPORTANT:
- **/32:** first 32 bits fixed 1 IP address (useful if want to set up firewall rule and give access to a specific host
- **/24:** first 24 bits fixed 256 IP addresses
- **/16:** first 16 bits fixed 2 power 16 (16 bits flexible)
- **/0:** every bit flexible

### OSI model (open systems interconnection):
STUDY SLIDE 15 FOR MODULE 5

### VPC:
- Allow to select IP address range
- Creation to subnets
- Configuration of route table and network gateways
- Can only belong to one AWS region

### Subnet:
Range of IP addresses that divide a VPC  
Belong to a single availability zone  
Classified as public or private

### IP Addressing:
- Cannot change address range
- Largest /16
- Smallest /28
- Five reserved IP addresses

### Public address:
Manual assignment thru Elastic IP

### Elastic IP address:
Can be allocated and remapped anytime  
Virtual network interface that can be attached or detached from an instance  
Attributes follow it when it is reattached to another instance

### Route tables:
- Destination
- Target  
Every subnet must be associated with a route table

### Internet gateway:
Function: allows communication between instances in your VPC and the internet.

### NAT:
Enables instances in a private subnet to connect to the internet, prevents the internet from initiating
