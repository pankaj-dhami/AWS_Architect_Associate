# AWS SAA Complete Practice Questions

## Question 1

A global company is using Amazon API Gateway to design REST APIs for its loyalty club users in the us-east-1 Region and the ap-southeast-2 Region. A solutions architect must design a solution to protect these API Gateway managed REST APIs across multiple accounts from SQL injection and cross-site scripting attacks. Which solution will meet these requirements with the LEAST amount of administrative effort?

### Options

- Set up AWS Shield in one of the Regions. Associate Regional web ACLs with an API stage.
- Set up AWS WAF in both Regions. Associate Regional web ACLs with an API stage.
- __Set up AWS Firewall Manager in both Regions. Centrally configure AWS WAF rules.__
- Set up AWS Shield in bath Regions. Associate Regional web ACLs with an API stage.

### Correct Answer

Set up AWS Firewall Manager in both Regions. Centrally configure AWS WAF rules.

### Explanation

AWS Firewall Manager is a centralized security management service that allows you to manage security policies for your AWS resources across multiple accounts. AWS WAF is a web application firewall that can protect your web applications from common attacks, including SQL injection and cross-site scripting attacks. By using AWS Firewall Manager, you can centrally configure AWS WAF rules and apply them to your API Gateway managed REST APIs across multiple accounts. This will reduce the amount of administrative effort required to manage the security of your APIs.

**Exam Tip:** Centralized multi‑account WAF management → use **AWS Firewall Manager**.

---

## Question 2

A solutions architect wants to design a solution to save costs for Amazon EC2 instances that do not need to run during a 2-week company shutdown. The applications running on the EC2 instances store data in instance memory that must be present when the instances resume operation.Which of the following options is correct ?

### Options

- __Run the applications on EC2 instances enabled for hibernation. Hibernate the instances before the 2- week company shutdown.__
- Note the Availability Zone for each EC2 instance before stopping it. Restart the instances in the same Availability Zones after the 2-week company shutdown.
- Modify the application to store the data on instance store volumes. Reattach the volumes while restarting them.
- Snapshot the EC2 instances before stopping them. Restore the snapshot after restarting the instances.

### Correct Answer

Run the applications on EC2 instances enabled for hibernation. Hibernate the instances before the 2- week company shutdown.

### Explanation

Hibernating EC2 instances save the contents of instance memory to an Amazon Elastic Block Store (Amazon EBS) root volume. When the instances restart, the instance memory contents are reloaded.

**Exam Tip:** When instance **RAM state must persist after stop → EC2 Hibernate**.

---

## Question 3

A company has a dynamic web application hosted on two Amazon EC2 instances. The company has its own SSL certificate, which is on each instance to perform SSL termination. There has been an increase in traffic recently, and the operations team determined that SSL encryption and decryption is causing the compute capacity of the web servers to reach their maximum limit. What should a solutions architect do to increase the application's performance?

### Options

- Create another EC2 instance as a proxy server. Migrate the SSL certificate to the new instance and configure it to direct connections to the existing EC2 instances.
- Create a new SSL certificate using AWS Certificate Manager (ACM). Install the ACM certificate on each instance.
- Create an Amazon S3 bucket Migrate the SSL certificate to the S3 bucket. Configure the EC2 instances to reference the bucket for SSL termination.
- __Import the SSL certificate into AWS Certificate Manager (ACM). Create an Application Load Balancer with an HTTPS listener that uses the SSL certificate from ACM__

### Correct Answer

Import the SSL certificate into AWS Certificate Manager (ACM). Create an Application Load Balancer with an HTTPS listener that uses the SSL certificate from ACM

### Explanation

The best solution is to offload the SSL encryption and decryption from the EC2 instances to an Application Load Balancer using ACM.

**Exam Tip:** Heavy SSL processing on EC2 → **SSL termination at ALB with ACM**.

---

## Question 4

### Explanation

AWS Config tracks configuration changes on your AWS resources, and AWS CloudTrail records a history of API calls made to these resources.

**Exam Tip:**  
Config → **resource configuration history**  
CloudTrail → **API activity logging**

---

## Question 5

### Explanation

S3 Lifecycle transitions data to Glacier Deep Archive and S3 Object Lock compliance mode prevents deletion even by root users.

**Exam Tip:** Regulatory retention where **no user (even root) can delete → S3 Object Lock Compliance Mode**.

---

## Question 6

### Explanation

On‑Demand Capacity Reservations reserve EC2 capacity in specific Availability Zones.

**Exam Tip:** Need **guaranteed EC2 capacity in a specific AZ → On‑Demand Capacity Reservation**.

---

## Question 7

### Explanation

Multipart uploads improve throughput and allow pause/resume but do not improve security.

**Exam Tip:** Multipart upload advantages → **parallel uploads, resume uploads, unknown object size**.

---

## Question 8

### Explanation

Versioning enables recovery and MFA Delete prevents accidental deletion.

**Exam Tip:** Protect S3 from accidental deletion → **Versioning + MFA Delete**.

---

## Question 9

### Explanation

Amazon S3 provides massive scalable object storage with low cost.

