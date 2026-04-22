# AWS SAA Complete Practice Questions


## Question 1
**Question:**  
A gaming company is implementing a shared storage solution for a gaming application that is hosted in an on-premises data center. The company needs the ability to use Lustre clients to access data. The solution must be fully managed. Which of the following options is correct?

**Options:**
- Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to the file share.
- Create an AWS Storage Gateway file gateway. Create a file share that uses the required client protocol. Connect the application server to the file share.
- Create an Amazon Elastic File System (Amazon EFS) file system, and configure it to support Lustre. Attach the file system to the origin server. Connect the application server to the file system.
- Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

**Correct Answer:**  
Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

**Explanation:**  
Amazon FSx for Lustre is a fully managed high-performance file system that supports Lustre clients and provides extremely high throughput and low latency.

---

## Question 2
**Question:**  
An e-commerce company runs an e-commerce application on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. The application stores transaction data in a MySQL database hosted on a large EC2 instance. The database performance degrades quickly as load increases, and the application handles more read requests than write transactions. The company wants automatic scaling for unpredictable read workloads with high availability.

**Options:**
- Use Amazon RDS with a Single-AZ deployment and add reader instances.
- Use Amazon Redshift with a single node.
- Use Amazon ElastiCache for Memcached with EC2 Spot Instances.
- Use Amazon Aurora with a Multi-AZ deployment and Aurora Auto Scaling with Aurora Replicas.

**Correct Answer:**  
Use Amazon Aurora with a Multi-AZ deployment. Configure Aurora Auto Scaling with Aurora Replicas.

**Explanation:**  
Aurora supports read replicas and auto scaling to handle unpredictable read workloads while providing high availability with Multi-AZ.

---

## Question 3
**Question:**  
Which IAM policy condition key should be used to check whether a request was sent using SSL?

**Options:**
- AWS:agent  
- AWS:sourceIP  
- AWS:secureTransport  
- AWS:secureIP  

**Correct Answer:**  
AWS:secureTransport

**Explanation:**  
The AWS:SecureTransport condition key evaluates whether a request was sent using HTTPS.

---

## Question 4
**Question:**  
If a company wants to build its own payment application, it should take advantage of the richness and flexibility of _____________.

**Options:**
- Payoneer Payment Services  
- EBay Payment service  
- PayPal Payment service  
- Amazon AWS FPS  

**Correct Answer:**  
Amazon AWS FPS

**Explanation:**  
Amazon FPS (Flexible Payments Service) enables developers to integrate payment functionality into applications.

---

## Question 5
**Question:**  
A solutions architect is designing a VPC with public and private subnets across three Availability Zones. The private subnets require internet access for software updates. What should be implemented?

**Options:**
- Create an egress-only internet gateway.
- Create three NAT instances.
- Create a second internet gateway.
- Create three NAT gateways, one in each public subnet.

**Correct Answer:**  
Create three NAT gateways, one for each public subnet in each AZ, and update private route tables to use them.

**Explanation:**  
NAT gateways allow instances in private subnets to access the internet without allowing inbound connections.

---

## Question 6
**Question:**  
A company uses Amazon DynamoDB to store customer data. The solution must meet an RPO of 15 minutes and an RTO of 1 hour in case of corruption.

**Options:**
- Configure DynamoDB point-in-time recovery.
- Schedule EBS snapshots every 15 minutes.
- Configure DynamoDB global tables.
- Export DynamoDB to S3 Glacier daily.

**Correct Answer:**  
Configure DynamoDB point-in-time recovery (PITR).

**Explanation:**  
PITR allows restoring a DynamoDB table to any point within the past 35 days, meeting both RPO and RTO requirements.

---

## Question 7
**Question:**  
An IT company needs to rotate credentials for Amazon RDS MySQL databases across multiple AWS Regions during maintenance activities.

**Options:**
- Store credentials in S3 and rotate using Lambda.
- Encrypt credentials using KMS and store in DynamoDB.
- Store credentials in AWS Secrets Manager with multi-region replication and scheduled rotation.
- Store credentials in Systems Manager Parameter Store.

**Correct Answer:**  
Store credentials in AWS Secrets Manager with multi-Region replication and scheduled rotation.

**Explanation:**  
Secrets Manager provides automatic credential rotation and secure replication across regions.

---

## Question 8
**Question:**  
A business‑critical web application runs on EC2 behind an ALB. The database is Amazon Aurora PostgreSQL deployed in a single AZ. The company wants high availability with minimal downtime and data loss.

**Options:**
- Use multiple Regions with Route 53 health checks.
- Configure Auto Scaling across multiple AZs and set database to Multi‑AZ with RDS Proxy.
- Use one AZ with hourly snapshots.
- Write data to S3 and process with Lambda.

