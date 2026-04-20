# AWS Certified Solutions Architect Associate - Practice Test 2

## Question 1
**Question**  
An IT company has registered its domain name with Amazon Route 53. The company uses Amazon API Gateway in the ca-central-1 Region as a public interface for its backend microservice APIs. Third‑party services consume the APIs securely. The company wants to design its API Gateway URL with the company's domain name and corresponding certificate so that the third‑party services can use HTTPS. Which option is correct?

**Options**
A. Create a Regional API Gateway endpoint. Associate the API Gateway endpoint with the company's domain name. Import the public certificate associated with the company's domain name into AWS Certificate Manager (ACM) in the same Region. Attach the certificate to the API Gateway endpoint. Configure Route 53 to route traffic to the API Gateway endpoint.  
B. Create a Regional API Gateway endpoint. Associate the API Gateway endpoint with the company's domain name. Import the public certificate into ACM in the us-east-1 Region. Attach the certificate to the APIs and create Route 53 DNS records.  
C. Create stage variables in API Gateway to overwrite the default URL and import the certificate into ACM.  
D. Create Route 53 DNS records and point an alias record to the Regional API Gateway stage endpoint. Import the certificate into ACM in us-east-1.

**Correct Answer**  
A

**Explanation**  
Import the certificate into ACM in the same Region as the API Gateway endpoint and map the custom domain name. Route 53 then routes traffic to the API Gateway endpoint securely using HTTPS.

---

## Question 2
**Question**  
A food company needs guaranteed Amazon EC2 capacity in three specific Availability Zones in a Region for an event that will last 1 week. What should the company do?

**Options**  
A. Purchase Reserved Instances specifying the Region.  
B. Create an On‑Demand Capacity Reservation specifying the Region.  
C. Purchase Reserved Instances specifying the Region and AZs.  
D. Create an On‑Demand Capacity Reservation specifying the Region and the three Availability Zones.

**Correct Answer**  
D

**Explanation**  
On‑Demand Capacity Reservations allow you to reserve compute capacity in specific Availability Zones.

---

## Question 3
**Question**  
AWS requires ____________ when you need to specify a resource uniquely across all of AWS.

**Options**  
A. User ID  
B. Amazon Resource Names  
C. Account ID  
D. User IAM Policy  

**Correct Answer**  
B

**Explanation**  
Amazon Resource Names (ARNs) uniquely identify AWS resources across all services.

---

## Question 4
**Question**  
A gaming company must track configuration changes and record API call history for AWS resources. Which solution is correct?

**Options**  
A. CloudTrail for configuration changes and Config for API calls  
B. AWS Config for configuration changes and AWS CloudTrail for API calls  
C. AWS Config for configuration changes and CloudWatch for API calls  
D. CloudTrail for configuration changes and CloudWatch for API calls  

**Correct Answer**  
B

**Explanation**  
AWS Config records configuration changes, while CloudTrail records API activity.

---

## Question 5
**Question**  
In a VPC network, access control lists (ACLs) act as a firewall for associated subnets controlling traffic at which level?

**Options**  
A. VPC  
B. EC2  
C. Subnet  
D. Database  

**Correct Answer**  
C

**Explanation**  
Network ACLs operate at the subnet level.

---

## Question 6
**Question**  
An application on EC2 in a VPC must access Amazon S3 without sending traffic over the internet. What should be done?

**Options**  
A. Configure an S3 gateway endpoint  
B. Create an S3 bucket in the same Region  
C. Configure a NAT gateway  
D. Create an S3 bucket in a private subnet  

**Correct Answer**  
A

**Explanation**  
Gateway endpoints allow private connectivity between VPC and S3 without internet routing.

---

## Question 7
**Question**  
An on‑premises application backs up time‑sensitive data to S3 but internet bandwidth is limited. What long‑term solution should be used?

**Options**  
A. Request removal of S3 service limits  
B. Use daily AWS Snowball devices  
C. Establish AWS VPN connections  
D. Establish a new AWS Direct Connect connection  

**Correct Answer**  
D

**Explanation**  
Direct Connect provides dedicated network connectivity with higher bandwidth and lower latency.

---

## Question 8
**Question**  
Traffic connects to an EC2 instance using its private IP. A standby instance must quickly take over if the primary fails. What should be done?

**Options**  
A. Move an Elastic IP between instances  
B. Configure DHCP to assign the same private IP  
C. Use an Application Load Balancer  
D. Attach a secondary Elastic Network Interface and move it to the standby instance  

