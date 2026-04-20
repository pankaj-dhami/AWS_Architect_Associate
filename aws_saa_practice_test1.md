# AWS Certified Solutions Architect Associate - Practice Test 1

## Question 1
Question:  
A gaming company is implementing a shared storage solution for a gaming application hosted in an on‑premises data center. The company needs the ability to use Lustre clients to access data. The solution must be fully managed.

Options:
A. Create an Amazon EC2 Windows instance and configure a Windows file share.  
B. Create an AWS Storage Gateway file gateway and create a file share.  
C. Create an Amazon EFS file system configured to support Lustre.  
D. Create an Amazon FSx for Lustre file system.

Correct Answer:  
D. Create an Amazon FSx for Lustre file system.

Explanation:  
Amazon FSx for Lustre is a fully managed high‑performance file system designed for workloads requiring Lustre clients.

---

## Question 2
Question:  
An e‑commerce application runs on EC2 instances behind an ALB with Auto Scaling across multiple AZs. A MySQL database on EC2 cannot handle increasing read workloads.

Options:
A. Use Amazon RDS Single‑AZ and add reader instances.  
B. Use Amazon Redshift with a single node.  
C. Use Amazon ElastiCache Memcached with Spot instances.  
D. Use Amazon Aurora Multi‑AZ with Aurora Replicas and Auto Scaling.

Correct Answer:  
D. Use Amazon Aurora Multi‑AZ with Aurora Replicas.

Explanation:  
Aurora supports high read scalability using replicas and provides high availability.

---

## Question 3
Question:  
Which IAM condition key checks whether a request was sent using SSL?

Options:
A. aws:Agent  
B. aws:SourceIp  
C. aws:SecureTransport  
D. aws:SecureIp  

Correct Answer:  
C. aws:SecureTransport

Explanation:  
`aws:SecureTransport` returns true if the request uses HTTPS.

---

## Question 4
Question:  
If a company wants to build its own payment application, it should take advantage of the flexibility of which service?

Options:
A. Payoneer Payment Services  
B. eBay Payment Service  
C. PayPal Payment Service  
D. Amazon Flexible Payments Service (FPS)

Correct Answer:  
D. Amazon Flexible Payments Service (FPS)

---

## Question 5
Question:  
A VPC has public and private subnets across three AZs. Private subnets require internet access for EC2 instances to download updates.

Options:
A. Create an egress‑only internet gateway.  
B. Create three NAT instances.  
C. Create another internet gateway in private subnets.  
D. Create three NAT gateways in the public subnets.

Correct Answer:  
D. Create three NAT gateways in public subnets.

---

## Question 6
Question:  
A company uses DynamoDB and requires an RPO of 15 minutes and RTO of 1 hour.

Options:
A. Configure DynamoDB point‑in‑time recovery.  
B. Schedule EBS snapshots.  
C. Use DynamoDB global tables.  
D. Export DynamoDB data daily to S3 Glacier.

Correct Answer:  
A. Configure DynamoDB point‑in‑time recovery.

---

## Question 7
Question:  
An IT company must rotate RDS credentials across multiple AWS Regions.

Options:
A. Store credentials in S3 with SSE.  
B. Store secrets in DynamoDB encrypted with KMS.  
C. Store secrets in AWS Secrets Manager with multi‑Region replication.  
D. Store credentials in Systems Manager Parameter Store.

Correct Answer:  
C. Store secrets in AWS Secrets Manager.

---

## Question 8
Question:  
A web application uses Aurora PostgreSQL in a single AZ and must become highly available.

Options:
A. Move EC2 instances to different Regions.  
B. Configure Auto Scaling across AZs and Aurora Multi‑AZ with RDS Proxy.  
C. Keep one AZ and rely on snapshots.  
D. Use S3 events to write to DB.

Correct Answer:  
B. Configure Auto Scaling across AZs and Aurora Multi‑AZ.

---

## Question 9
Question:  
All cloud data must be encrypted at rest using keys stored on‑premises.

Options:
A. SSE‑KMS  
B. SSE‑S3  
C. SSE‑C  
D. Client‑side encryption  

Correct Answers:  
C. SSE‑C  
D. Client‑side encryption

---

## Question 10
Question:  
A voting system receives hundreds of thousands of requests per minute. The database cannot keep up with writes.

Options:
A. Resize the database during voting.  
B. Send votes to Amazon SQS and process with worker instances.  
C. Use Multi‑AZ database writes.  
D. Use Lambda for request handling.