**Correct Answer:**  
Configure the Auto Scaling group to use multiple AZs. Configure the database as Multi‑AZ and use RDS Proxy.

**Explanation:**  
Multi‑AZ deployment and RDS Proxy increase resilience, availability, and connection stability.

---

## Question 9
**Question:**  
A company requires all data stored in the cloud to be encrypted at rest using encryption keys stored on‑premises.

**Options:**
- SSE‑KMS  
- SSE‑S3  
- SSE‑C  
- Client-side encryption  

**Correct Answers:**  
- Server-side encryption with customer-provided keys (SSE‑C)  
- Client-side encryption  

**Explanation:**  
Both approaches allow customers to control encryption keys outside AWS.

---

## Question 10
**Question:**  
A media company runs an online voting system where hundreds of thousands of votes are submitted within minutes. EC2 instances write votes to an Amazon RDS database, which cannot keep up with the requests.

**Options:**
- Re-provision larger database instances during voting.
- Send votes to an Amazon SQS queue and process with worker instances.
- Convert database to Multi‑AZ and write to both instances.
- Migrate to Lambda with API Gateway.

**Correct Answer:**  
Configure the front-end application to send votes to an Amazon SQS queue and use worker instances to process them.

**Explanation:**  
SQS decouples the application from the database and allows votes to be processed at a manageable rate.


## Question 11
**Question:**  
A company is deploying a public web application behind an Application Load Balancer (ALB). The application must be encrypted at the edge using an SSL/TLS certificate issued by an external certificate authority (CA). The certificate must be rotated each year before expiration. Which option is correct?

**Options:**
- Use AWS Certificate Manager (ACM) to issue a certificate and apply it to the ALB with managed renewal.
- Use AWS Certificate Manager (ACM) to issue a certificate and import the key material.
- Use AWS Certificate Manager Private Certificate Authority to issue the certificate.
- Import the external certificate into AWS Certificate Manager and apply it to the ALB.

**Correct Answer:**  
Use AWS Certificate Manager (ACM) to import an SSL/TLS certificate, apply it to the ALB, and use Amazon EventBridge notifications for expiration reminders so it can be rotated manually.

**Explanation:**  
Certificates issued by external CAs must be imported into ACM. ACM cannot automatically renew imported certificates, so notifications must be used to trigger manual rotation.

---

## Question 12
**Question:**  
After configuring VPC peering between VPC X and VPC Y, VPC Y has both an Internet Gateway (IGW) and a Direct Connect connection to the corporate network. Can instances in VPC X access the corporate network via Direct Connect and the internet via the IGW in VPC Y?

**Options:**
- Yes, VPC peering routes traffic between VPCs.
- VPC peering does not support edge-to-edge routing.
- Instances in VPC X can access the corporate office but not the internet.
- Instances in VPC X can access the internet but not the corporate office.

**Correct Answer:**  
VPC peering does not support edge-to-edge routing.

**Explanation:**  
VPC peering does not allow routing from one VPC to another VPC’s gateway (IGW, NAT, or VPN). Transit Gateway would be required for such routing.

---

## Question 13
**Question:**  
An ecommerce application sends new order information to an Amazon API Gateway REST API. The company needs to ensure that orders are processed in the exact order they are received.

**Options:**
- Send messages to an Amazon SQS FIFO queue and process them with AWS Lambda.
- Publish messages to an Amazon SNS topic and process them with Lambda.
- Block requests using an API Gateway authorizer.
- Send messages to an SQS standard queue.

**Correct Answer:**  
Send messages to an Amazon SQS FIFO queue and process them with AWS Lambda.

**Explanation:**  
SQS FIFO queues guarantee message ordering and exactly-once processing.

---

## Question 14
**Question:**  
An automated transcription service processes uploaded audio files using EC2 workers and generates text files. Both files must be stored together in durable storage, but storage capacity requirements are unknown. Which option is the most scalable and cost-effective?

**Options:**
- Multiple Amazon EBS volumes with snapshots
- Amazon Glacier Vault
- Amazon S3 bucket
- Instance store volumes

**Correct Answer:**  
A single Amazon S3 bucket.

**Explanation:**  
Amazon S3 provides highly scalable, durable object storage and can store both files efficiently.

---

## Question 15
**Question:**  
Multiple web servers frequently access a shared Amazon RDS MySQL Multi‑AZ database. The company needs secure access and frequent credential rotation.

**Options:**
- Store encrypted credentials on the web server file system using AWS KMS.
- Store credentials in AWS Secrets Manager.
- Store credentials in AWS Systems Manager OpsCenter.
- Store credentials in an encrypted S3 bucket.

**Correct Answer:**  
Store the database credentials in AWS Secrets Manager and grant the web servers permission to access them.

**Explanation:**  
Secrets Manager securely stores and automatically rotates credentials.

---