**Correct Answer**  
D

**Explanation**  
Moving the ENI preserves the private IP and allows quick failover.

---

## Question 9
**Question**  
A media application stores files in S3. Files must survive AZ loss and access patterns are unpredictable. Which storage class minimizes cost?

**Options**  
A. S3 Intelligent‑Tiering  
B. S3 Standard‑IA  
C. S3 Standard  
D. S3 One Zone‑IA  

**Correct Answer**  
A

**Explanation**  
Intelligent‑Tiering automatically moves objects between tiers based on usage patterns.

---

## Question 10
**Question**  
An Aurora Multi‑AZ cluster experiences heavy read traffic causing write latency. What should be done?

**Options**  
A. Create a second Aurora database  
B. Enable read‑through caching  
C. Read from the Multi‑AZ standby  
D. Create Aurora replicas and modify the application to use their endpoints  

**Correct Answer**  
D

**Explanation**  
Aurora replicas offload read traffic while writes continue on the primary.

---

## Question 11
**Question**  
A containerized web application must move to AWS with minimal code changes and scale automatically.

**Options**  
A. AWS Lambda with API Gateway  
B. HPC cluster with AWS ParallelCluster  
C. AWS Fargate on ECS with Auto Scaling and ALB  
D. Two EC2 instances with ALB  

**Correct Answer**  
C

**Explanation**  
Fargate runs containers without managing infrastructure and supports auto scaling.

---

## Question 12
**Question**  
A photo processing application must scale for varying traffic.

**Options**  
A. Three EC2 instances with EBS volumes  
B. Use Kinesis Data Firehose  
C. Use Lambda and store photos and metadata in DynamoDB  
D. Use Lambda to process photos, store images in S3 and metadata in DynamoDB  

**Correct Answer**  
D

**Explanation**  
Serverless architecture using S3 + Lambda + DynamoDB scales automatically.

---

## Question 13
**Question**  
A SharePoint deployment requires Windows shared storage integrated with Active Directory.

**Options**  
A. Mount S3 as a volume  
B. Use Amazon EFS with AD authentication  
C. Use Amazon FSx for Windows File Server with AD  
D. Use Storage Gateway SMB shares  

**Correct Answer**  
C

**Explanation**  
FSx for Windows File Server provides SMB shares integrated with Active Directory.

---

## Question 14
**Question**  
A Python app processes JSON files thousands of times daily. The solution must be scalable with minimal operational overhead.

**Options**  
A. S3 + Lambda + Aurora  
B. EBS + EC2 processing  
C. SQS + ECS containers  
D. S3 + EC2 processing  

**Correct Answer**  
A

**Explanation**  
S3 triggers Lambda to process files and store results in Aurora with minimal management.

---

## Question 15
**Question**  
Accounting records must stay accessible for 1 year, archived for 9 more years, and cannot be deleted by anyone.

**Options**  
A. Store in Glacier with policy denying deletion  
B. Lifecycle to Glacier Deep Archive + S3 Object Lock compliance mode  
C. Intelligent‑Tiering with IAM deny policy  
D. Lifecycle to One Zone‑IA with governance mode  

**Correct Answer**  
B

**Explanation**  
Lifecycle transitions data and Object Lock compliance mode prevents deletion even by root.

---

## Question 16
**Question**  
In Amazon ECS, what is the logical grouping of container instances on which tasks are placed?

**Options**  
A. Cluster  
B. Container  
C. Task definition  
D. EC2 instance  

**Correct Answer**  
A

**Explanation**  
A cluster is the logical grouping of container instances.

---

## Question 17
**Question**  
Scientists must add files to S3 but nobody can modify or delete them for 1 year.

**Options**  
A. Object Lock governance with legal hold  
B. Object Lock compliance mode with 365‑day retention  
C. IAM policy preventing deletion  
D. Lambda function to track hashes  

**Correct Answer**  
B

**Explanation**  
Compliance mode prevents modification or deletion for the retention period.

---

## Question 18
**Question**  
A public web application must be protected against large‑scale DDoS attacks.

**Options**  
A. Enable AWS Shield with Route 53  
B. Enable Amazon Inspector  
C. Enable Amazon GuardDuty  
D. Enable AWS Shield Advanced and assign the ELB  

**Correct Answer**  
D

**Explanation**  
Shield Advanced provides enhanced DDoS protection for ELB and other services.

---

## Question 19
**Question**  
EC2 instances access S3 over the internet but must now use a private route.