Correct Answer:  
B. Send votes to Amazon SQS.

---

## Question 11
Question:  
A public application behind an ALB must use a certificate issued by an external CA.

Options:
A. Issue a certificate from AWS ACM.  
B. Import the certificate into ACM and use managed renewal.  
C. Use ACM Private CA.  
D. Import the certificate into ACM and manually rotate before expiration.

Correct Answer:  
D. Import the certificate and manually rotate.

---

## Question 12
Question:  
After creating VPC peering between two VPCs, can instances access the internet via the peer VPC’s IGW?

Options:
A. Yes, peering allows internet routing.  
B. No, VPC peering does not support edge‑to‑edge routing.  
C. Yes, if route tables are configured.  
D. Only if a NAT gateway is used.

Correct Answer:  
B. VPC peering does not support edge‑to‑edge routing.

---

## Question 13
Question:  
An e‑commerce application must process orders in the exact order received.

Options:
A. Use SQS FIFO with Lambda processing.  
B. Use SNS with Lambda.  
C. Use API Gateway authorizers.  
D. Use SQS standard queues.

Correct Answer:  
A. SQS FIFO queue.

---

## Question 14
Question:  
A transcription system stores uploaded audio files and generated text files. Storage capacity is unknown.

Options:
A. Multiple EBS volumes  
B. Amazon Glacier vault  
C. Amazon S3 bucket  
D. Instance store

Correct Answer:  
C. Amazon S3.

---

## Question 15
Question:  
Web servers frequently access an RDS database and credentials must rotate automatically.

Options:
A. Encrypt credentials with KMS on the server.  
B. Store credentials in AWS Secrets Manager.  
C. Store credentials in Systems Manager OpsCenter.  
D. Store credentials in S3.

Correct Answer:  
B. AWS Secrets Manager.

---

## Question 16
Question:  
Ensure S3 bucket configuration changes are monitored.

Options:
A. AWS Config with rules  
B. AWS Trusted Advisor  
C. Amazon Inspector  
D. S3 server access logging

Correct Answer:  
A. AWS Config.

---

## Question 17
Question:  
A company migrating Windows file servers to AWS requires minimal changes and low latency.

Options:
A. Deploy S3 File Gateway  
B. Use FSx for Windows + FSx File Gateway  
C. Deploy Amazon FSx for Windows File Server  
D. Migrate data to S3

Correct Answer:  
C. Amazon FSx for Windows File Server.

---

## Question 18
Question:  
A company must privately connect to a service in another provider’s VPC.

Options:
A. Virtual private gateway  
B. AWS PrivateLink endpoint  
C. NAT gateway  
D. VPC peering

Correct Answer:  
B. AWS PrivateLink.

---

## Question 19
Question:  
Limit S3 bucket access to accounts within the same AWS Organization.

Options:
A. Monitor CloudTrail events  
B. Use aws:PrincipalOrgID condition key  
C. Use aws:PrincipalOrgPaths  
D. Use principal tags

Correct Answer:  
B. aws:PrincipalOrgID.

---

## Question 20
Question:  
Configure security groups for a two‑tier web application using SQL Server.

Options:
A. Allow inbound 443 to DB from web SG  
B. Allow inbound 1433 to DB from web SG  
C. Allow outbound 443 from web tier to internet  
D. Allow DB outbound traffic to web tier

Correct Answers:  
B. Allow inbound 1433 from web tier  
C. Allow inbound 443 to web tier from internet

---

## Question 21
Question:  
An HTTP application behind a Network Load Balancer (NLB) is not detecting HTTP errors from EC2 instances.

Options:
A. Enable HTTP health checks on the NLB  
B. Create a CloudWatch alarm for UnhealthyHostCount  
C. Replace the NLB with an Application Load Balancer and configure HTTP health checks  
D. Add a cron job to restart the service on EC2

Correct Answer:  
C. Replace the NLB with an Application Load Balancer.

Explanation:  
NLB only supports TCP health checks. ALB supports HTTP health checks.

---

## Question 22
Question:  
AWS Organizations notifications sent to root email were missed.

Options:
A. Forward root emails to all users  
B. Use same root email for all accounts  
C. Configure root emails as distribution lists and configure alternate contacts  
D. Send notifications to a single admin

Correct Answer:  
C. Configure root email distribution lists and alternate contacts.

---

## Question 23
Question:  
What determines the cost of AWS CloudFormation?

Options:
A. $0.20 per template  
B. Time to build stack  
C. $0.101 per template  
D. No additional cost, only pay for resources created