## Question 16
**Question:**  
A company must ensure that Amazon S3 buckets have not been modified without authorization. What should the solutions architect implement?

**Options:**
- AWS Config rules
- AWS Trusted Advisor checks
- Amazon Inspector assessments
- S3 server access logging with EventBridge

**Correct Answer:**  
Enable AWS Config with appropriate rules.

**Explanation:**  
AWS Config tracks configuration changes and can detect unauthorized modifications to S3 bucket configurations.

---

## Question 17
**Question:**  
A company has over 5 TB of data stored on on‑premises Windows file servers. The company is migrating workloads to AWS and needs minimal latency access from both on‑premises and cloud environments without changing file access patterns.

**Options:**
- Deploy Amazon S3 File Gateway
- Deploy Amazon FSx for Windows File Server with FSx File Gateway
- Deploy Amazon FSx for Windows File Server and migrate data to it
- Deploy S3 File Gateway and store files in S3

**Correct Answer:**  
Deploy Amazon FSx for Windows File Server and migrate the data to it.

**Explanation:**  
FSx for Windows File Server provides native SMB support and minimal operational overhead.

---

## Question 18
**Question:**  
A company needs private connectivity from its VPC to a service hosted in another company’s VPC. Connectivity must be private and restricted to the target service.

**Options:**
- Use a virtual private gateway
- Use AWS PrivateLink with a VPC endpoint
- Use a NAT gateway
- Use VPC peering

**Correct Answer:**  
Use AWS PrivateLink by connecting to a VPC endpoint created by the service provider.

**Explanation:**  
AWS PrivateLink provides private connectivity between VPCs without exposing traffic to the public internet.

---

## Question 19
**Question:**  
A company uses AWS Organizations with multiple accounts. An S3 bucket in the management account contains project reports. Access must be limited to users from accounts within the organization with minimal operational overhead.

**Options:**
- Monitor organization events with CloudTrail
- Use the aws:PrincipalOrgID condition key
- Use aws:PrincipalOrgPaths
- Use aws:PrincipalTag

**Correct Answer:**  
Add the **aws:PrincipalOrgID** condition key to the S3 bucket policy.

**Explanation:**  
This condition key allows access to any principal that belongs to the specified AWS Organization.

---

## Question 20
**Question:**  
A two‑tier web application runs on EC2 instances in public subnets with a SQL Server database on EC2 in a private subnet. Which security group rules should be configured? (Select TWO)

**Options:**
- Allow inbound ports 443 and 1433 from web tier to database tier.
- Allow inbound port 1433 from web tier security group to database tier.
- Allow outbound 443 from web tier to 0.0.0.0/0.
- Allow outbound ports 443 and 1433 from database tier to web tier.
- Allow inbound port 443 from 0.0.0.0/0 to web tier.

**Correct Answers:**
- Allow inbound port **1433** from the web tier security group to the database tier.
- Allow inbound port **443** from **0.0.0.0/0** to the web tier.

**Explanation:**  
The web tier must accept HTTPS traffic from the internet, and the database tier should only accept SQL traffic from the web tier.


## Question 21
**Question:**  
An HTTP application runs behind a Network Load Balancer (NLB). The NLB target group contains EC2 instances in an Auto Scaling group. The company notices that HTTP errors are not detected and unhealthy instances require manual restarts. The company wants to improve availability without writing custom code.

**Options:**
- Enable HTTP health checks on the NLB.
- Use a CloudWatch alarm on UnhealthyHostCount.
- Replace the NLB with an Application Load Balancer and enable HTTP health checks.
- Add a cron job to restart the application when errors occur.

**Correct Answer:**  
Replace the NLB with an Application Load Balancer and enable HTTP health checks.

**Explanation:**  
Network Load Balancers only perform TCP health checks. Application Load Balancers support HTTP/HTTPS health checks and can detect application‑level failures.

---

## Question 22
**Question:**  
A company uses AWS Organizations with separate AWS accounts for business units. The root email recipient missed an important notification. Future notifications must not be missed and should be limited to administrators.

**Options:**
- Forward root emails to all users in the organization.
- Use the same root email for all accounts.
- Configure root email addresses as distribution lists for administrators and set alternate contacts.
- Send all notifications to a single administrator.

**Correct Answer:**  
Configure root user email addresses as distribution lists for administrators and configure AWS account alternate contacts.

---

## Question 23
**Question:**  
A company uses multiple AWS CloudFormation templates to build different application architectures. What determines the cost of using CloudFormation?

**Options:**
- $0.20 per template per month
- Build time of the template
- $0.101 per template per month
- Cost of the underlying AWS resources created

**Correct Answer:**  
CloudFormation has no additional cost. You only pay for the underlying resources created.

---