**Options**  
A. Move EC2 to private subnets and create an S3 VPC endpoint  
B. Use NAT gateway  
C. Use Direct Connect  
D. Restrict security groups  

**Correct Answer**  
A

**Explanation**  
Gateway VPC endpoints allow private access to S3.

---

## Question 20
**Question**  
A product manager without an AWS account needs read‑only access to a CloudWatch dashboard.

**Options**  
A. Bastion server access  
B. Create IAM user  
C. Share the CloudWatch dashboard using a shareable link  
D. Create IAM user with ViewOnlyAccess  

**Correct Answer**  
C

**Explanation**  
CloudWatch dashboards can be shared via a public shareable link.

---

## Question 21
**Question**  
A solutions architect must select a storage solution for a NoSQL database that requires random I/O reads greater than 100,000 4 KB IOPS. Which EC2 storage option meets this requirement?

**Options**  
A. SSD instance store  
B. EBS optimized instances  
C. High storage instance in RAID 10  
D. EBS Provisioned IOPS  

**Correct Answer**  
D

**Explanation**  
EBS Provisioned IOPS (io1/io2) volumes provide guaranteed high IOPS performance suitable for high‑performance databases.

---

## Question 22
**Question**  
A media company wants to cache confidential media files globally with low latency. Files are stored in S3. What should be used?

**Options**  
A. AWS Global Accelerator  
B. Amazon CloudFront connected to S3  
C. Amazon SQS  
D. AWS DataSync  

**Correct Answer**  
B

**Explanation**  
CloudFront is a CDN that caches S3 content at edge locations globally for faster delivery.

---

## Question 23
**Question**  
A VPC architecture contains public, private, and database subnets across two AZs. Only EC2 instances in private subnets must access the RDS database. What should be configured?

**Options**  
A. New route table excluding public CIDR  
B. Security group allowing inbound traffic from the private subnet security group  
C. Security group denying traffic from public subnet  
D. VPC peering between subnets  

**Correct Answer**  
B

**Explanation**  
Security groups can restrict database access so that only instances with the private subnet security group can connect.

---

## Question 24
**Question**  
A company stores audit documents in S3 and wants protection from accidental deletion.

**Options**  
A. Encrypt with KMS  
B. Enable Versioning and MFA Delete  
C. Lifecycle policy denying delete  
D. Enable MFA on IAM users  

**Correct Answer**  
B

**Explanation**  
Versioning preserves previous object versions and MFA Delete requires MFA authentication for deletion.

---

## Question 25
**Question**  
Which strategies does DynamoDB use to deliver high performance? (Select two)

**Options**  
A. EBS‑optimized instances  
B. Caching instances  
C. Database partitioning across nodes  
D. Read replicas  
E. Data stored on SSDs  

**Correct Answers**  
C, E

**Explanation**  
DynamoDB horizontally partitions data across nodes and stores it on SSDs to provide high throughput and performance.

---

## Question 26
**Question**  
A company runs a containerized web application with PostgreSQL on premises. Operational overhead is high. Which two changes should be made?

**Options**  
A. Use CloudFront  
B. Host application on EC2  
C. Add ElastiCache  
D. Migrate containers to AWS Fargate with ECS  
E. Migrate PostgreSQL to Amazon Aurora  

**Correct Answers**  
D, E

**Explanation**  
Fargate removes infrastructure management and Aurora provides a managed scalable relational database.

---

## Question 27
**Question**  
A company uses API Gateway across multiple accounts and needs protection from SQL injection and XSS attacks with minimal administration.

**Options**  
A. AWS Firewall Manager with centralized AWS WAF rules  
B. AWS Shield with web ACL  
C. AWS Shield in one region  
D. AWS WAF configured individually  

**Correct Answer**  
A

**Explanation**  
Firewall Manager centrally manages WAF rules across multiple AWS accounts.

---

## Question 28
**Question**  
Developers need scalable key management for encryption with minimal operational overhead.

**Options**  
A. Use MFA  
B. Use AWS KMS  
C. Use AWS Certificate Manager  
D. Restrict IAM users  

**Correct Answer**  
B

**Explanation**  
AWS KMS provides managed encryption key creation, storage, and rotation.

---

## Question 29
**Question**  
A company runs HPC workloads generating large datasets and storing them long‑term in S3. Which solution provides high‑performance file system access?

**Options**  
A. FSx for Windows + S3  
B. FSx for Lustre + S3  
C. Glacier + EBS  
D. S3 + EBS gp2  

**Correct Answer**  
B