Correct Answer:  
D. CloudFormation itself has no cost.

---

## Question 24
Question:  
A company must retain 10 years of logs with minimal cost.

Options:
A. Store logs in S3 and move to Glacier Deep Archive after 1 month  
B. Store logs in CloudWatch and export to Glacier  
C. Store logs in S3 and move via AWS Backup  
D. Store logs in CloudWatch and lifecycle to Glacier

Correct Answer:  
A. S3 with lifecycle to Glacier Deep Archive.

---

## Question 25
Question:  
A company uploads 500GB daily from global locations to one S3 bucket.

Options:
A. Upload to regional buckets then replicate  
B. Use Snowball Edge daily  
C. Upload to EC2 then snapshot to S3  
D. Enable S3 Transfer Acceleration and multipart upload

Correct Answer:  
D. S3 Transfer Acceleration.

---

## Question 26
Question:  
A monolithic application is being broken into smaller services while keeping code.

Options:
A. Host on Amazon ECS with an ALB  
B. Use AWS Lambda with API Gateway  
C. Host on EC2 with Auto Scaling  
D. Use Elastic Beanstalk

Correct Answer:  
A. Amazon ECS with ALB.

---

## Question 27
Question:  
Which S3 storage classes provide 11 nines durability?

Options:
A. Standard, Standard‑IA, One Zone‑IA  
B. Standard, Glacier, RRS  
C. Standard‑IA, One Zone‑IA, RRS  
D. RRS, Standard, One Zone‑IA

Correct Answer:  
A. Standard, Standard‑IA, One Zone‑IA.

---

## Question 28
Question:  
How can an EC2 instance determine its public and private IP?

Options:
A. Query instance metadata  
B. Query CloudWatch metrics  
C. Use ipconfig or ifconfig  
D. Query instance userdata

Correct Answer:  
A. Query instance metadata.

---

## Question 29
Question:  
A website must withstand large DDoS attacks.

Options:
A. Use Spot Instances scaling  
B. Use Lambda to block IPs  
C. Use Amazon CloudFront  
D. Use AWS Shield Advanced

Correct Answers:  
C. Amazon CloudFront  
D. AWS Shield Advanced

---

## Question 30
Question:  
An EC2 instance must access S3 privately without internet.

Options:
A. Create S3 gateway VPC endpoint  
B. Use CloudWatch logs export  
C. Use API Gateway private link  
D. Use instance profile

Correct Answer:  
A. Gateway VPC endpoint.

---

## Question 31
Question:  
Encrypt S3 data, log key usage, and rotate yearly.

Options:
A. SSE‑KMS manual rotation  
B. SSE‑S3  
C. SSE‑KMS automatic rotation  
D. SSE‑C

Correct Answer:  
C. SSE‑KMS with automatic rotation.

---

## Question 32
Question:  
Avoid hardcoding database credentials and rotate automatically.

Options:
A. Parameter Store encrypted parameters  
B. Store credentials in S3  
C. Store credentials in Secrets Manager  
D. Store in instance metadata

Correct Answer:  
C. AWS Secrets Manager.

---

## Question 33
Question:  
Deliver downloadable reports globally with minimal infrastructure.

Options:
A. ALB + EC2 Auto Scaling  
B. CloudFront + S3  
C. Lambda + DynamoDB  
D. Route53 + ALB

Correct Answer:  
B. CloudFront + S3.

---

## Question 34
Question:  
Process jobs in parallel while ensuring durability.

Options:
A. SNS + Auto Scaling CPU scaling  
B. SQS + Auto Scaling based on network usage  
C. SQS + Auto Scaling based on queue length  
D. SNS + Auto Scaling by message count

Correct Answer:  
C. SQS queue with scaling based on queue length.

---

## Question 35
Question:  
Gaming application using UDP requires global low latency and static IP.

Options:
A. Route53 + ALB  
B. CloudFront + NLB  
C. API Gateway + ALB  
D. AWS Global Accelerator + NLB

Correct Answer:  
D. AWS Global Accelerator.

---

## Question 36
Question:  
Detect PHI in medical documents.

Options:
A. Textract + SageMaker  
B. Python libraries  
C. Rekognition + Comprehend Medical  
D. Textract + Comprehend Medical

Correct Answer:  
D. Textract + Comprehend Medical.

---

## Question 37
Question:  
First step when creating an AWS account?

Options:
A. Use company email address  
B. Use ELB  
C. Use CloudSearch  
D. Use EC2