## Question 24
**Question:**  
A company must retain application logs for 10 years. Logs from the past month are frequently accessed, while older logs are rarely accessed. The application generates more than 10 TB of logs per month. What is the most cost‑effective storage solution?

**Options:**
- Store logs in Amazon S3 and transition them to S3 Glacier Deep Archive after 1 month.
- Store logs in CloudWatch Logs and use AWS Backup to archive them.
- Store logs in Amazon S3 and use AWS Backup to move them to Glacier.
- Store logs in CloudWatch Logs and use lifecycle policies.

**Correct Answer:**  
Store logs in Amazon S3 and use lifecycle policies to move logs older than 1 month to S3 Glacier Deep Archive.

---

## Question 25
**Question:**  
A company collects 500 GB of sensor data daily from sites around the world. Each site has a high‑speed internet connection. The company wants to upload all data quickly into a single Amazon S3 bucket with minimal operational complexity.

**Options:**
- Upload to regional S3 buckets and replicate them.
- Use AWS Snowball Edge devices.
- Upload data to EC2 instances and snapshot to S3.
- Enable S3 Transfer Acceleration and use multipart uploads.

**Correct Answer:**  
Enable S3 Transfer Acceleration on the destination bucket and upload using multipart uploads.

**Explanation:**  
S3 Transfer Acceleration uses AWS edge locations to speed up global uploads to a single S3 bucket.

---

## Question 26
**Question:**  
A company wants to migrate a monolithic application to AWS while keeping most of the code. The company plans to break the application into smaller services managed by different teams and requires high scalability with minimal operational overhead.

**Options:**
- Host the application on Amazon ECS with an Application Load Balancer.
- Use AWS Lambda with API Gateway.
- Use EC2 instances in an Auto Scaling group.

**Correct Answer:**  
Host the application on Amazon ECS with an Application Load Balancer.

**Explanation:**  
Amazon ECS allows containerized services to be deployed and scaled easily while reducing infrastructure management overhead.

---

## Question 27
**Question:**  
Which Amazon S3 storage classes provide **99.999999999% (11 nines) durability**?

**Options:**
- Standard, Standard‑IA, One Zone‑IA
- Standard, Glacier, Reduced Redundancy
- Standard‑IA, One Zone‑IA, Reduced Redundancy
- Reduced Redundancy, Standard, One Zone‑IA

**Correct Answer:**  
Standard, Standard‑IA, One Zone‑IA.

---

## Question 28
**Question:**  
How can software running on an Amazon EC2 instance determine its public and private IP addresses?

**Options:**
- Query instance metadata
- Query CloudWatch metrics
- Use ifconfig or ipconfig
- Query instance user data

**Correct Answer:**  
Query the local instance metadata.

**Explanation:**  
EC2 instance metadata provides runtime information about the instance including public and private IP addresses.

---

## Question 29
**Question:**  
A company needs to design a highly available website that can withstand large‑scale DDoS attacks from thousands of IP addresses. Which two actions should be taken?

**Options:**
- Use Spot instances in Auto Scaling
- Add attacker IPs to NACLs using Lambda
- Use Amazon CloudFront
- Use Amazon GuardDuty
- Use AWS Shield Advanced

**Correct Answers:**
- Use Amazon CloudFront.
- Use AWS Shield Advanced.

**Explanation:**  
CloudFront distributes traffic globally and helps absorb attacks. AWS Shield Advanced provides advanced DDoS protection.

---

## Question 30
**Question:**  
An application running on an EC2 instance in a VPC needs to access an Amazon S3 bucket without internet connectivity.

**Options:**
- Create a gateway VPC endpoint for S3
- Stream logs through CloudWatch
- Use API Gateway with PrivateLink
- Use an instance profile

**Correct Answer:**  
Create a gateway VPC endpoint for Amazon S3.

**Explanation:**  
A gateway VPC endpoint allows private connectivity between a VPC and S3 without using an Internet Gateway or NAT gateway.


## Question 31
**Question:**  
A company needs to store confidential data in Amazon S3. The data must be encrypted at rest, encryption key usage must be logged for auditing, and keys must rotate every year. Which option should be used?

**Options:**
- Server‑side encryption with AWS KMS (SSE‑KMS) with manual rotation  
- Server‑side encryption with Amazon S3 managed keys (SSE‑S3)  
- Server‑side encryption with AWS KMS (SSE‑KMS) with automatic rotation  
- Server‑side encryption with customer‑provided keys (SSE‑C)

**Correct Answer:**  
Server‑side encryption with AWS KMS (SSE‑KMS) with automatic rotation.

**Explanation:**  
AWS KMS logs key usage through CloudTrail and supports automatic key rotation, which satisfies auditing and compliance requirements.

---

## Question 32
**Question:**  
A company runs a two‑tier application on EC2 that connects to an Amazon RDS database. Database credentials must not be hardcoded and must rotate automatically.

