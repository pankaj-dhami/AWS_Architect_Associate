# AWS Certified Solutions Architect Associate - Practice Test 3

## Question 1
**Question:**  
Organizers for a global event want to put daily reports online as static HTML pages. The pages are expected to generate millions of views from users around the world. The files are stored in an Amazon S3 bucket. A solutions architect has been asked to design an efficient and effective solution. Which action should the solutions architect take to accomplish this?

**Options:**
- Use Amazon CloudFront with the S3 bucket as its origin.
- Generate presigned URLs for the files.
- Use the geoproximity feature of Amazon Route 53.
- Use cross-Region replication to all Regions.

**Correct Answer:**  
Use Amazon CloudFront with the S3 bucket as its origin.

**Explanation:**  
Amazon CloudFront is a content delivery network (CDN) that delivers content globally with low latency and high availability by caching content on edge locations close to users. Associating the S3 bucket with a CloudFront distribution allows static HTML pages to be served quickly to users worldwide while reducing load on the origin.

---

## Question 2
**Question:**  
A security team wants to limit access to specific services or actions in all of the team’s AWS accounts. All accounts belong to a large organization in AWS Organizations. The solution must be scalable and there must be a single point where permissions can be maintained. What should a solutions architect do to accomplish this?

**Options:**
- Create a service control policy in the root organizational unit to deny access to the services or actions.
- Create an ACL to provide access to the services or actions.
- Create a security group to allow accounts and attach it to user groups.
- Create cross-account roles in each account to deny access to the services or actions.

**Correct Answer:**  
Create a service control policy in the root organizational unit to deny access to the services or actions.

**Explanation:**  
Service Control Policies (SCPs) in AWS Organizations allow centralized control over permissions across accounts. Applying an SCP at the root or organizational unit ensures consistent restrictions across all member accounts.

---

## Question 3
**Question:**  
A company is concerned about the security of its public web application due to recent web attacks. The application uses an Application Load Balancer (ALB). A solutions architect must reduce the risk of DDoS attacks against the application. Which option is correct?

**Options:**
- Configure Amazon GuardDuty to monitor the ALB.
- Enable AWS Shield Advanced to prevent attacks.
- Configure Amazon Macie to prevent attacks.
- Add an Amazon Inspector agent to the ALB.

**Correct Answer:**  
Enable AWS Shield Advanced to prevent attacks.

**Explanation:**  
AWS Shield Advanced provides managed DDoS protection for applications running on AWS. It protects against volumetric, protocol, and application-layer attacks and integrates with services such as ALB.

---

## Question 4
**Question:**  
One of your instances is reporting an unhealthy system status check. However, this is not something you should have to monitor and repair on your own. How might you automate the repair of the system status check failure in an AWS environment?

**Options:**
- Write a script that queries the EC2 API for each instance status check.
- Implement a third party monitoring tool such as Nagios.
- Create CloudWatch metrics that stop and then start the instance based off of status check alarms.
- Write a script that periodically shuts down and starts instances.

**Correct Answer:**  
Create CloudWatch metrics that stop and then start the instance based off of status check alarms.

**Explanation:**  
Amazon CloudWatch alarms can monitor EC2 status checks and trigger automated recovery actions such as rebooting or stopping/starting instances when failures occur.

---

## Question 5
**Question:**  
A news company web application is running on Amazon EC2 instances behind an Application Load Balancer. The company now requires that the application be accessed from only one specific country. Which configuration will meet this requirement?

**Options:**
- Configure the network ACL for the subnet that contains the EC2 instances.
- Configure the security group for the EC2 instances.
- Configure the security group on the Application Load Balancer.
- Configure AWS WAF on the Application Load Balancer in a VPC.

**Correct Answer:**  
Configure AWS WAF on the Application Load Balancer in a VPC.

**Explanation:**  
AWS WAF supports geographic match rules, allowing access to be restricted based on country.

---

## Question 6
**Question:**  
A company provides an API to automate tax computations. During the holiday season, inquiries spike and cause slow response times. The solution must be scalable and elastic.

**Options:**
- API Gateway connected to EC2 instance.
- Application Load Balancer with EC2 instances.
- API hosted directly on EC2.
- API Gateway with AWS Lambda for tax computations.