**Exam Tip:** Huge datasets (hundreds of TB) with web access → **Amazon S3**.

---

## Question 10

### Explanation

Composite alarms evaluate multiple alarms together to reduce false alerts.

**Exam Tip:** Alarm triggers only when **multiple metrics meet conditions → CloudWatch Composite Alarm**.

---

## Question 11

### Explanation

Read replicas allow read queries without impacting write workloads.

**Exam Tip:** Separate read traffic from write traffic → **RDS Read Replicas**.

---

## Question 12

### Explanation

AWS KMS is a managed service for creating and controlling encryption keys.

**Exam Tip:** Managed encryption key service → **AWS KMS**.

---

## Question 13

### Explanation

A cluster is the logical grouping of container instances in ECS.

**Exam Tip:** ECS architecture → **Cluster = group of container instances**.

---

## Question 14

### Explanation

S3 Object Lock legal hold prevents deletion indefinitely until removed.

**Exam Tip:** Need **indefinite immutability until manually removed → S3 Object Lock Legal Hold**.

---

## Question 15

### Explanation

CloudFront caches content at edge locations worldwide.

**Exam Tip:** Global low‑latency content delivery → **Amazon CloudFront CDN**.

---

## Question 16

### Explanation

Encrypt snapshot copy then restore a new encrypted DB instance.

**Exam Tip:** Cannot encrypt existing RDS → **copy snapshot with encryption then restore**.

---

## Question 17

### Explanation

Running queries on a read replica prevents impact on the primary DB.

**Exam Tip:** Reporting workloads affecting DB performance → **use Read Replica**.

---

## Question 18

### Explanation

Aurora replicas offload read‑heavy reporting tasks.

**Exam Tip:** Heavy read/report workload on Aurora → **Aurora Replica**.

---

## Question 19

### Explanation

Fargate removes server management and Aurora provides managed scalable database.

**Exam Tip:** Reduce infrastructure management → **Fargate + Aurora**.

---

## Question 20

### Explanation

Instances launched in a dedicated tenancy VPC automatically become dedicated instances.

**Exam Tip:** VPC tenancy = dedicated → **all instances become Dedicated Instances**.

---

## Question 21

### Explanation

Provisioned IOPS provides consistent high‑performance disk operations.

**Exam Tip:** Databases requiring **extremely high IOPS → EBS Provisioned IOPS**.

---

## Question 22

### Explanation

CORS allows browser scripts from different domains to access S3 resources.

**Exam Tip:** Browser accessing S3 from different domain → **Enable CORS**.

---

## Question 23

### Explanation

Security groups can reference other security groups to control access.

**Exam Tip:** Allow DB access only from specific instances → **Security group referencing another SG**.

---

## Question 24

### Explanation

Elastic Beanstalk itself is free; you pay for the underlying AWS resources.

**Exam Tip:** Elastic Beanstalk pricing → **pay only for underlying resources**.

---

## Question 25

### Explanation

CloudFront caches S3 website content globally.

**Exam Tip:** Reduce global latency for S3 website → **CloudFront distribution**.

---

## Question 26

### Explanation

Lifecycle rules are closely tied with versioning management behavior.

**Exam Tip:** Lifecycle policies are often tested with **versioning configuration**.

---

## Question 27

### Explanation

Spot Instances provide discounted compute for interruptible workloads.

**Exam Tip:** Stateless, interruptible workloads → **EC2 Spot Instances**.

---

## Question 28

### Explanation

Managed MQ, Auto Scaling consumers, and RDS Multi‑AZ provide high availability.

**Exam Tip:** Highly available messaging architecture → **Amazon MQ + Auto Scaling + RDS Multi‑AZ**.

---

## Question 29

### Explanation

Event‑driven architecture processes files immediately after upload.

**Exam Tip:** Real‑time file processing → **S3 Event → SQS → Lambda**.

---

## Question 30

### Explanation

Elastic Network Interfaces can move between instances to preserve private IP.

**Exam Tip:** Fast failover using same private IP → **Move ENI between instances**.

---

## Question 31

### Explanation

Provisioned IOPS SSD ensures consistent disk performance.

**Exam Tip:** RDS storage bottleneck → **Provisioned IOPS SSD**.

---

## Question 32

### Explanation

Amazon EFS provides shared scalable file storage.

**Exam Tip:** Shared file system across many EC2 instances → **Amazon EFS**.

---

## Question 33

### Explanation

EBS snapshots are incremental.

**Exam Tip:** Snapshots are incremental → **keep base snapshot + latest incremental**.

---

## Question 34

### Explanation

Aurora replicas allow scaling read operations.

**Exam Tip:** Separate read/write workload in Aurora → **Aurora Replica**.

---

## Question 35

### Explanation

Fargate runs containers without managing servers.

**Exam Tip:** Containers with minimal ops → **AWS Fargate**.

---

## Question 36

### Explanation

FSx for Windows provides managed Windows file shares.

**Exam Tip:** Windows SMB + Active Directory → **Amazon FSx for Windows File Server**.

---

## Question 37

### Explanation

Direct Connect provides a dedicated private network link.

**Exam Tip:** Dedicated high‑bandwidth private AWS connection → **Direct Connect**.