**Options:**
- Store credentials in Systems Manager Parameter Store with rotation  
- Store credentials in an encrypted S3 configuration file  
- Store credentials as a secret in AWS Secrets Manager with automatic rotation  
- Store credentials in instance metadata

**Correct Answer:**  
Store the database credentials as a secret in AWS Secrets Manager with automatic rotation.

**Explanation:**  
AWS Secrets Manager securely stores credentials and supports automatic rotation using Lambda.

---

## Question 33
**Question:**  
A website provides downloadable historical performance reports globally. The solution must be highly scalable, cost‑effective, and require minimal infrastructure provisioning.

**Options:**
- Application Load Balancer with EC2 Auto Scaling  
- Amazon CloudFront with Amazon S3  
- AWS Lambda with DynamoDB  
- Route 53 with internal ALBs

**Correct Answer:**  
Amazon CloudFront and Amazon S3.

**Explanation:**  
S3 provides durable and scalable object storage, and CloudFront caches content at edge locations for low latency globally.

---

## Question 34
**Question:**  
A stateless processing application must process jobs in parallel and scale based on workload. The system must be loosely coupled and ensure durable job storage.

**Options:**
- Use SNS with EC2 Auto Scaling based on CPU  
- Use SQS with Auto Scaling based on network usage  
- Use SQS queue with Auto Scaling based on number of queue messages  
- Use SNS with Auto Scaling based on published messages

**Correct Answer:**  
Use an Amazon SQS queue and scale EC2 instances based on the number of messages in the queue.

**Explanation:**  
SQS provides durable job storage and decouples producers from consumers while Auto Scaling allows workers to scale based on queue depth.

---

## Question 35
**Question:**  
A gaming application uses UDP traffic and requires low latency, static IP addresses, and routing users to the nearest edge location.

**Options:**
- Route 53 with ALB and Lambda  
- CloudFront with NLB and Lambda  
- API Gateway with ALB and EC2  
- AWS Global Accelerator with NLB and EC2 Auto Scaling

**Correct Answer:**  
Use AWS Global Accelerator with a Network Load Balancer and EC2 Auto Scaling.

**Explanation:**  
AWS Global Accelerator provides static IP addresses and routes traffic through the AWS global network to the nearest healthy endpoint with low latency.

---

## Question 36
**Question:**  
A hospital uses API Gateway and Lambda to upload PDF and JPEG reports. The hospital must detect protected health information (PHI) in these documents.

**Options:**
- Amazon Textract + Amazon SageMaker  
- Custom Python libraries  
- Amazon Rekognition + Amazon Comprehend Medical  
- Amazon Textract + Amazon Comprehend Medical

**Correct Answer:**  
Use Amazon Textract to extract text and Amazon Comprehend Medical to detect PHI.

**Explanation:**  
Textract extracts text from documents and images, while Comprehend Medical analyzes the text to identify PHI.

---

## Question 37
**Question:**  
A company is creating its first AWS account. What is the first step?

**Options:**
- Set up the account using a company email address  
- Create the account via ELB  
- Create the account via CloudSearch  
- Create the account via EC2

**Correct Answer:**  
Set up the account using the company email address.

---

## Question 38
**Question:**  
A company wants to convert uploaded PDF files into JPG images. Files must be stored and processed in a scalable and cost‑effective way.

**Options:**
- Store files in DynamoDB and process with Lambda  
- Store files in Amazon S3 and trigger Lambda using S3 events  
- Use Elastic Beanstalk with EC2 and EFS  
- Use Elastic Beanstalk with EC2 and EBS

**Correct Answer:**  
Store files in Amazon S3 and trigger an AWS Lambda function using S3 PUT events.

**Explanation:**  
S3 provides scalable storage and event triggers allow serverless processing with Lambda.

---

## Question 39
**Question:**  
An AWS Glue ETL job processes data from an S3 bucket daily. The job is reprocessing old data each time it runs. How can this be prevented?

**Options:**
- Use FindMatches ML transform  
- Delete data after processing  
- Set NumberOfWorkers to 1  
- Enable job bookmarks

**Correct Answer:**  
Enable job bookmarks.

**Explanation:**  
Job bookmarks allow AWS Glue to track processed data and process only new records.

---

## Question 40
**Question:**  
A social media website allows users to upload images. The company must automatically detect inappropriate content with minimal development effort.

**Options:**
- Use Amazon Rekognition with human review for low‑confidence predictions  
- Deploy a custom ML model on AWS Fargate  
- Use Amazon SageMaker with Ground Truth  
- Use Amazon Comprehend

**Correct Answer:**  
Use Amazon Rekognition with human review for low‑confidence predictions.

**Explanation:**  
Amazon Rekognition provides prebuilt content moderation capabilities, reducing development effort.