Correct Answer:  
A. Company email address.

---

## Question 38
Question:  
Convert PDF to JPG files at scale.

Options:
A. Store in DynamoDB + Lambda  
B. Store in S3 + Lambda triggered by S3 events  
C. Elastic Beanstalk + EFS  
D. Elastic Beanstalk + EBS

Correct Answer:  
B. S3 + Lambda.

---

## Question 39
Question:  
AWS Glue reprocesses all data each run.

Options:
A. Use FindMatches transform  
B. Delete processed data  
C. Reduce workers  
D. Use job bookmarks

Correct Answer:  
D. Job bookmarks.

---

## Question 40
Question:  
Detect inappropriate images with minimal development.

Options:
A. Amazon Rekognition + human review  
B. Fargate custom ML model  
C. SageMaker model  
D. Amazon Comprehend

Correct Answer:  
A. Amazon Rekognition.

---

## Question 41
Question:  
A company wants to reduce cost of a three‑tier architecture running on EC2. Production runs 24/7 while dev and test run only part of the day.

Options:
A. Spot for production, Reserved for dev/test  
B. On‑Demand for production, Spot for dev/test  
C. Reserved Instances for production, On‑Demand for dev/test  
D. Spot for production, Reserved for dev/test

Correct Answer:  
C. Reserved Instances for production, On‑Demand for dev/test.

---

## Question 42
Question:  
A Lambda function must be invoked by an EventBridge rule using least privilege.

Options:
A. Add execution role with lambda:InvokeFunction and principal *  
B. Add resource‑based policy allowing events.amazonaws.com to invoke  
C. Add execution role with lambda.amazonaws.com principal  
D. Add resource policy with lambda:* for EventBridge

Correct Answer:  
B. Resource‑based policy allowing events.amazonaws.com.

---

## Question 43
Question:  
Two AWS accounts each contain a VPC and must securely copy files between EC2 instances.

Options:
A. Direct Connect gateway  
B. VPC peering connection  
C. VPC gateway endpoints  
D. Virtual private gateway

Correct Answer:  
B. VPC peering connection.

---

## Question 44
Question:  
A High Performance Computing (HPC) system requires low‑latency networking.

Options:
A. Placement groups  
B. EC2 with DynamoDB  
C. Elastic MapReduce  
D. ELB with Auto Scaling

Correct Answer:  
A. Placement groups.

---

## Question 45
Question:  
RDS automatically switches to a standby replica in another AZ when which feature is enabled?

Options:
A. Multiple read replicas  
B. Multiple write replicas  
C. Multi‑AZ deployment  
D. Multi‑Region deployment

Correct Answer:  
C. Multi‑AZ deployment.

---

## Question 46
Question:  
Restrict access to an S3 bucket only to accounts within the same AWS Organization.

Options:
A. aws:PrincipalOrgPaths  
B. aws:PrincipalTag  
C. CloudTrail monitoring  
D. aws:PrincipalOrgID

Correct Answer:  
D. aws:PrincipalOrgID.

---

## Question 47
Question:  
A “one‑deal‑a‑day” website must handle millions of requests with millisecond latency.

Options:
A. S3 + CloudFront + API Gateway + Lambda + DynamoDB  
B. Multiple S3 buckets with CloudFront  
C. Kubernetes on EKS with RDS  
D. EC2 Auto Scaling with ALB

Correct Answer:  
A. S3 + CloudFront + API Gateway + Lambda + DynamoDB.

---

## Question 48
Question:  
How can an EC2 instance be copied to another Region?

Options:
A. Directly copy instance  
B. Stop instance and copy  
C. Detach root volume and attach in another region  
D. Create an AMI and copy it to another Region

Correct Answer:  
D. Create an AMI and copy it.

---

## Question 49
Question:  
Users see different documents depending on which EC2 instance serves the request.

Options:
A. Send requests to both servers  
B. Copy data to both EBS volumes  
C. Move data to Amazon EFS and mount on both instances  
D. Use ALB sticky sessions

Correct Answer:  
C. Use Amazon EFS.

---

## Question 50
Question:  
Which are IAM components?

Options:
A. Organizational Units  
B. Users  
C. EC2  
D. Groups  
E. SNS

Correct Answers:  
B. Users  
D. Groups

---

## Question 51
Question:  
Ensure EC2, RDS, and Redshift resources always have tags.

Options:
A. Lambda script with API calls  
B. Cost Explorer reports  
C. AWS Config rules  
D. EC2 script with cron