---

## Question 38

### Explanation

S3 static hosting with CloudFront reduces operational overhead.

**Exam Tip:** Static site with lowest ops overhead → **S3 + CloudFront**.

---

## Question 39

### Explanation

Shield Advanced provides protection against large‑scale DDoS attacks.

**Exam Tip:** Enterprise DDoS protection → **AWS Shield Advanced**.

---

## Question 40

### Explanation

Lambda automatically processes objects uploaded to S3.

**Exam Tip:** Event‑driven serverless processing → **S3 trigger + Lambda**.

---

## Question 41

### Explanation

Compliance mode prevents object deletion by any user.

**Exam Tip:** Strict WORM requirement → **S3 Object Lock Compliance Mode**.

---

## Question 42

### Explanation

Gateway VPC endpoints allow private connectivity to S3.

**Exam Tip:** Access S3 privately from VPC → **Gateway VPC Endpoint**.

---

## Question 43

### Explanation

Network ACLs control traffic at subnet level.

**Exam Tip:** NACLs operate at the **Subnet level**.

---

## Question 44

### Explanation

FSx for Windows integrates with Active Directory.

**Exam Tip:** Windows file shares + AD integration → **FSx for Windows**.

---

## Question 45

### Explanation

API Gateway custom domains require ACM certificate in same region.

**Exam Tip:** Custom domain for API Gateway → **ACM certificate + Route53**.

---

## Question 46

### Explanation

Target tracking scaling maintains a specific metric level.

**Exam Tip:** Maintain fixed CPU target → **Target Tracking Auto Scaling**.

---

## Question 47

### Explanation

DynamoDB achieves performance via partitioning and SSD storage.

**Exam Tip:** DynamoDB performance → **partitioning + SSD storage**.

---

## Question 48

### Explanation

Versioning keeps historical copies and MFA Delete prevents accidental removal.

**Exam Tip:** Protect S3 from accidental deletion → **Versioning + MFA Delete**.

---

## Question 49

### Explanation

Serverless architecture scales automatically with demand.

**Exam Tip:** Image processing architecture → **Lambda + S3 + DynamoDB**.

---

## Question 50

### Explanation

Secrets Manager stores credentials securely and rotates them automatically.

**Exam Tip:** Centralized credential storage with rotation → **AWS Secrets Manager**.

---

## Question 51

### Explanation

CloudWatch dashboards can be shared externally via secure links.

**Exam Tip:** External dashboard access → **CloudWatch dashboard sharing link**.

---

## Question 52

### Explanation

Session Manager enables secure instance access without opening SSH ports.

**Exam Tip:** Secure EC2 administration without bastion → **Systems Manager Session Manager**.

---

## Question 53

### Explanation

Elastic Network Interfaces provide additional network interfaces.

**Exam Tip:** Extra EC2 network interface → **Elastic Network Interface (ENI)**.

---

## Question 54

### Explanation

FSx for Lustre integrates high‑performance file systems with S3.

**Exam Tip:** HPC workloads with shared high‑performance storage → **FSx for Lustre + S3**.

---

## Question 55

### Explanation

S3 Intelligent‑Tiering automatically moves objects between tiers based on usage.

**Exam Tip:** **Unpredictable access pattern → S3 Intelligent‑Tiering**.

---

## Question 56

### Explanation

Origin Access Identity allows CloudFront to access S3 privately.

**Exam Tip:** Prevent direct S3 access while using CloudFront → **Origin Access Identity (OAI)**.

---

## Question 57

### Explanation

Lifecycle transitions archive objects after they are no longer frequently accessed.

**Exam Tip:** Long‑term rarely accessed data → **Glacier Deep Archive**.

---

## Question 58

### Explanation

S3 provides the cheapest hosting for static websites.

**Exam Tip:** Cheapest static website hosting → **Amazon S3**.

---

## Question 59

### Explanation

Instance warm‑up prevents premature scaling decisions.

**Exam Tip:** Applications needing startup time → **Auto Scaling warm‑up configuration**.

---

## Question 60

### Explanation

Gateway endpoints route S3 traffic privately inside a VPC.

**Exam Tip:** Private S3 access from VPC → **S3 Gateway Endpoint**.

---

## Question 61

### Explanation

Spot instances minimize cost for stateless container workloads.

**Exam Tip:** Stateless containers with lowest compute cost → **Spot Instances**.

---

## Question 62

### Explanation

On‑Demand instances guarantee uninterrupted execution.

**Exam Tip:** Jobs that **cannot be interrupted → On‑Demand Instances**.

---

## Question 63

### Explanation

Gateway VPC endpoints remove NAT data transfer charges to S3.

**Exam Tip:** Avoid NAT data transfer to S3 → **Gateway VPC Endpoint**.

---

## Question 64

### Explanation

Auto Scaling uses EC2 instances, ELB, and CloudWatch metrics.

**Exam Tip:** Auto Scaling core services → **EC2 + ELB + CloudWatch**.

---

## Question 65

### Explanation

ARNs uniquely identify AWS resources across services.

**Exam Tip:** Global AWS resource identifier → **ARN (Amazon Resource Name)**.