## Question 41
**Question:**  
A company wants to reduce costs for a three‑tier architecture running on EC2 across development, test, and production environments. Production runs 24/7 while development and test run about 8 hours per day and will be stopped when not in use. Which EC2 purchasing option is MOST cost‑effective?

**Options:**
- Use Spot blocks for production and Reserved Instances for dev/test  
- Use On‑Demand for production and Spot blocks for dev/test  
- Use Reserved Instances for production and On‑Demand for dev/test  
- Use Spot Instances for production and Reserved Instances for dev/test  

**Correct Answer:**  
Use Reserved Instances for production and On‑Demand Instances for development and test.

**Explanation:**  
Reserved Instances provide the lowest cost for steady workloads running continuously (production). On‑Demand is ideal for intermittent workloads such as development and test environments.

---

## Question 42
**Question:**  
A company is deploying a serverless workload. An EventBridge rule will invoke an AWS Lambda function. Permissions must follow the principle of least privilege.

**Options:**
- Add an execution role with lambda:InvokeFunction and * as principal  
- Add a resource‑based policy with lambda:InvokeFunction and Service: events.amazonaws.com  
- Add an execution role with lambda:InvokeFunction and Service: lambda.amazonaws.com  
- Add a resource‑based policy with lambda:* and Service: events.amazonaws.com  

**Correct Answer:**  
Add a resource‑based policy with **lambda:InvokeFunction** and **Service: events.amazonaws.com** as the principal.

**Explanation:**  
EventBridge requires permission to invoke the Lambda function. A resource‑based policy allows only EventBridge to invoke the function, following least privilege.

---

## Question 43
**Question:**  
Two AWS accounts each contain a VPC (VPC‑TEST100 and VPC‑TEST200). The operations team needs secure file transfer between EC2 instances in these VPCs without single points of failure or bandwidth limitations.

**Options:**
- Use Direct Connect gateway  
- Create a VPC peering connection  
- Use VPC gateway endpoints  
- Use virtual private gateways  

**Correct Answer:**  
Create a **VPC peering connection** between the VPCs.

**Explanation:**  
VPC peering allows secure, direct networking between VPCs across accounts with no bandwidth bottleneck.

---

## Question 44
**Question:**  
A company needs to implement a High Performance Computing (HPC) environment requiring low‑latency network communication between EC2 instances.

**Options:**
- Placement groups  
- EC2 with DynamoDB  
- Elastic MapReduce  
- ELB with Auto Scaling  

**Correct Answer:**  
Placement groups.

**Explanation:**  
Placement groups place EC2 instances close together within an Availability Zone to enable low‑latency networking, which is ideal for HPC workloads.

---

## Question 45
**Question:**  
Amazon RDS automatically switches to a standby database in another Availability Zone during outages if which feature is enabled?

**Options:**
- Multiple read replicas  
- Multiple write replicas  
- Multi‑AZ deployment  
- Multi‑Region deployment  

**Correct Answer:**  
Multi‑AZ deployment.

**Explanation:**  
RDS Multi‑AZ creates a standby replica in another AZ and automatically fails over during outages.

---

## Question 46
**Question:**  
A company uses AWS Organizations. An S3 bucket in the management account must only allow access to users from accounts within the organization with minimal operational overhead.

**Options:**
- Use aws:PrincipalOrgPaths condition  
- Use aws:PrincipalTag condition  
- Monitor events with CloudTrail and update policies  
- Use aws:PrincipalOrgID condition key  

**Correct Answer:**  
Add the **aws:PrincipalOrgID** condition key in the S3 bucket policy.

**Explanation:**  
This allows access for all accounts within the AWS Organization without listing each account individually.

---

## Question 47
**Question:**  
An ecommerce company is launching a one‑deal‑a‑day website that must handle millions of requests per hour with millisecond latency.

**Options:**
- Static website on S3 with CloudFront, APIs with API Gateway + Lambda, data in DynamoDB  
- Full website hosted on S3 with order data stored in S3  
- Containers on EKS with RDS  
- EC2 Auto Scaling with ALB and RDS  

**Correct Answer:**  
Use **Amazon S3 + CloudFront for static content, API Gateway + Lambda for backend APIs, and DynamoDB for data storage.**

**Explanation:**  
These fully managed services provide massive scalability and low operational overhead.

---

## Question 48
**Question:**  
How can an EC2 instance be copied to another AWS Region?

**Options:**
- Instances cannot be copied  
- Stop instance and copy  
- Detach root volume and move it  
- Create an AMI and copy it to another region  

**Correct Answer:**  
Create an AMI of the instance and copy the AMI to the destination region.

**Explanation:**  
After copying the AMI, a new instance can be launched in the target region.

---

## Question 49
**Question:**  
A web application stores user‑uploaded documents on EBS volumes attached to EC2 instances in multiple Availability Zones behind an ALB. Users sometimes see only a subset of documents. What is the correct solution?

