# AWS SAA Complete Practice Questions

## Question 1

Organizers for a global event want to put daily reports online as static HTML pages. The pages are expected to generate millions of views from users around the world. The files are stored in an Amazon S3 bucket. A solutions architect has been asked to design an efficient and effective solution. Which action should the solutions architect take to accomplish this?

### Options

- __Use Amazon CloudFront with the S3 bucket as its origin.__
- Generate presigned URLs for the files.
- Use the geoproximity feature of Amazon Route 53.
- Use cross-Region replication to all Regions.

### Correct Answer

Use Amazon CloudFront with the S3 bucket as its origin.

### Explanation

**Exam Tip:** Global static content + S3 + millions of users worldwide = use **CloudFront CDN**.

Amazon CloudFront is a content delivery network (CDN) that can be used to deliver content to users around the world with low latency and high availability. CloudFront works by caching content on edge servers that are located close to the users who request the content.

## Question 2

### Explanation

**Exam Tip:** Need centralized permission control across multiple AWS accounts in an organization = **Service Control Policies (SCPs)**.

## Question 3

### Explanation

**Exam Tip:** Question mentions **DDoS protection for AWS resources** → think **AWS Shield (Advanced for stronger protection)**.

## Question 4

### Explanation

**Exam Tip:** Automatic recovery for EC2 system status check failures = **CloudWatch Alarm + EC2 recovery action (stop/start or recover)**.

## Question 5

### Explanation

**Exam Tip:** Restrict web access by **country/geo location** → use **AWS WAF geo match rules**.

## Question 6

### Explanation

**Exam Tip:** API workload with **spiky seasonal traffic + no server management** → **API Gateway + Lambda (serverless)**.

## Question 7

### Explanation

**Exam Tip:** Same static media accessed globally with need to reduce S3 load → **CloudFront caching**.

## Question 8

### Explanation

**Exam Tip:** Web exploit protection (SQL injection/XSS) = **AWS WAF**, Large sophisticated DDoS mitigation = **AWS Shield Advanced**.

## Question 9

### Explanation

**Exam Tip:** Requirement says **synchronous replication + high availability for RDS** → **RDS Multi‑AZ** (not read replica).

## Question 10

### Explanation

**Exam Tip:** Requirements include **minimum server management + rapid scaling** → fully serverless stack: **S3 + API Gateway + Lambda + DynamoDB on-demand**.

## Question 11

### Explanation

**Exam Tip:** Containers needing AWS service access → assign **IAM Role to the ECS Task (taskRoleArn)**.

## Question 12

### Explanation

**Exam Tip:** Shared **Windows file system across EC2 instances** → **Amazon FSx for Windows File Server**.

## Question 13

### Explanation

**Exam Tip:** Highly available DB + minimal management containers → **RDS Multi‑AZ + ECS Fargate**.

## Question 14

### Explanation

**Exam Tip:** Need **SFTP access to S3 with minimal management** → **AWS Transfer Family**.

## Question 15

### Explanation

**Exam Tip:** Managed deployment for web apps with **easy environment swapping for testing** → **Elastic Beanstalk URL swapping**.

## Question 16

### Explanation

**Exam Tip:** Heavy reporting queries impacting production DB → offload reads using **RDS Read Replica**.

## Question 17

### Explanation

**Exam Tip:** Extract text from scanned documents → **Amazon Textract**, then analyze medical info → **Comprehend Medical**.

## Question 18

### Explanation

**Exam Tip:** Prevent lost work during system failure → **decouple with SQS queue**.

## Question 19

### Explanation

**Exam Tip:** Automatically delete DynamoDB data after time period → **DynamoDB TTL attribute**.

## Question 20

### Explanation

**Exam Tip:** Kubernetes workloads migrating to AWS without code changes → **Amazon EKS**, serverless compute → **Fargate**.

## Question 21

### Explanation

**Exam Tip:** Convert speech with multiple speakers to text → **Amazon Transcribe**; query transcripts in S3 → **Athena**.

## Question 22

### Explanation

**Exam Tip:** Secure API Gateway with existing Cognito users → **Cognito User Pool Authorizer**.

## Question 23

### Explanation

**Exam Tip:** Processing delay due to growing SQS queue → scale workers using **Auto Scaling based on queue depth**.

## Question 24

### Explanation

**Exam Tip:** Data lake with centralized governance and fine‑grained permissions → **AWS Lake Formation**.

## Question 25

### Explanation

**Exam Tip:** Distributed session storage for scalable web apps → **ElastiCache (Redis/Memcached)**.

## Question 26

### Explanation

**Exam Tip:** AWS pricing varies by region due to **regional infrastructure and operational costs**.

## Question 27

### Explanation

**Exam Tip:** Cannot connect to database on EC2 → **first check Security Group inbound port rule**.

## Question 28

### Explanation

**Exam Tip:** Key S3 facts: **static website hosting + virtually unlimited objects**.