**Explanation**  
FSx for Lustre integrates with S3 and provides high‑performance file systems suitable for HPC workloads.

---

## Question 30
**Question**  
An RDS MySQL database with 2 TB gp2 storage experiences slow inserts. What should be done?

**Options**  
A. Enable Multi‑AZ replicas  
B. Change storage to Provisioned IOPS SSD  
C. Use memory optimized instance  
D. Use burstable instance  

**Correct Answer**  
B

**Explanation**  
Provisioned IOPS provides consistent disk performance for heavy database workloads.

---

## Question 31
**Question**  
A solutions architect cannot enable lifecycle policies on an S3 bucket. What might be the reason?

**Options**  
A. Versioning not enabled  
B. Versioning enabled  
C. Bucket type incorrect  
D. Bucket corrupted  

**Correct Answer**  
A

**Explanation**  
Lifecycle policies may require versioning to be enabled depending on lifecycle configuration requirements.

---

## Question 32
**Question**  
Which snapshot strategy provides lowest cost while allowing full EBS restore?

**Options**  
A. Maintain original snapshot and latest incremental snapshot  
B. Archive to Glacier  
C. Overwrite snapshots  
D. Maintain single snapshot  

**Correct Answer**  
A

**Explanation**  
EBS snapshots are incremental, so maintaining the first and latest snapshots provides efficient recovery.

---

## Question 33
**Question**  
Which is NOT a benefit of multipart uploads to Amazon S3?

**Options**  
A. More secure than normal upload  
B. Begin upload before final size known  
C. Pause and resume uploads  
D. Improved throughput  

**Correct Answer**  
A

**Explanation**  
Multipart upload improves throughput and reliability but does not increase security.

---

## Question 34
**Question**  
Which services are required for EC2 Auto Scaling? (Choose three)

**Options**  
A. SQS  
B. CloudWatch  
C. SNS  
D. ELB  
E. EC2  

**Correct Answers**  
B, D, E

**Explanation**  
Auto Scaling relies on EC2 instances, CloudWatch metrics, and often Elastic Load Balancing.

---

## Question 35
**Question**  
A static S3 website must reduce latency globally in the most cost‑effective way.

**Options**  
A. AWS Global Accelerator  
B. Amazon CloudFront in front of S3  
C. S3 Transfer Acceleration  
D. Replicate S3 buckets globally  

**Correct Answer**  
B

**Explanation**  
CloudFront caches content at edge locations globally.

---

## Question 36
**Question**  
A stateless container application must minimize cost and tolerate interruptions.

**Options**  
A. On‑Demand EC2 Auto Scaling  
B. On‑Demand EKS nodes  
C. Spot Instances in EKS managed node group  
D. Spot Instances in EC2 Auto Scaling  

**Correct Answer**  
C

**Explanation**  
Spot Instances provide discounted compute and are suitable for stateless workloads.

---

## Question 37
**Question**  
Backup files are accessed for 1 month and then rarely but must be kept indefinitely.

**Options**  
A. Move to One Zone‑IA  
B. Intelligent‑Tiering  
C. Lifecycle to Glacier Deep Archive after 1 month  
D. Lifecycle to Standard‑IA  

**Correct Answer**  
C

**Explanation**  
Glacier Deep Archive provides the lowest long‑term storage cost.

---

## Question 38
**Question**  
A JavaScript script hosted in S3 must be accessed by websites from other domains.

**Options**  
A. Enable versioning  
B. Use signed URL  
C. Public execute privileges  
D. Enable CORS  

**Correct Answer**  
D

**Explanation**  
CORS allows cross‑domain resource access in browsers.

---

## Question 39
**Question**  
EC2 instances access S3 via a NAT gateway causing transfer costs. What is the most cost‑effective solution?

**Options**  
A. NAT instance  
B. NAT gateway per AZ  
C. Dedicated host  
D. Gateway VPC endpoint for S3  

**Correct Answer**  
D

**Explanation**  
Gateway endpoints provide private S3 access without NAT or internet charges.

---

## Question 40
**Question**  
A static corporate website must be scalable and secure with minimal operations. (Choose two)

**Options**  
A. EC2 Auto Scaling  
B. AWS WAF  
C. CloudFront  
D. AWS Lambda  
E. S3 static website hosting  

**Correct Answers**  
C, E

**Explanation**  
S3 hosts static sites while CloudFront provides CDN and HTTPS support.

---

## Question 41
**Question**  
Users upload files to S3 which must be processed immediately and stored in JSON format.