**Options:**
- Send requests to both servers  
- Copy data between EBS volumes  
- Use Amazon EFS shared storage  
- Route users to the correct server  

**Correct Answer:**  
Copy the data from both EBS volumes to **Amazon EFS** and store new files in EFS.

**Explanation:**  
EFS provides shared file storage that can be mounted by multiple EC2 instances simultaneously.

---

## Question 50
**Question:**  
Which of the following are IAM components? (Select two)

**Options:**
- Organizational Units  
- Users  
- EC2  
- Groups  
- SNS  

**Correct Answers:**
- Users  
- Groups  

**Explanation:**  
IAM users represent identities, and IAM groups allow permissions to be managed collectively for multiple users.


## Question 51
**Question:**  
A gaming company wants to ensure that all EC2 instances, RDS DB instances, and Redshift clusters are properly tagged. The company wants to minimize operational effort. What should a solutions architect do?

**Options:**
- Write API calls and run them periodically using Lambda  
- Use Cost Explorer and manually tag resources  
- Use AWS Config rules to detect improperly tagged resources  
- Write API calls and run them periodically on EC2  

**Correct Answer:**  
Use AWS Config rules to define and detect resources that are not properly tagged.

**Explanation:**  
AWS Config can continuously monitor resource configurations and evaluate them against rules to ensure required tags exist.

---

## Question 52
**Question:**  
An ecommerce website hosted on‑premises in the US is launching in Europe. The backend must remain on‑premises. The company needs to improve page load times for European users quickly.

**Options:**
- Move the website to S3 with cross‑region replication  
- Launch an EC2 instance in us‑east‑1  
- Use Route 53 geoproximity routing  
- Use Amazon CloudFront with the on‑premises server as a custom origin  

**Correct Answer:**  
Use Amazon CloudFront with a custom origin pointing to the on‑premises servers.

**Explanation:**  
CloudFront caches content at global edge locations, improving performance for European users without moving the backend.

---

## Question 53
**Question:**  
An application receives data through API Gateway into a Lambda function which stores data in Aurora PostgreSQL. High traffic requires increasing Lambda quotas. A better architecture is needed for scalability.

**Options:**
- Refactor to EC2 with Tomcat  
- Two Lambda functions connected via SNS  
- Two Lambda functions connected via SQS  
- Move database to DynamoDB with DAX  

**Correct Answer:**  
Use two Lambda functions integrated through an Amazon SQS queue.

**Explanation:**  
SQS decouples components and allows each Lambda function to scale independently.

---

## Question 54
**Question:**  
A company wants to run containerized applications but does not want to manage infrastructure.

**Options:**
- ECS on AWS Fargate  
- ECS on EC2 instances  
- ECS optimized AMI on EC2  
- EC2 instances with Docker installed  

**Correct Answer:**  
Use Amazon ECS on AWS Fargate.

**Explanation:**  
AWS Fargate is a serverless container compute engine that eliminates the need to manage EC2 instances.

---

## Question 55
**Question:**  
A two‑tier application runs in a single Availability Zone. Web servers are in public subnets and the database is in a private subnet. High availability is required. (Select TWO)

**Correct Answers:**
- Create new public and private subnets in another AZ and deploy an RDS Multi‑AZ database  
- Create an EC2 Auto Scaling group and an Application Load Balancer across multiple AZs

**Explanation:**  
Deploying infrastructure across multiple Availability Zones with load balancing and Multi‑AZ databases ensures high availability.

---

## Question 56
**Question:**  
A hybrid architecture must connect on‑premises infrastructure to AWS with low latency and high availability. The company wants to minimize cost and accept slower performance if the primary connection fails.

**Options:**
- Direct Connect with automatic failover  
- Direct Connect with VPN backup  
- Two VPN tunnels  
- Two Direct Connect connections  

**Correct Answer:**  
Provision an AWS Direct Connect connection with a VPN connection as backup.

**Explanation:**  
Direct Connect provides consistent low latency, while VPN offers a lower‑cost failover solution.

---

## Question 57
**Question:**  
A database migrated to EC2 requires 64,000 IOPS and should use a single EBS volume if possible.

**Options:**
- Use I3 instances with instance store  
- Use two io1 volumes with RAID  
- Use Nitro‑based EC2 with a Provisioned IOPS SSD (io1) volume  
- Use four gp2 volumes with RAID  

**Correct Answer:**  
Use a Nitro‑based EC2 instance with an EBS Provisioned IOPS SSD (io1) volume.

**Explanation:**  
Provisioned IOPS SSD volumes support high IOPS workloads and Nitro instances provide high‑performance EBS throughput.

---

## Question 58
**Question:**  
An application frequently transfers images to and from S3 within the same region. Data transfer costs have increased. What should be done?