**Correct Answer:**  
Design a REST API using Amazon API Gateway that accepts item names and passes them to AWS Lambda.

**Explanation:**  
API Gateway combined with AWS Lambda provides a fully serverless architecture that automatically scales based on request volume.

---

## Question 7
**Question:**  
A gaming company hosts a browser-based application with videos and images stored in Amazon S3. Millions of users globally access this content. The company wants to reduce load on the origin cost-effectively.

**Options:**
- Amazon ElastiCache for Memcached
- Amazon CloudFront distribution in front of S3
- Amazon ElastiCache for Redis
- AWS Global Accelerator

**Correct Answer:**  
Deploy an Amazon CloudFront web distribution in front of the S3 bucket.

**Explanation:**  
CloudFront caches content at edge locations around the world, reducing latency and load on the S3 origin.

---

## Question 8
**Question:**  
A company wants to protect its API platform against SQL injection and large DDoS attacks. Which combination provides the most protection? (Choose two)

**Options:**
- AWS Shield Standard with API Gateway
- Amazon GuardDuty with AWS Shield Standard
- AWS WAF to protect the NLB
- AWS WAF to protect Amazon API Gateway
- AWS Shield Advanced with the NLB

**Correct Answers:**
- Use AWS WAF to protect Amazon API Gateway.
- Use AWS Shield Advanced with the NLB.

**Explanation:**  
AWS WAF protects against application-layer attacks such as SQL injection, while AWS Shield Advanced protects against sophisticated DDoS attacks.

---

## Question 9
**Question:**  
A company wants a reliable MySQL database on AWS that minimizes data loss and stores each transaction on at least two nodes.

**Options:**
- EC2 MySQL with Lambda replication
- RDS MySQL read replica across Regions
- RDS MySQL Multi-AZ deployment
- RDS replication to three nodes

**Correct Answer:**  
Create an Amazon RDS MySQL DB instance with Multi-AZ enabled.

**Explanation:**  
Multi-AZ deployments synchronously replicate data to a standby instance in another Availability Zone and automatically fail over.

---

## Question 10
**Question:**  
A company is building a dynamic ordering website and wants minimal server maintenance and automatic scaling.

**Options:**
- EC2 + ALB + Aurora
- EC2 + ALB + DynamoDB provisioned
- S3 + API Gateway + Lambda + Aurora
- S3 + API Gateway + Lambda + DynamoDB on-demand + CloudFront

**Correct Answer:**  
Host static content in S3, dynamic content via API Gateway and Lambda, DynamoDB with on-demand capacity, and CloudFront.

**Explanation:**  
This architecture is fully serverless and scales automatically with minimal operational overhead.

---

## Question 11
**Question:**  
An Amazon ECS application must store resized images in S3. How should permissions be granted?

**Options:**
- IAM role assigned as taskRoleArn
- IAM user with S3 permissions
- Security group allowing S3 access
- Update S3 role and relaunch container

**Correct Answer:**  
Create an IAM role with S3 permissions and specify it as taskRoleArn in the ECS task definition.

**Explanation:**  
ECS tasks can assume IAM roles that grant the necessary permissions to access AWS services securely.

---

## Question 12
**Question:**  
A Windows application requires a shared Windows file system accessible by EC2 instances across multiple Availability Zones.

**Options:**
- Amazon EBS
- Amazon EFS
- Amazon FSx for Windows File Server
- AWS Storage Gateway

**Correct Answer:**  
Configure Amazon FSx for Windows File Server.

**Explanation:**  
Amazon FSx provides native Windows file system support and SMB protocol compatibility.

---

## Question 13
**Question:**  
An ecommerce application requires high availability with minimal manual management. (Choose two)

**Options:**
- RDS Multi-AZ
- ECS with Fargate
- ECS with EC2
- EC2 Docker cluster
- RDS read replicas

**Correct Answers:**
- Amazon RDS DB instance in Multi-AZ mode
- Amazon ECS cluster with Fargate launch type

**Explanation:**  
These services provide automatic scaling, high availability, and minimal infrastructure management.

---

## Question 14
**Question:**  
A partner must upload files via SFTP to an S3 data lake with minimal operational overhead.