**Options**  
A. EventBridge + Kinesis + Lambda  
B. EMR  
C. S3 → SQS → EC2  
D. S3 → SQS → Lambda → DynamoDB  

**Correct Answer**  
D

**Explanation**  
S3 event notifications trigger SQS messages which Lambda processes and stores results.

---

## Question 42
**Question**  
A company needs highly available Windows file shares on AWS.

**Options**  
A. Use S3 with IAM  
B. Use S3 File Gateway  
C. Use FSx for Windows File Server Multi‑AZ  
D. Use EFS  

**Correct Answer**  
C

**Explanation**  
FSx for Windows provides managed SMB shares with Active Directory support.

---

## Question 43
**Question**  
Aurora performance drops during monthly reports due to high read IOPS.

**Options**  
A. Run reports on Aurora Replica  
B. Increase instance size  
C. Increase IOPS  
D. Use Redshift  

**Correct Answer**  
A

**Explanation**  
Aurora replicas offload read workloads.

---

## Question 44
**Question**  
An application stores DB credentials locally. The company wants to reduce credential management overhead.

**Options**  
A. AWS Secrets Manager with automatic rotation  
B. Store credentials in S3  
C. Store credentials in encrypted EBS  
D. Systems Manager Parameter Store rotation  

**Correct Answer**  
A

**Explanation**  
Secrets Manager securely stores credentials and supports automatic rotation.

---

## Question 45
**Question**  
An unencrypted RDS database must be encrypted going forward.

**Options**  
A. Encrypt EBS volume  
B. Copy snapshot and encrypt  
C. Encrypt snapshot copy and restore new DB instance  
D. Copy snapshots to S3  

**Correct Answer**  
C

**Explanation**  
RDS encryption must be enabled at creation. Restoring from an encrypted snapshot creates an encrypted DB.

---

## Question 46
**Question**  
What is AWS billing policy for Elastic Beanstalk?

**Options**  
A. Pay only for underlying AWS resources  
B. Pay if resources are in same AZ  
C. Not applicable  
D. Yearly fee  

**Correct Answer**  
A

**Explanation**  
Elastic Beanstalk itself is free; charges apply only for underlying services like EC2 or RDS.

---

## Question 47
**Question**  
How can a company protect S3 objects from accidental deletion? (Choose two)

**Options**  
A. Enable versioning  
B. Lifecycle policy  
C. Bucket policy  
D. Default encryption  
E. Enable MFA Delete  

**Correct Answers**  
A, E

**Explanation**  
Versioning preserves object history and MFA Delete prevents accidental removal.

---

## Question 48
**Question**  
A message processing system using ActiveMQ on EC2 must become highly available.

**Options**  
A. Duplicate EC2 servers  
B. Use Amazon MQ with active/standby brokers + Auto Scaling consumers + RDS Multi‑AZ  
C. Amazon MQ with extra EC2  
D. Amazon MQ + RDS Multi‑AZ only  

**Correct Answer**  
B

**Explanation**  
Amazon MQ provides managed ActiveMQ brokers with HA while RDS Multi‑AZ provides database availability.

---

## Question 49
**Question**  
What is the most cost‑effective method to host a static website?

**Options**  
A. Amazon S3  
B. ALB + Lambda  
C. EC2 web server  
D. AWS Fargate  

**Correct Answer**  
A

**Explanation**  
S3 static website hosting provides low‑cost hosting without servers.

---

## Question 50
**Question**  
A company must reduce false CloudWatch alarms when CPU and disk IOPS are both high.

**Options**  
A. Composite alarms  
B. CloudWatch Synthetics  
C. Single metric alarms  
D. CloudWatch dashboards  

**Correct Answer**  
A

**Explanation**  
Composite alarms combine multiple conditions before triggering.

---

## Question 51
**Question**  
Files in S3 must only be accessible through CloudFront and not directly via S3 URL.

**Options**  
A. Bucket policies  
B. Origin Access Identity  
C. CloudFront principal policy  
D. IAM user  

**Correct Answer**  
B

**Explanation**  
OAI allows CloudFront to access S3 privately.

---

## Question 52
**Question**  
A company must ensure S3 objects remain unchanged indefinitely until legal hold is removed.

**Options**  
A. Glacier Vault Lock  
B. CloudTrail monitoring  
C. Object Lock with long retention  
D. Object Lock with legal hold  

**Correct Answer**  
D

**Explanation**  
Legal hold prevents modification or deletion until removed.

---

## Question 53
**Question**  
What is the name of additional network interfaces attached to EC2 instances?