## Question 29

### Explanation

**Exam Tip:** AWS Single Sign‑On with external identity providers → **SAML 2.0 federation**.

## Question 30

### Explanation

**Exam Tip:** CloudFront cache miss → **request goes to origin and then is cached at edge**.

## Question 31

### Explanation

**Exam Tip:** “WAF sandwich” architecture = **WAF instances in Auto Scaling between two load balancers**.

## Question 32

### Explanation

**Exam Tip:** EC2 communication inside VPC depends mainly on **Security Groups and Network ACL rules**.

## Question 33

### Explanation

**Exam Tip:** Subnets must **fit within VPC CIDR and not overlap**.

## Question 34

### Explanation

**Exam Tip:** Multiple ENIs from different subnets → instance follows **network rules of all attached ENIs**.

## Question 35

### Explanation

**Exam Tip:** Quickly block an IP range across subnets → **Network ACL deny rule**.

## Question 36

### Explanation

**Exam Tip:** Elastic Beanstalk = **PaaS that manages infrastructure automatically for application deployment**.

## Question 37

### Explanation

**Exam Tip:** NAT instance security group should allow **traffic from private subnet**, not public subnet web traffic.

## Question 38

### Explanation

**Exam Tip:** Subnets operate within **one AZ only** and use **NACLs for subnet-level traffic control**.

## Question 39

### Explanation

**Exam Tip:** S3 is object storage; **databases and messaging workloads should not be stored directly in S3**.

## Question 40

### Explanation

**Exam Tip:** Successful S3 upload confirmation = **HTTP 200 response + MD5 checksum match**.

## Question 41

### Explanation

**Exam Tip:** KMS encryption pattern = **data keys encrypt data, master keys encrypt the data keys**.

## Question 42

### Explanation

**Exam Tip:** **RAID 5/6 not recommended for EBS** due to parity overhead and poor performance.

## Question 43

### Explanation

**Exam Tip:** When external service requires **whitelisted IPs from Auto Scaling instances**, route traffic through **NAT with Elastic IPs**.

## Question 44

### Explanation

**Exam Tip:** Route 53 root domain pointing to AWS resource → use **Alias A record** (not CNAME).

## Question 45

### Explanation

**Exam Tip:** For EC2 internal communication → allow traffic using **security group referencing itself**.

## Question 46

### Explanation

**Exam Tip:** Instances backed by **instance store (S3‑backed AMI)** lose root volume data when terminated.

## Question 47

### Explanation

**Exam Tip:** NACLs are **stateless**, so outbound rules must allow return traffic for SSH.

## Question 48

### Explanation

**Exam Tip:** Highest IOPS storage available to EC2 = **instance store SSD**.

## Question 49

### Explanation

**Exam Tip:** Ping failures usually caused by **security group or NACL blocking ICMP**.

## Question 50

### Explanation

**Exam Tip:** NAT instances must have **Source/Destination check disabled**.

## Question 51

### Explanation

**Exam Tip:** Accessing EC2 in private subnet via VPN → allow **SSH from corporate network CIDR**.

## Question 52

### Explanation

**Exam Tip:** RDS Multi‑AZ failover changes underlying IP → applications should **handle reconnect logic**.

## Question 53

### Explanation

**Exam Tip:** Assign custom private IPs only when launching EC2 **inside a VPC**.

## Question 54

### Explanation

**Exam Tip:** NAT instances require **source/destination check disabled** to forward traffic.

## Question 55

### Explanation

**Exam Tip:** Auto Scaling can **add/remove instances**, but cannot **resize instance types or scale RDS replicas automatically**.

## Question 56

### Explanation

**Exam Tip:** Hybrid DNS between on‑prem and VPC → configure **VPC DHCP option set with internal DNS server**.

## Question 57

### Explanation

**Exam Tip:** High‑performance networking on EC2 → **Enhanced Networking using SR‑IOV**.

## Question 58

### Explanation

**Exam Tip:** Handling sudden traffic spikes → **Auto Scaling + caching + protection services (multiple AWS tools)**.

## Question 59

### Explanation

**Exam Tip:** Offload heavy reporting queries from primary DB → **Read Replicas**.

## Question 60

### Explanation

**Exam Tip:** Improve Direct Connect resilience → **secondary DX connection + VPN backup**.

## Question 61

### Explanation

**Exam Tip:** Database connectivity troubleshooting → **check security group port + DB listener configuration**.

## Question 62

### Explanation

**Exam Tip:** Hybrid architecture with on‑prem database → connect AWS resources using **Site‑to‑Site VPN (IPsec)**.

## Question 63

### Explanation

**Exam Tip:** Unknown storage size + durability requirement → **Amazon S3 scalable object storage**.

## Question 64

### Explanation

**Exam Tip:** Key S3 features: **virtually unlimited storage and objects accessible via URL**.