**Options:**
- EC2 SFTP servers behind NLB
- AWS Transfer Family with SFTP endpoint
- EC2 with VPN upload
- S3 File Gateway

**Correct Answer:**  
Use AWS Transfer Family with an SFTP-enabled server and S3 destination.

**Explanation:**  
AWS Transfer Family is a fully managed service supporting SFTP, FTPS, and FTP for direct integration with S3.

---

## Question 15
**Question:**  
A company migrating Java and PHP applications to AWS requires frequent feature testing with minimal operational overhead.

**Options:**
- Containerized app on EC2
- EC2 with Auto Scaling and ALB
- Elastic Beanstalk with URL swapping
- Static site with S3 and Lambda

**Correct Answer:**  
Deploy the web application to AWS Elastic Beanstalk and use URL swapping for testing.

**Explanation:**  
Elastic Beanstalk simplifies deployment and environment management while supporting blue/green deployments.

---

## Question 16
**Question:**  
Reporting queries on an RDS MySQL database cause timeouts during order processing.

**Options:**
- Schedule queries at night
- Use read replica for both apps
- Migrate to DynamoDB
- Move reporting queries to a read replica

**Correct Answer:**  
Create a read replica and move reporting queries to it.

**Explanation:**  
Read replicas offload read-heavy workloads from the primary database instance.

---

## Question 17
**Question:**  
A hospital scans documents and needs to extract medical information and allow SQL queries. (Choose two)

**Correct Answers:**
- Use AWS Lambda with Amazon Textract and Amazon Comprehend Medical.
- Store results in Amazon S3 and query using Amazon Athena.

**Explanation:**  
Textract extracts text from documents and Comprehend Medical identifies medical entities. Athena enables SQL queries on S3 data.

---

## Question 18
**Question:**  
A company wants order processing to continue automatically if systems fail.

**Options:**
- SNS + Lambda
- Auto Scaling + EventBridge
- Auto Scaling + SQS queue
- ALB endpoint processing

**Correct Answer:**  
Move EC2 instances to an Auto Scaling group and use an SQS queue for order messages.

**Explanation:**  
SQS decouples producers and consumers, ensuring orders are processed even if instances fail.

---

## Question 19
**Question:**  
A DynamoDB table stores data but only the last 30 days are needed.

**Options:**
- Add TTL attribute
- Redeploy CloudFormation every 30 days
- Lambda delete old items
- EC2 monitoring app

**Correct Answer:**  
Add a TTL attribute (timestamp + 30 days).

**Explanation:**  
DynamoDB TTL automatically deletes expired items without extra infrastructure.

---

## Question 20
**Question:**  
A company runs Kubernetes with MongoDB on-premises and wants to migrate to AWS without code changes.

**Options:**
- ECS + EC2 + MongoDB
- EKS + Fargate + DocumentDB
- ECS + Fargate + DynamoDB
- EKS + EC2 + DynamoDB

**Correct Answer:**  
Use Amazon EKS with AWS Fargate and Amazon DocumentDB.

**Explanation:**  
EKS maintains Kubernetes compatibility while DocumentDB provides MongoDB compatibility.

---

## Question 21
**Question:**  
A call center solution requires speaker recognition and transcript analysis.

**Options:**
- Rekognition + ML
- Transcribe + Athena
- Rekognition + Textract
- Translate + Redshift

**Correct Answer:**  
Use Amazon Transcribe for speaker recognition and Amazon Athena for analysis.

**Explanation:**  
Transcribe identifies multiple speakers and generates transcripts suitable for querying.

---

## Question 22
**Question:**  
An application uses Amazon Cognito for authentication and API Gateway for APIs. Access control should be managed with minimal development effort.

**Options:**
- Lambda authorizer
- Email validation via Lambda
- Cognito user pool authorizer
- API key validation

**Correct Answer:**  
Configure an Amazon Cognito user pool authorizer in API Gateway.

**Explanation:**  
This allows API Gateway to automatically validate Cognito tokens.

---

## Question 23
**Question:**  
Meeting invitations are delayed as customer demand increases.