**Options:**
- Route traffic through an internet gateway  
- Deploy an S3 VPC gateway endpoint  
- Route calls through API Gateway  
- Use a NAT gateway  

**Correct Answer:**  
Deploy an S3 VPC gateway endpoint and configure endpoint policies.

**Explanation:**  
VPC endpoints allow private connectivity to S3 without routing traffic through the internet, reducing data transfer costs.

---

## Question 59
**Question:**  
In Amazon ECS, what is the logical grouping of container instances where tasks are placed?

**Options:**
- Container  
- Cluster  
- Container instance  
- Task definition  

**Correct Answer:**  
Cluster.

**Explanation:**  
A cluster is a logical group of container instances that run tasks or services.

---

## Question 60
**Question:**  
When mapping an Amazon EBS volume to an EC2 instance in AWS CloudFormation, what identifiers should be referenced?

**Options:**
- Physical IDs of the instance  
- Logical ID of the instance  
- Logical IDs of both the block storage and the instance  
- Physical IDs of both resources  

**Correct Answer:**  
Reference the logical IDs of both the EBS volume and the EC2 instance.

**Explanation:**  
CloudFormation uses logical IDs within templates to reference and connect resources.


## Question 61
**Question:**  
A company runs a public three‑tier application in a VPC across multiple Availability Zones. Application EC2 instances run in private subnets and must download software patches from the internet, but they cannot be directly accessible from the internet. Which actions should be taken? (Select TWO)

**Options:**
- Define a custom route table with a route to the NAT gateway for internet traffic and associate it with the private subnets  
- Configure a NAT instance in a private subnet  
- Define a route table with a route to the internet gateway for private subnets  
- Assign Elastic IP addresses to the EC2 instances  
- Configure a NAT gateway in a public subnet  

**Correct Answers:**
- Configure a NAT gateway in a public subnet  
- Define a custom route table with a route to the NAT gateway and associate it with the private subnets

**Explanation:**  
A NAT gateway allows instances in private subnets to initiate outbound internet traffic without allowing inbound internet connections. The private subnet route table must route internet traffic to the NAT gateway.

---

## Question 62
**Question:**  
If SSL traffic should remain encrypted end‑to‑end and should not terminate at the load balancer, which protocol should be used from the client to the load balancer?

**Options:**
- DNS  
- HTTPS  
- TCP  
- DHCP  

**Correct Answer:**  
TCP.

**Explanation:**  
Using TCP allows SSL traffic to pass through the load balancer without termination so that encryption remains intact until it reaches the backend servers.

---

## Question 63
**Question:**  
A company runs an SMB file server on‑premises storing large files. Files are frequently accessed during the first few days after creation, but after 7 days they are rarely accessed. Storage capacity is nearly exhausted. The solution must maintain low‑latency access to recent files and support lifecycle management.

**Options:**
- Use AWS DataSync to copy files older than 7 days to AWS  
- Install utilities on user computers to access S3 and archive after 7 days  
- Create an Amazon S3 File Gateway and apply an S3 Lifecycle policy to move data to Glacier Deep Archive after 7 days  
- Deploy Amazon FSx for Windows File Server  

**Correct Answer:**  
Create an Amazon S3 File Gateway and configure an S3 Lifecycle policy to transition data to S3 Glacier Deep Archive after 7 days.

**Explanation:**  
S3 File Gateway provides cached local access to frequently used files while storing data in S3. Lifecycle policies automatically move older files to lower‑cost storage.

---

## Question 64
**Question:**  
A regulatory requirement states that uploaded documents cannot be modified or deleted after being stored. Which AWS solution meets this requirement?

**Options:**
- Store files on Amazon EFS in read‑only mode  
- Store files in S3 with versioning and restrict ACLs  
- Store files in S3 with lifecycle archiving  
- Store files in S3 with Versioning and Object Lock enabled  

**Correct Answer:**  
Store documents in an S3 bucket with **S3 Versioning and S3 Object Lock enabled**.

**Explanation:**  
S3 Object Lock enforces write‑once‑read‑many (WORM) storage, preventing objects from being modified or deleted for a specified period.

---

## Question 65
**Question:**  
A news portal delivers global content using an EC2 API server behind an Application Load Balancer. Users are located worldwide and the company wants the lowest possible latency.

**Options:**
- Deploy the stack in two regions with Route 53 geolocation routing  
- Deploy the stack in two regions with Route 53 latency routing  
- Deploy in one region and use CloudFront for static and dynamic content  
- Use CloudFront for static content and ALB for dynamic content  

**Correct Answer:**  
Deploy the application stack in two AWS Regions and use **Route 53 latency‑based routing**.

**Explanation:**  
Latency routing directs users to the region with the lowest network latency, improving response times for global users.