**Options**  
A. Elastic Network Interface  
B. Network ACL  
C. AWS Elastic Interface  
D. Elastic IP  

**Correct Answer**  
A

**Explanation**  
ENIs provide additional network interfaces within a VPC.

---

## Question 54
**Question**  
Applications running on EC2 store critical data in memory that must persist after stopping for two weeks.

**Options**  
A. Restart in same AZ  
B. Store in instance store  
C. Snapshot instance  
D. Use EC2 hibernation  

**Correct Answer**  
D

**Explanation**  
Hibernation saves RAM contents to the root EBS volume.

---

## Question 55
**Question**  
SSL processing on EC2 instances is causing performance issues.

**Options**  
A. Proxy EC2 instance  
B. Import certificate to ACM and use ALB HTTPS listener  
C. Store certificate in S3  
D. Install ACM certificate on each instance  

**Correct Answer**  
B

**Explanation**  
ALB can offload SSL termination.

---

## Question 56
**Question**  
A web application stores 900 TB of text documents and must scale cost‑effectively.

**Options**  
A. OpenSearch  
B. Amazon S3  
C. Amazon EFS  
D. Amazon EBS  

**Correct Answer**  
B

**Explanation**  
S3 offers highly scalable object storage at low cost.

---

## Question 57
**Question**  
An RDS MySQL database must separate read and write traffic.

**Options**  
A. Multi‑AZ  
B. Read replicas with reduced resources  
C. Multi‑AZ secondary reads  
D. Read replicas with same resources  

**Correct Answer**  
D

**Explanation**  
Read replicas distribute read workloads without impacting the primary DB.

---

## Question 58
**Question**  
An application receives traffic bursts daily but EC2 instances need 1 minute warm‑up.

**Options**  
A. Auto Scaling step scaling with instance warm‑up  
B. CloudFront  
C. Network Load Balancer slow start  
D. ElastiCache  

**Correct Answer**  
A

**Explanation**  
Warm‑up settings prevent scaling decisions before instances are ready.

---

## Question 59
**Question**  
A reporting script slows down an RDS database used for development.

**Options**  
A. ElastiCache  
B. Manual exports  
C. Multi‑AZ  
D. Read replica for reporting  

**Correct Answer**  
D

**Explanation**  
Reporting queries should run on read replicas to avoid impacting the primary DB.

---

## Question 60
**Question**  
Administrators need secure remote access to EC2 instances with minimal operational overhead.

**Options**  
A. EC2 serial console  
B. Site‑to‑site VPN + SSH  
C. IAM roles + Systems Manager Session Manager  
D. Bastion host  

**Correct Answer**  
C

**Explanation**  
Session Manager enables secure access without opening SSH ports.

---

## Question 61
**Question**  
Reserved Instances handle most workload but extra capacity is required monthly for a job that cannot be interrupted.

**Options**  
A. On‑Demand instances during high demand  
B. Spot instances  
C. Larger reserved instances  
D. Additional reserved instances  

**Correct Answer**  
A

**Explanation**  
On‑Demand instances provide temporary reliable capacity without interruption risk.

---

## Question 62
**Question**  
A batch processing job is stateless and can be interrupted.

**Options**  
A. On‑Demand instances  
B. Lambda  
C. Reserved instances  
D. Spot instances  

**Correct Answer**  
D

**Explanation**  
Spot instances offer significant cost savings for interruptible workloads.

---

## Question 63
**Question**  
An Auto Scaling group must maintain CPU utilization around 40%.

**Options**  
A. Simple scaling  
B. Scheduled scaling  
C. Target tracking scaling policy  
D. Lambda function  

**Correct Answer**  
C

**Explanation**  
Target tracking automatically adjusts capacity to maintain a specific metric value.

---

## Question 64
**Question**  
If you launch an instance into a VPC with instance tenancy set to dedicated, what happens?

**Options**  
A. Dedicated instance  
B. Spot instance  
C. EC2 instance  
D. New instance  

**Correct Answer**  
A

**Explanation**  
Instances launched into a VPC with dedicated tenancy run on dedicated hardware.

---

## Question 65
**Question**  
An application generates files from tens of GB to hundreds of TB and requires a standard file system structure with automatic scaling.

**Options**  
A. EKS with EBS  
B. EC2 Auto Scaling with EBS  
C. EC2 Auto Scaling with EFS  
D. ECS with S3  

**Correct Answer**  
C

**Explanation**  
Amazon EFS provides a scalable, shared file system accessible by multiple EC2 instances.