**Options:**
- Add DynamoDB DAX
- Auto Scaling group based on SQS queue depth
- Add API Gateway
- Add CloudFront

**Correct Answer:**  
Add an Auto Scaling group and scale based on SQS queue depth.

**Explanation:**  
Scaling workers based on queue length improves processing throughput.

---

## Question 24
**Question:**  
A retail company wants centralized analytics with fine-grained permissions and minimal operational overhead.

**Options:**
- Redshift cluster
- AWS Lake Formation
- Store everything in RDS
- Lambda + Athena + S3 policies

**Correct Answer:**  
Create a data lake using AWS Lake Formation.

**Explanation:**  
Lake Formation simplifies building and managing data lakes with centralized access control.

---

## Question 25
**Question:**  
An application running on EC2 with frequent scaling needs distributed session management.

**Options:**
- AWS STS
- Sticky sessions
- Systems Manager Session Manager
- Amazon ElastiCache

**Correct Answer:**  
Use Amazon ElastiCache.

**Explanation:**  
ElastiCache provides a distributed in-memory store suitable for session data.

---

## Question 26
**Question:**  
Why do S3 storage costs differ between regions?

**Options:**
- It must be a mistake
- AWS charges less where costs are lower
- It balances next bill
- Time zone pricing

**Correct Answer:**  
AWS charges less where its costs are lower.

**Explanation:**  
Pricing varies by region based on infrastructure costs.

---

## Question 27
**Question:**  
Unable to connect to SQL Server on a Windows EC2 instance.

**Options:**
- Check VPC routing
- Check Windows firewall
- Verify security group allows TCP 1433
- Use different user

**Correct Answer:**  
Verify security group allows TCP port 1433 from your IP.

---

## Question 28
**Question:**  
Choose correct S3 statements. (Choose 3)

**Correct Answers:**
- You can serve static websites from S3
- You can have unlimited objects in a bucket
- Reduced Redundancy Storage can be used for lower cost

---

## Question 29
**Question:**  
How do you achieve single sign-on with AWS?

**Options:**
- Not possible
- MFA
- AD and LDAP integration
- Configure SAML 2.0
- IAM policies

**Correct Answer:**  
Configure SAML 2.0.

---

## Question 30
**Question:**  
What happens if CloudFront content is not at the edge location?

**Options:**
- Request waits
- 404 error
- Routed to next edge
- Retrieved from origin and cached

**Correct Answer:**  
CloudFront retrieves content from the origin and caches it at the edge location.

---

## Question 31
**Question:**  
What is a “WAF sandwich”?

**Correct Answer:**  
The WAF EC2 instances run in an Auto Scaling group placed between two Elastic Load Balancers.

---

## Question 32
**Question:**  
Two EC2 instances in different subnets must communicate. (Choose two)

**Correct Answers:**
- Network ACL allows communication between subnets
- Security groups allow traffic on required ports

---

## Question 33
**Question:**  
VPC CIDR 20.0.0.0/24 with subnets /25 and /25.

**Correct Answer:**  
AWS allows creating the private subnet with CIDR 20.0.0.128/25.

---

## Question 34
**Question:**  
What happens when an instance has ENIs from different subnets?

**Correct Answer:**  
The instance follows rules of both subnets.

---

## Question 35
**Question:**  
Quickly deny traffic from a malicious IP block.

**Correct Answer:**  
Modify Network ACLs for public subnets to deny the IP block.

---

## Question 36
**Question:**  
Characteristics of Elastic Beanstalk (Choose 2)

**Correct Answers:**
- Helps quickly deploy and manage applications in AWS.
- You don’t need to manage the underlying infrastructure.

---

## Question 37
**Question:**  
Which NAT security group rule is unnecessary?

**Correct Answer:**  
Inbound rule allowing Source 20.0.0.0/24 on port 80.

---

## Question 38
**Question:**  
Characteristics of subnets (Choose 2)

**Correct Answers:**
- Network ACLs control traffic entering and exiting subnets.
- Default subnets are assigned /20 blocks.

---

## Question 39
**Question:**  
What data should not be stored in S3?

**Correct Answers:**
- Website database
- Application notifications

---

## Question 40
**Question:**  
How do you know an S3 object upload succeeded?