Correct Answer:  
C. AWS Config rules.

---

## Question 52
Question:  
An on‑premises website must load quickly for European users.

Options:
A. Move site to S3  
B. Launch EC2 in us‑east‑1  
C. Route53 geoproximity routing  
D. CloudFront with custom origin pointing to on‑prem

Correct Answer:  
D. CloudFront with custom origin.

---

## Question 53
Question:  
A Lambda ingestion system is reaching scaling limits when writing to Aurora.

Options:
A. Move code to EC2  
B. Two Lambdas connected by SNS  
C. Two Lambdas connected by SQS  
D. Migrate DB to DynamoDB

Correct Answer:  
C. Lambda functions connected via SQS.

---

## Question 54
Question:  
A company wants to run containers without managing infrastructure.

Options:
A. ECS on Fargate  
B. ECS on EC2  
C. ECS optimized AMI on EC2  
D. EC2 instances with Docker

Correct Answer:  
A. ECS on Fargate.

---

## Question 55
Question:  
A two‑tier application running in one AZ must become highly available.

Options:
A. Create subnets in another AZ and deploy RDS Multi‑AZ  
B. Add Auto Scaling and ALB across AZs  
C. Create new subnets in same AZ  
D. Migrate DB to public subnet

Correct Answers:  
A. RDS Multi‑AZ in private subnets  
B. EC2 Auto Scaling with ALB across AZs

---

## Question 56
Question:  
Hybrid architecture needs low latency but low‑cost backup connectivity.

Options:
A. Direct Connect with auto failover  
B. Direct Connect with VPN backup  
C. Two VPN tunnels  
D. Two Direct Connect connections

Correct Answer:  
B. Direct Connect with VPN backup.

---

## Question 57
Question:  
A database requires 64,000 IOPS on a single EBS volume.

Options:
A. I3 instance with instance store  
B. Two io1 volumes striped  
C. Nitro EC2 instance with io1 Provisioned IOPS volume  
D. RAID 0 gp2 volumes

Correct Answer:  
C. Nitro EC2 with io1.

---

## Question 58
Question:  
An application frequently accesses S3 in the same Region and transfer costs increased.

Options:
A. Use Internet Gateway  
B. Use S3 VPC Gateway Endpoint  
C. Use API Gateway  
D. Use NAT gateway

Correct Answer:  
B. S3 VPC Gateway Endpoint.

---

## Question 59
Question:  
In Amazon ECS, what is a logical grouping of container instances?

Options:
A. Container  
B. Cluster  
C. Container instance  
D. Task definition

Correct Answer:  
B. Cluster.

---

## Question 60
Question:  
In CloudFormation how do you map EBS to EC2?

Options:
A. Reference physical instance IDs  
B. Logical instance IDs  
C. Logical IDs of both EBS and EC2  
D. Physical IDs of both

Correct Answer:  
C. Logical IDs of both.

---

## Question 61
Question:  
Private EC2 instances must download patches from the internet.

Options:
A. Route table pointing to NAT gateway  
B. NAT instance in private subnet  
C. Route table to Internet Gateway  
D. Assign Elastic IPs

Correct Answers:  
A. Route table to NAT gateway  
B. NAT gateway in public subnet

---

## Question 62
Question:  
If SSL should not terminate on the load balancer, which protocol is used?

Options:
A. DNS  
B. HTTPS  
C. TCP  
D. DHCP

Correct Answer:  
C. TCP.

---

## Question 63
Question:  
A company must extend an SMB file server with lifecycle management.

Options:
A. AWS DataSync  
B. Install S3 utilities on user computers  
C. Amazon S3 File Gateway with lifecycle to Glacier  
D. Amazon FSx for Windows

Correct Answer:  
C. S3 File Gateway with lifecycle.

---

## Question 64
Question:  
Uploaded documents must never be modified or deleted.

Options:
A. EFS read‑only mount  
B. S3 Versioning with read‑only ACL  
C. S3 lifecycle archiving  
D. S3 Versioning with Object Lock

Correct Answer:  
D. S3 Versioning with Object Lock.

---

## Question 65
Question:  
A global news portal must deliver personalized content with lowest latency.

Options:
A. Multi‑Region deployment with Route53 geolocation  
B. Multi‑Region deployment with Route53 latency routing  
C. Single region with CloudFront for all content  
D. Single region with CloudFront only for static content

Correct Answer:  
B. Route53 latency‑based routing with multi‑Region deployment.