**Correct Answer:**  
HTTP 200 response code and matching MD5 checksum.

---

## Question 41
**Question:**  
How does AWS KMS work?

**Correct Answer:**  
KMS uses master keys and data keys. Data keys encrypt data, and master keys encrypt the data keys.

---

## Question 42
**Question:**  
Which RAID configuration is not recommended for EBS?

**Correct Answer:**  
RAID 5 and RAID 6.

---

## Question 43
**Question:**  
Payment service requires whitelisted IP addresses.

**Correct Answer:**  
Route requests through NAT instances with Elastic IPs.

---

## Question 44
**Question:**  
How should a DNS zone apex record point to an ELB?

**Correct Answer:**  
Create an A record alias to the load balancer DNS name.

---

## Question 45
**Question:**  
Security group setup for NFS image processing servers.

**Correct Answer:**  
Allow HTTPS to front-end servers and allow internal traffic between instances.

---

## Question 46
**Question:**  
What happens to root volume data when an S3-backed AMI instance is terminated?

**Correct Answer:**  
The data is automatically deleted.

---

## Question 47
**Question:**  
Instance cannot be accessed via SSH due to outbound rules.

**Correct Answer:**  
Modify the outbound network ACL to allow outbound traffic.

---

## Question 48
**Question:**  
Which provides maximum IOPS?

**Correct Answer:**  
Instance-based SSD storage.

---

## Question 49
**Question:**  
Why can’t instance A ping instance B? (Choose 2)

**Correct Answers:**
- Subnet B NACL blocks outbound ICMP
- Security group of instance B blocks inbound ICMP

---

## Question 50
**Question:**  
Private instances cannot access the internet through NAT.

**Correct Answer:**  
Disable Source/Destination Check on the NAT instance.

---

## Question 51
**Question:**  
How should SSH access be configured to reach a private subnet instance over VPN?

**Correct Answer:**  
Allow inbound SSH from the user’s network.

---

## Question 52
**Question:**  
.NET utilities fail during RDS Multi-AZ failover.

**Correct Answer:**  
Flush DNS cache so utilities reconnect to the updated endpoint.

---

## Question 53
**Question:**  
How do you assign predetermined private IP addresses to EC2 instances?

**Correct Answer:**  
Launch the instances in a VPC.

---

## Question 54
**Question:**  
Private instances cannot access internet through NAT.

**Correct Answer:**  
Disable Source/Destination Check on the NAT instance.

---

## Question 55
**Question:**  
What Auto Scaling cannot do? (Choose 2)

**Correct Answers:**
- Add RDS read replicas
- Increase instance size

---

## Question 56
**Question:**  
Hybrid architecture internal DNS configuration (Choose two)

**Correct Answers:**
- Use on-prem DNS with VPC DHCP option set
- Use EC2 DNS server with VPC DHCP option set

---

## Question 57
**Question:**  
How to enable enhanced networking with lower latency?

**Correct Answer:**  
Use Single Root I/O Virtualization (SR-IOV).

---

## Question 58
**Question:**  
What helps respond to sudden web traffic spikes?

**Correct Answer:**  
All of these answers.

---

## Question 59
**Question:**  
Best solution for heavy reporting queries on database.

**Correct Answer:**  
Use Read Replicas.

---

## Question 60
**Question:**  
Improve Direct Connect fault tolerance. (Choose 2)

**Correct Answers:**
- Hardware VPN between VPC-1 and on-premises
- Additional Direct Connect connection in same region

---

## Question 61
**Question:**  
Cannot connect to PostgreSQL on EC2.

**Correct Answer:**  
Allow port 5432 in security groups and ensure PostgreSQL listens on external interface.

---

## Question 62
**Question:**  
Application on AWS must connect to MySQL database in on-premises data center.

**Correct Answer:**  
Connect using an IPsec VPN.

---

## Question 63
**Question:**  
Cost-efficient and scalable storage for audio and transcription files.

**Correct Answer:**  
Store both files in a single Amazon S3 bucket.

---

## Question 64
**Question:**  
Characteristics of Amazon S3 (Choose 2)

**Correct Answers:**
- S3 allows storing virtually unlimited data.
- Objects are directly accessible via a URL.