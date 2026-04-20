# AWS Certified Solutions Architect Associate - Practice Test 1

## Question 1
Question:  
A gaming company is implementing a shared storage solution for a gaming application that is hosted in an on‑premises data center. The company needs the ability to use Lustre clients to access data. The solution must be fully managed.

Options:
A. Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to the file share.  
B. Create an AWS Storage Gateway file gateway. Create a file share that uses the required client protocol. Connect the application server to the file share.  
C. Create an Amazon Elastic File System (Amazon EFS) file system, and configure it to support Lustre. Attach the file system to the origin server. Connect the application server to the file system.  
D. Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

Correct Answer:  
D. Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

---

## Question 2
Question:  
An e‑commerce company runs an e‑commerce application on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 auto‑scaling group across multiple Availability Zones. The auto‑scaling group scales based on CPU utilization metrics. The e‑commerce application stores the transaction data in a MySQL 8.0 database that is hosted on a large EC2 instance. The database's performance degrades quickly as application load increases. The application handles more read requests than write transactions. The company wants a solution that will automatically scale the database to meet the demand of unpredictable read workloads while maintaining high availability.

Options:
A. Use Amazon RDS with a Single‑AZ deployment Configure Amazon RDS to add reader instances in a different Availability Zone.  
B. Use Amazon Redshift with a single node for leader and compute functionality.  
C. Use Amazon ElastiCache for Memcached with EC2 Spot Instances.  
D. Use Amazon Aurora with a Multi‑AZ deployment. Configure Aurora Auto Scaling with Aurora Replicas.

Correct Answer:  
D. Use Amazon Aurora with a Multi‑AZ deployment. Configure Aurora Auto Scaling with Aurora Replicas.

---

## Question 3
Question:  
Which IAM policy condition key should be used if the solution architect wants to check whether the request was sent using SSL?

Options:
A. AWS: agent  
B. AWS: source IP  
C. AWS: secure transport  
D. AWS: secure IP  

Correct Answer:  
C. AWS: secure transport

---

## Question 4
Question:  
If a company wants to build its own payment application, it should take advantage of the richness and flexibility of _____________.

Options:
A. Payoneer Payment Services  
B. EBay Payment service  
C. PayPal Payment service  
D. Amazon AWS FPS  

Correct Answer:  
D. Amazon AWS FPS

---

## Question 5
Question:  
A solutions architect is designing a VPC with public and private subnets. The VPC and subnets use IPv4 CIDR blocks. There is one public subnet and one private subnet in each of three Availability Zones (AZs) for high availability. An internet gateway is used to provide internet access for the public subnets. The private subnets require access to the internet to allow Amazon EC2 instances to download software updates. What should the solutions architect do to enable Internet access for the private subnets?

Options:
A. Create an egress‑only internet gateway on one of the public subnets. Update the route table for the private subnets that forward non‑VPC traffic to the egress‑only Internet gateway.  
B. Create three NAT instances, one for each private subnet in each AZ. Create a private route table for each AZ that forwards non‑VPC traffic to the NAT instance in its AZ.  
C. Create a second internet gateway on one of the private subnets. Update the route table for the private subnets that forward non‑VPC traffic to the private internet gateway.  
D. Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non‑VPC traffic to the NAT gateway in its AZ.

Correct Answer:  
D. Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non‑VPC traffic to the NAT gateway in its AZ.

---

## Question 6
Question:  
A company runs a shopping application that uses Amazon DynamoDB to store customer information. In case of data corruption, a solutions architect needs to design a solution that meets a recovery point objective (RPO) of 15 minutes and a recovery time objective (RTO) of 1 hour. What should the solutions architect recommend to meet these requirements?

Options:
A. Configure DynamoDB point‑in‑time recovery. For RPO recovery, restore to the desired point in time.  
B. Schedule Amazon Elastic Block Store (Amazon EBS) snapshots for the DynamoDB table every 15 minutes. For RPO recovery, restore the DynamoDB table by using the EBS snapshot.  
C. Configure DynamoDB global tables. For RPO recovery, point the application to a different AWS Region.  
D. Export the DynamoDB data to Amazon S3 Glacier on a daily basis. For RPO recovery, import the data from S3 Glacier to DynamoDB.

Correct Answer:  
A. Configure DynamoDB point‑in‑time recovery. For RPO recovery, restore to the desired point in time.

---

## Question 7
Question:  
A IT company performs monthly maintenance on its AWS infrastructure. During these maintenance activities, the company needs to rotate the credentials for its Amazon RDS for MySQL databases across multiple AWS Regions. Which of the following options is correct?

Options:
A. Store the credentials in an Amazon S3 bucket that has server‑side encryption (SSE) enabled. Use Amazon EventBridge (Amazon CloudWatch Events) to invoke an AWS Lambda function to rotate the credentials.  
B. Encrypt the credentials as secrets by using AWS Key Management Service (AWS KMS) multi‑Region customer managed keys. Store the secrets in an Amazon DynamoDB global table. Use an AWS Lambda function to retrieve the secrets from DynamoDB. Use the RDS API to rotate the secrets.  
C. Store the credentials as secrets in AWS Secrets Manager. Use multi‑Region secret replication for the required Regions. Configure Secrets Manager to rotate the secrets on a schedule.  
D. Store the credentials as secrets in AWS Systems Manager by creating a secure string parameter. Use multi‑Region secret replication for the required Regions. Configure Systems Manager to rotate the secrets on a schedule.

Correct Answer:  
C. Store the credentials as secrets in AWS Secrets Manager. Use multi‑Region secret replication for the required Regions. Configure Secrets Manager to rotate the secrets on a schedule.

---

## Question 8
Question:  
An IT company is running a business‑critical web application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances are in an Auto Scaling group. The application uses an Amazon Aurora PostgreSQL database that is deployed in a single Availability Zone. The company wants the application to be highly available with minimum downtime and minimum loss of data. Which of the following options is correct?

Options:
A. Place the EC2 instances in different AWS Regions. Use Amazon Route 53 health checks to redirect traffic. Use Aurora PostgreSQL Cross‑Region Replication.  
B. Configure the Auto Scaling group to use multiple Availability Zones. Configure the database as Multi‑AZ. Configure an Amazon RDS Proxy instance for the database.  
C. Configure the Auto Scaling group to use one Availability Zone. Generate hourly snapshots of the database. Recover the database from the snapshots in the event of a failure.  
D. Configure the Auto Scaling group to use multiple AWS Regions. Write the data from the application to Amazon S3. Use S3 Event Notifications to launch an AWS Lambda function to write the data to the database.

Correct Answer:  
B. Configure the Auto Scaling group to use multiple Availability Zones. Configure the database as Multi‑AZ. Configure an Amazon RDS Proxy instance for the database.

---

## Question 9
Question:  
A IT company’s security team requires that all data stored in the cloud be encrypted at rest at all times using encryption keys stored on premises. Which encryption options meet these requirements? (Select TWO).

Options:
A. Use server‑side encryption with AWS KMS managed encryption keys (SSE‑KMS).  
B. Use server‑side encryption with Amazon S3 managed encryption keys (SSE‑S3).  
C. Use an AWS Lambda function invoked by Amazon S3 events to encrypt the data using the customer’s keys.  
D. Use server‑side encryption with customer‑provided encryption keys (SSE‑C).  
E. Use client‑side encryption to provide at‑rest encryption.

Correct Answers:  
D. Use server‑side encryption with customer‑provided encryption keys (SSE‑C).  
E. Use client‑side encryption to provide at‑rest encryption.

---

## Question 10
Question:  
A media company runs an online voting system for a weekly live television program. During broadcasts, users submit hundreds of thousands of votes within minutes to a front‑end fleet of Amazon EC2 instances that run in an Auto Scaling group. The EC2 instances write the votes to an Amazon RDS database. However, the database is unable to keep up with the requests that come from the EC2 instances. A solutions architect must design a solution that processes the votes in the most efficient manner and without downtime. Which of the following options is correct?

Options:
A. Use Amazon EventBridge (Amazon CloudWatch Events) to create a scheduled event to re‑provision the database with larger, memory optimized instances during voting periods. When voting ends, re‑provision the database to use smaller instances.  
B. Configure the front‑end application to send votes to an Amazon Simple Queue Service (Amazon SQS) queue. Provision worker instances to read the SQS queue and write the vote information to the database.  
C. Scale the database horizontally by converting it to a Multi‑AZ deployment. Configure the front‑end application to write to both the primary and secondary DB instances.  
D. Migrate the front‑end application to AWS Lambda. Use Amazon API Gateway to route user requests to the Lambda functions.

Correct Answer:  
B. Configure the front‑end application to send votes to an Amazon Simple Queue Service (Amazon SQS) queue. Provision worker instances to read the SQS queue and write the vote information to the database.

---

## Question 11
Question:  
My company is deploying a new public web application to AWS. The application will run behind an Application Load Balancer (ALB). The application needs to be encrypted at the edge with an SSL/TLS certificate that is issued by an external certificate authority (CA). The certificate must be rotated each year before the certificate expires. Which of the following options is correct?

Options:
A. Use AWS Certificate Manager (ACM) to issue an SSL/TLS certificate. Apply the certificate to the ALB. Use the managed renewal feature to automatically rotate the certificate.  
B. Use AWS Certificate Manager (ACM) to issue an SSL/TLS certificate. Import the key material from the certificate. Apply the certificate to the ALB. Use the managed renewal feature to automatically rotate the certificate.  
C. Use AWS Certificate Manager (ACM) Private Certificate Authority to issue an SSL/TLS certificate from the root CA. Apply the certificate to the ALB. Use the managed renewal feature to automatically rotate the certificate.  
D. Use AWS Certificate Manager (ACM) to import an SSL/TLS certificate. Apply the certificate to the ALB. Use Amazon EventBridge (Amazon CloudWatch Events) to send a notification when the certificate is nearing expiration. Rotate the certificate manually.

Correct Answer:  
D. Use AWS Certificate Manager (ACM) to import an SSL/TLS certificate. Apply the certificate to the ALB. Use Amazon EventBridge (Amazon CloudWatch Events) to send a notification when the certificate is nearing expiration. Rotate the certificate manually.

---

## Question 12
Question:  
You successfully configure VPC Peering between VPC X and VPC Y. You then establish an IGW and a Direct Connect connection in VPC Y. Can instances in VPC X connect to your corporate office via the Direct Connect service, and connect to the Internet via the IGW. Which of the following options is correct?

Options:
A. Yes: VPC Peering is designed to route traffic between the VPCs.  
B. VPC peering does not support edge to edge routing.  
C. Instances in VPC A will be able to access the corporate office, but not the Internet.  
D. Instances in VPC A will be able to access the Internet, but not the corporate office.

Correct Answer:  
B. VPC peering does not support edge to edge routing.

---

## Question 13
Question:  
ABC company is building an ecommerce web application on AWS. The application sends information about new orders to an Amazon API Gateway REST API to process. The company wants to ensure that orders are processed in the order that they are received. Which of the following options is correct?

Options:
A. Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) FIFO queue when the application receives an order. Configure the SQS FIFO queue to invoke an AWS Lambda function for processing.  
B. Use an API Gateway integration to publish a message to an Amazon Simple Notification Service (Amazon SNS) topic when the application receives an order. Subscribe an AWS Lambda function to the topic to perform processing.  
C. Use an API Gateway authorizer to block any requests while the application processes an order.  
D. Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) standard queue when the application receives an order. Configure the SQS standard queue to invoke an AWS Lambda function for processing.

Correct Answer:  
A. Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) FIFO queue when the application receives an order. Configure the SQS FIFO queue to invoke an AWS Lambda function for processing.

---

## Question 14
Question:  
You are building an automated transcription service in which "Amazon EC2 worker" instances process an uploaded audio file and generate a text file. You must store both of these files in the same durable storage until the text file is retrieved, but you do not know what the storage capacity requirements are. Which storage option is both cost-efficient and scalable?

Options:
A. Multiple Amazon EBS volume with snapshots  
B. A single Amazon Glacier Vault  
C. A single Amazon S3 bucket  
D. Multiple instance stores

Correct Answer:  
C. A single Amazon S3 bucket

---

## Question 15
Question:  
A company has several web servers that need to frequently access a common Amazon RDS MySQL Multi-AZ DB instance. The company wants a secure method for the web servers to connect to the database while meeting a security requirement to rotate user credentials frequently. Which of the following options is correct?

Options:
A. Store the database user credentials in files encrypted with AWS Key Management Service (AWS KMS) on the web server file system. The web server should be able to decrypt the files and access the database.  
B. Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to access AWS Secrets Manager.  
C. Store the database user credentials in AWS Systems Manager OpsCenter. Grant the necessary IAM permissions to allow the web servers to access OpsCenter.  
D. Store the database user credentials in a secure Amazon S3 bucket. Grant the necessary IAM permissions to allow the web servers to retrieve credentials and access the database.

Correct Answer:  
B. Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to access AWS Secrets Manager.

---

## Question 16
Question:  
A mobile company needs to review its AWS Cloud deployment to ensure that its Amazon S3 buckets do not have unauthorized configuration changes. What should a solutions architect do to accomplish this goal?

Options:
A. Turn on AWS Config with the appropriate rules.  
B. Turn on AWS Trusted Advisor with the appropriate checks.  
C. Turn on Amazon Inspector with the appropriate assessment template.  
D. Turn on Amazon S3 server access logging. Configure Amazon EventBridge (Amazon Cloud Watch Events).

Correct Answer:  
A. Turn on AWS Config with the appropriate rules.

---

## Question 17
Question:  
A financial company has more than 5 TB of file data on Windows file servers that run on premises. Users and applications interact with the data each day. The company is moving its Windows workloads to AWS. As the company continues this process, the company requires access to AWS and on-premises file storage with minimum latency. The company needs a solution that minimizes operational overhead and requires no significant changes to the existing file access patterns. The company uses an AWS Site-to-Site VPN connection for connectivity to AWS. Which of the following options is correct?

Options:
A. Deploy and configure an Amazon S3 File Gateway on premises. Move the on-premises file data to the S3 File Gateway. Reconfigure the on-premises workloads and the cloud workloads to use the S3 File Gateway.  
B. Deploy and configure Amazon FSx for Windows File Server on AWS. Deploy and configure an Amazon FSx File Gateway on premises. Move the on-premises file data to the FSx File Gateway. Configure the cloud workloads to use FSx for Windows File Server on AWS. Configure the on-premises workloads to use the FSx File Gateway.  
C. Deploy and configure Amazon FSx for Windows File Server on AWS. Move the on-premises file data to FSx for Windows File Server. Reconfigure the workloads to use FSx for Windows File Server on AWS.  
D. Deploy and configure an Amazon S3 File Gateway on premises. Move the on-premises file data to Amazon S3. Reconfigure the workloads to use either Amazon S3 directly or the S3 File Gateway. depending on each workload's location.

Correct Answer:  
C. Deploy and configure Amazon FSx for Windows File Server on AWS. Move the on-premises file data to FSx for Windows File Server. Reconfigure the workloads to use FSx for Windows File Server on AWS.

---

## Question 18
Question:  
An IT company runs workloads on AWS. The company needs to connect to a service from an external provider. The service is hosted in the provider's VPC. According to the company’s security team, the connectivity must be private and must be restricted to the target service. The connection must be initiated only from the company’s VPC. Which of the following options is correct?

Options:
A. Ask the provider to create a virtual private gateway in its VPC. Use AWS PrivateLink to connect to the target service.  
B. Ask the provider to create a VPC endpoint for the target service. Use AWS PrivateLink to connect to the target service.  
C. Create a NAT gateway in a public subnet of the company’s VPC. Update the route table to connect to the target service.  
D. Create a VPC peering connection between the company's VPC and the provider's VPC. Update the route table to connect to the target service.

Correct Answer:  
B. Ask the provider to create a VPC endpoint for the target service. Use AWS PrivateLink to connect to the target service.

---

## Question 19
Question:  
XYZ company uses AWS Organizations to manage multiple AWS accounts for different departments. The management account has an Amazon S3 bucket that contains project reports. The company wants to limit access to this S3 bucket to only users of accounts within the organization in AWS Organizations without operational overhead. Which of the following options is correct?

Options:
A. Use AWS CloudTrail to monitor the CreateAccount, InviteAccountToOrganization, LeaveOrganization, and RemoveAccountFromOrganization events. Update the S3 bucket policy accordingly.  
B. Add the aws PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy.  
C. Create an organizational unit (OU) for each department. Add the aws:PrincipalOrgPaths global condition key to the S3 bucket policy.  
D. Tag each user that needs access to the S3 bucket. Add the aws:PrincipalTag global condition key to the S3 bucket policy.

Correct Answer:  
B. Add the aws PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy.

---

## Question 20
Question:  
A solutions architect is designing a two-tier web application. The application consists of a public-facing web tier hosted on Amazon EC2 in public subnets. The database tier consists of Microsoft SQL Server running on Amazon EC2 in a private subnet. Security is a high priority for the company. How should security groups be configured in this situation? (Select two.)

Options:
A. Configure the security group for the database tier to allow inbound traffic on ports 443 and 1433 from the security group for the web tier.  
B. Configure the security group for the database tier to allow inbound traffic on port 1433 from the security group for the web tier.  
C. Configure the security group for the web tier to allow outbound traffic on port 443 from 0.0.0.0/0.  
D. Configure the security group for the database tier to allow outbound traffic on ports 443 and 1433 to the security group for the web tier.  
E. Configure the security group for the web tier to allow inbound traffic on port 443 from 0.0.0.0/0.

Correct Answers:  
B. Configure the security group for the database tier to allow inbound traffic on port 1433 from the security group for the web tier.  
E. Configure the security group for the web tier to allow inbound traffic on port 443 from 0.0.0.0/0.

---

## Question 21
Question:  
An IT company's HTTP application is behind a Network Load Balancer (NLB). The NLB's target group is configured to use an Amazon EC2 Auto Scaling group with multiple EC2 instances that run the web service. The company notices that the NLB is not detecting HTTP errors for the application. These errors require a manual restart of the EC2 instances that run the web service. The company needs to improve the application's availability without writing custom scripts or code. Which of the following options is correct?

Options:
A. Enable HTTP health checks on the NLB, supplying the URL of the company's application.  
B. Create an Amazon CloudWatch alarm that monitors the UnhealthyHostCount metric for the NLB. Configure an Auto Scaling action to replace unhealthy instances when the alarm is in the ALARM state.  
C. Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Configure an Auto Scaling action to replace unhealthy instances.  
D. Add a cron job to the EC2 instances to check the local application's logs once each minute. If HTTP errors are detected, the application will restart.

Correct Answer:  
C. Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Configure an Auto Scaling action to replace unhealthy instances.

---

## Question 22
Question:  
A company uses AWS Organizations to create dedicated AWS accounts for each business unit to manage each business unit's account independently upon request. The root email recipient missed a notification that was sent to the root user email address of one account. The company wants to ensure that all future notifications are not missed. Future notifications must be limited to account administrators. Which of the following options is correct?

Options:
A. Configure the company’s email server to forward notification email messages that are sent to the AWS account root user email address to all users in the organization.  
B. Configure all existing AWS accounts and all newly created accounts to use the same root user email address. Configure AWS account alternate contacts in the AWS Organizations console or programmatically.  
C. Configure all AWS account root user email addresses as distribution lists that go to a few administrators who can respond to alerts. Configure AWS account alternate contacts in the AWS Organizations console or programmatically.  
D. Configure all AWS account root user email messages to be sent to one administrator who is responsible for monitoring alerts and forwarding those alerts to the appropriate groups.

Correct Answer:  
C. Configure all AWS account root user email addresses as distribution lists that go to a few administrators who can respond to alerts. Configure AWS account alternate contacts in the AWS Organizations console or programmatically.

---

## Question 23
Question:  
You have 10 CloudFormation templates; each template is for a different application architecture. This architecture varies between your web apps and your gaming apps. What determines the cost of using the CloudFormation templates. Which of the following options is correct?

Options:
A. 0.20$ per template per month  
B. The time it takes to build the architecture with Cloud Formation.  
C. 0.101$ per template per month  
D. Cloud Formation does not have any additional cost but you are charged for the underlying resources it builds.

Correct Answer:  
D. Cloud Formation does not have any additional cost but you are charged for the underlying resources it builds.

---

## Question 24
Question:  
A company needs to retain application log files for a critical application for 10 years. The application team regularly accesses logs from the past month for troubleshooting, but logs older than 1 month are rarely accessed. The application generates more than 10 TB of logs per month. Which storage option meets these requirements MOST cost-effectively?

Options:
A. Store the logs in Amazon S3. Use S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.  
B. Store the logs in Amazon CloudWatch Logs. Use AWS Backup to move logs more than 1 month old to S3 Glacier Deep Archive.  
C. Store the logs in Amazon S3. Use AWS Backup to move logs more than 1 month old to S3 Glacier Deep Archive.  
D. Store the logs in Amazon CloudWatch Logs. Use Amazon S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.

Correct Answer:  
A. Store the logs in Amazon S3. Use S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.

---

## Question 25
Question:  
XYZ company collects data for temperature, humidity, and atmospheric pressure in cities across multiple continents. The average volume of data that the company collects from each site daily is 500 GB. Each site has a high-speed Internet connection. The XYZ company wants to aggregate the data from all these global sites as quickly as possible in a single Amazon S3 bucket. The solution must minimize operational complexity. Which of the following options is correct?

Options:
A. Upload the data from each site to an S3 bucket in the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3 bucket. Then remove the data from the origin S3 bucket.  
B. Schedule AWS Snowball Edge Storage Optimized device jobs daily to transfer data from each site to the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3 bucket.  
C. Upload the data from each site to an Amazon EC2 instance in the closest Region. Store the data in an Amazon Elastic Block Store (Amazon EBS) volume. At regular intervals, take an EBS snapshot and copy it to the Region that contains the destination S3 bucket. Restore the EBS volume in that Region.  
D. Turn on S3 Transfer Acceleration on the destination S3 bucket. Use multipart uploads to directly upload site data to the destination S3 bucket.

Correct Answer:  
D. Turn on S3 Transfer Acceleration on the destination S3 bucket. Use multipart uploads to directly upload site data to the destination S3 bucket.

---

## Question 26
Question:  
A company wants to migrate its existing on-premises monolithic application to AWS. The company wants to keep as much of the front-end code and the backend code as possible. However, the company wants to break the application into smaller applications. A different team will manage each application. The company needs a highly scalable solution that minimizes operational overhead. Which of the following options is correct?

Options:
A. Host the application on Amazon Elastic Container Service (Amazon ECS). Set up an Application Load Balancer with Amazon ECS as the target.  
B. Host the application on AWS Lambda. Integrate the application with Amazon API Gateway.  
C. Host the application on Amazon EC2 instances. Set up an Application Load Balancer with EC2 instances in an Auto Scaling group as targets.

Correct Answer:  
A. Host the application on Amazon Elastic Container Service (Amazon ECS). Set up an Application Load Balancer with Amazon ECS as the target.

---

## Question 27
Question:  
Which of the following Amazon S3 Storage Classes offer 99.999999999% (11 x 9s) durability?

Options:
A. Standard, Standard-Infrequent Access, One Zone-Infrequent Access  
B. Standard, Glacier, Reduced Redundancy Storage  
C. Standard-Infrequent Access, One Zone-Infrequent Access, Reduced Redundancy Storage  
D. Reduced Redundancy Storage, Standard, One Zone-Infrequent Access

Correct Answer:  
A. Standard, Standard-Infrequent Access, One Zone-Infrequent Access

---

## Question 28
Question:  
How can software determine the public and private IP addresses of the Amazon Elastic Cloud Compute instance that it is running on? Which of the following options is correct?

Options:
A. Query the local instance metadata  
B. Query the appropriate Amazon CloudWatch metric  
C. Use an ipconfig or ifconfig command  
D. Query the local instance userdata

Correct Answer:  
A. Query the local instance metadata

---

## Question 29
Question:  
A solutions architect must design a highly available infrastructure for a website. The website is powered by Windows web servers that run on Amazon EC2 instances. The solutions architect must implement a solution that can mitigate a large-scale DDoS attack that originates from thousands of IP addresses. Downtime is not acceptable for the website. Which actions should the solutions architect take to protect the website from such an attack? (Choose two.)

Options:
A. Use EC2 Spot Instances in an Auto Scaling group with a target tracking scaling policy that is set to 80% CPU utilization.  
B. Use an AWS Lambda function to automatically add attacker IP addresses to VPC network ACLs.  
C. Configure the website to use Amazon CloudFront for both static and dynamic content.  
D. Configure Amazon GuardDuty to automatically block the attackers.  
E. Use AWS Shield Advanced to stop the DDoS attack.

Correct Answers:  
C. Configure the website to use Amazon CloudFront for both static and dynamic content.  
E. Use AWS Shield Advanced to stop the DDoS attack.

---

## Question 30
Question:  
An application runs on an Amazon EC2 instance in a VPC. The application processes logs that are stored in an Amazon S3 bucket. The EC2 instance needs to access the S3 bucket without connectivity to the internet. Which solution will provide private network connectivity to Amazon S3?

Options:
A. Create a gateway VPC endpoint to the S3 bucket.  
B. Stream the logs to Amazon CloudWatch Logs. Export the logs to the S3 bucket.  
C. Create an Amazon API Gateway API with a private link to access the S3 endpoint.  
D. Create an instance profile on Amazon EC2 to allow S3 access.

Correct Answer:  
A. Create a gateway VPC endpoint to the S3 bucket.

---

## Question 31
Question:  
A company is preparing to store confidential data in Amazon S3. For compliance reasons, the data must be encrypted at rest. Encryption key usage must be logged for auditing purposes. Keys must be rotated every year. Which of the following options is correct?

Options:
A. Server-side encryption with AWS KMS keys (SSE-KMS) with manual rotation  
B. Server-side encryption with Amazon S3 managed keys (SSE-S3)  
C. Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation  
D. Server-side encryption with customer-provided keys (SSE-C)

Correct Answer:  
C. Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation

---

## Question 32
Question:  
An IT company is developing a two-tier web application on AWS. The company's developers have deployed the application on an Amazon EC2 instance that connects directly to a backend Amazon RDS database. The company must not hardcode database credentials in the application. The company must also implement a solution to automatically rotate the database credentials on a regular basis. Which of the following options is correct?

Options:
A. Store the database credentials as encrypted parameters in AWS Systems Manager Parameter Store. Turn on automatic rotation for the encrypted parameters. Attach the required permission to the EC2 role to grant access to the encrypted parameters.  
B. Store the database credentials in a configuration file in an encrypted Amazon S3 bucket. Use Amazon EventBridge rules to run a scheduled AWS Lambda function that updates the RDS credentials and the credentials in the configuration file at the same time.  
C. Store the database credentials as a secret in AWS Secrets Manager. Turn on automatic rotation for the secret. Attach the required permission to the EC2 role to grant access to the secret.  
D. Store the database credentials in the instance metadata.

Correct Answer:  
C. Store the database credentials as a secret in AWS Secrets Manager. Turn on automatic rotation for the secret. Attach the required permission to the EC2 role to grant access to the secret.

---

## Question 33
Question:  
A company’s website provides users with downloadable historical performance reports. The website needs a solution that will scale to meet the company’s website demands globally. The solution should be cost-effective, limit the provisioning of infrastructure resources, and provide the fastest possible response time. Which of the following options is correct?

Options:
A. Application Load Balancer with Amazon EC2 Auto Scaling  
B. Amazon CloudFront and Amazon S3  
C. AWS Lambda and Amazon DynamoDB  
D. Amazon Route 53 with internal Application Load Balancers

Correct Answer:  
B. Amazon CloudFront and Amazon S3

---

## Question 34
Question:  
A solutions architect is designing the cloud architecture for a new application being deployed on AWS. The process should run in parallel while adding and removing application nodes as needed based on the number of jobs to be processed. The processor application is stateless. The solutions architect must ensure that the application is loosely coupled and the job items are durably stored. Which of the following options is correct?

Options:
A. Create an Amazon SNS topic and scale instances based on CPU.  
B. Create an Amazon SQS queue and scale based on network usage.  
C. Create an Amazon SQS queue and scale instances based on queue length.  
D. Create an Amazon SNS topic and scale based on message count.

Correct Answer:  
C. Create an Amazon SQS queue and scale instances based on queue length.

---

## Question 35
Question:  
A gaming company is designing a highly available architecture. The application runs on a modified Linux kernel and supports only UDP-based traffic. The company needs the front-end tier to provide the best possible user experience. That tier must have low latency, route traffic to the nearest edge location, and provide static IP addresses for entry into the application endpoints. What should a solutions architect do to meet these requirements?

Options:
A. Configure Amazon Route 53 with an Application Load Balancer.  
B. Configure Amazon CloudFront with a Network Load Balancer.  
C. Configure Amazon API Gateway with an Application Load Balancer.  
D. Configure AWS Global Accelerator with a Network Load Balancer.

Correct Answer:  
D. Configure AWS Global Accelerator with a Network Load Balancer.

---

## Question 36
Question:  
A new hospital recently deployed a RESTful API with Amazon API Gateway and AWS Lambda. The hospital needs to modify the Lambda code to identify protected health information (PHI) in reports that are uploaded in PDF and JPEG format. Which of the following options is correct?

Options:
A. Use Amazon Textract and Amazon SageMaker.  
B. Use Python libraries to extract text and detect PHI.  
C. Use Amazon Rekognition and Amazon Comprehend Medical.  
D. Use Amazon Textract and Amazon Comprehend Medical.

Correct Answer:  
D. Use Amazon Textract and Amazon Comprehend Medical.

---

## Question 37
Question:  
We have a client who is considering a move to AWS. In establishing a new account, what is the first thing the company should do?

Options:
A. Set up an account using their company email address.  
B. Set up an account via ELB.  
C. Set up an account using Cloud Search.  
D. Set up an account via EC2.

Correct Answer:  
A. Set up an account using their company email address.

---

## Question 38
Question:  
A document management company runs its infrastructure on AWS and wants to convert uploaded PDF files to JPG images at scale. The files average 5 MB. Which solution is most affordable and scalable?

Options:
A. Store files in DynamoDB and process with Lambda.  
B. Store files in Amazon S3 and trigger AWS Lambda using S3 events.  
C. Use Elastic Beanstalk with EFS storage.  
D. Use Elastic Beanstalk with EBS storage.

Correct Answer:  
B. Store files in Amazon S3 and trigger AWS Lambda using S3 events.

---

## Question 39
Question:  
An AWS Glue ETL job processes XML data from an Amazon S3 bucket daily. AWS Glue is reprocessing all the data each run. What should the solutions architect do?

Options:
A. Use FindMatches transform.  
B. Delete processed data.  
C. Reduce workers.  
D. Enable job bookmarks.

Correct Answer:  
D. Enable job bookmarks.

---

## Question 40
Question:  
A social media website allows users to upload images. The company must ensure images do not contain inappropriate content with minimal development effort. Which solution should be used?

Options:
A. Amazon Rekognition with human review for low-confidence results.  
B. Custom ML model on AWS Fargate.  
C. Amazon SageMaker custom model.  
D. Amazon Comprehend.

Correct Answer:  
A. Amazon Rekognition with human review for low-confidence results.

---

## Question 41
Question:  
A company wants to reduce costs of its EC2 three-tier architecture. Production runs 24/7 while dev and test run only part of the day. Which purchasing model is most cost-effective?

Options:
A. Spot for production and Reserved for dev/test  
B. On-Demand for production and Spot for dev/test  
C. Reserved Instances for production and On-Demand for dev/test  
D. Spot for production and Reserved for dev/test

Correct Answer:  
C. Reserved Instances for production and On-Demand for dev/test.

---

## Question 42
Question:  
A Lambda function must be invoked by an EventBridge rule using least privilege. Which configuration is correct?

Options:
A. Execution role allowing lambda:InvokeFunction for *.  
B. Resource-based policy allowing events.amazonaws.com to invoke the function.  
C. Execution role allowing lambda.amazonaws.com.  
D. Resource policy allowing lambda:*.

Correct Answer:  
B. Resource-based policy allowing events.amazonaws.com to invoke the function.

---

## Question 43
Question:  
Two AWS accounts each contain a VPC and must securely copy files between EC2 instances without bandwidth bottlenecks. Which solution should be used?

Options:
A. Direct Connect gateway  
B. VPC peering connection  
C. VPC gateway endpoint  
D. Virtual private gateway

Correct Answer:  
B. VPC peering connection.

---

## Question 44
Question:  
Which AWS feature is used to implement high-performance computing with low-latency networking?

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
In the event of an outage, Amazon RDS automatically switches to a standby replica in another AZ when which feature is enabled?

Options:
A. Multiple read replicas  
B. Multiple write replicas  
C. Multi-AZ deployment  
D. Multi-Region deployment

Correct Answer:  
C. Multi-AZ deployment.

---

## Question 46
Question:  
How can an S3 bucket restrict access only to accounts within the same AWS Organization?

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
An ecommerce company launches a one-deal-a-day website that must handle millions of requests with millisecond latency. Which architecture is best?

Options:
A. S3 + CloudFront + API Gateway + Lambda + DynamoDB  
B. Multiple S3 buckets  
C. Kubernetes on EKS  
D. EC2 Auto Scaling

Correct Answer:  
A. S3 + CloudFront + API Gateway + Lambda + DynamoDB.

---

## Question 48
Question:  
How can an EC2 instance be copied to another Region?

Options:
A. Direct copy  
B. Stop and copy  
C. Detach root volume  
D. Create an AMI and copy it

Correct Answer:  
D. Create an AMI and copy it.

---

## Question 49
Question:  
Users see different documents depending on which EC2 instance serves their request. What should be done?

Options:
A. Send requests to both servers  
B. Copy data to both EBS volumes  
C. Move data to Amazon EFS and mount on both instances  
D. Use sticky sessions

Correct Answer:  
C. Move data to Amazon EFS and mount on both instances.

---

## Question 50
Question:  
Which of the following are IAM components? (Select two)

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
Ensure EC2, RDS, and Redshift resources always have required tags. What should be used?

Options:
A. Lambda script  
B. Cost Explorer  
C. AWS Config rules  
D. EC2 cron script

Correct Answer:  
C. AWS Config rules.

---

## Question 52
Question:  
An on-premises website must load faster for European users but backend remains in the US. What should be used?

Options:
A. Move to S3  
B. EC2 in us-east-1  
C. Route53 geoproximity routing  
D. CloudFront with custom origin

Correct Answer:  
D. CloudFront with custom origin.

---

## Question 53
Question:  
A Lambda ingestion system reaches scaling limits when writing to Aurora. What architecture improves scalability?

Options:
A. Move to EC2  
B. Two Lambdas with SNS  
C. Two Lambdas with SQS  
D. Move to DynamoDB

Correct Answer:  
C. Two Lambdas connected with SQS.

---

## Question 54
Question:  
A company wants to run containers without managing servers. Which service should be used?

Options:
A. ECS on Fargate  
B. ECS on EC2  
C. ECS optimized AMI  
D. EC2 with Docker

Correct Answer:  
A. ECS on Fargate.

---

## Question 55
Question:  
A two-tier application running in one AZ must become highly available. Which actions should be taken? (Select two)

Options:
A. Deploy RDS Multi-AZ in private subnets  
B. Deploy EC2 Auto Scaling with ALB across AZs  
C. Create new subnets in same AZ  
D. Move DB to public subnet

Correct Answers:  
A. Deploy RDS Multi-AZ  
B. Deploy EC2 Auto Scaling with ALB

---

## Question 56
Question:  
A hybrid architecture needs consistent low latency but cheaper backup connectivity. Which design is correct?

Options:
A. Direct Connect with automatic failover  
B. Direct Connect with VPN backup  
C. Two VPN tunnels  
D. Two Direct Connect connections

Correct Answer:  
B. Direct Connect with VPN backup.

---

## Question 57
Question:  
A database requires 64,000 IOPS on a single EBS volume. Which configuration should be used?

Options:
A. I3 instance store  
B. Two io1 volumes striped  
C. Nitro EC2 instance with io1 volume  
D. RAID gp2 volumes

Correct Answer:  
C. Nitro EC2 instance with io1 volume.

---

## Question 58
Question:  
An application frequently accesses S3 in the same Region and transfer costs increased. What should be implemented?

Options:
A. Internet Gateway  
B. S3 VPC Gateway Endpoint  
C. API Gateway  
D. NAT Gateway

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
In CloudFormation how do you map EBS volumes to EC2 instances?

Options:
A. Reference physical instance IDs  
B. Logical instance IDs  
C. Logical IDs of both EBS and EC2  
D. Physical IDs of both

Correct Answer:  
C. Logical IDs of both EBS and EC2.

---

## Question 61
Question:  
Private EC2 instances must download patches from the internet. Which actions are required? (Select two)

Options:
A. Route table pointing to NAT gateway  
B. NAT instance in private subnet  
C. Route table to Internet Gateway  
D. Assign Elastic IPs  
E. NAT gateway in public subnet

Correct Answers:  
A. Route table pointing to NAT gateway  
E. NAT gateway in public subnet

---

## Question 62
Question:  
If SSL should not terminate on the load balancer, which protocol should be used between the client and the load balancer?

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
An SMB file server must extend storage and keep recent files fast while archiving older files automatically. Which solution is correct?

Options:
A. AWS DataSync  
B. Install S3 utilities on clients  
C. Amazon S3 File Gateway with lifecycle policies  
D. Amazon FSx for Windows

Correct Answer:  
C. Amazon S3 File Gateway with lifecycle policies.

---

## Question 64
Question:  
Uploaded documents must never be modified or deleted after storage due to regulatory requirements. Which solution should be used?

Options:
A. EFS read-only mount  
B. S3 Versioning with read-only ACL  
C. S3 lifecycle archiving  
D. S3 Versioning with Object Lock

Correct Answer:  
D. S3 Versioning with Object Lock.

---

## Question 65
Question:  
A global news portal must deliver personalized content with the least latency worldwide. Which architecture should be used?

Options:
A. Multi-Region deployment with Route53 geolocation routing  
B. Multi-Region deployment with Route53 latency-based routing  
C. Single Region with CloudFront for all content  
D. Single Region with CloudFront only for static content

Correct Answer:  
B. Multi-Region deployment with Route53 latency-based routing.

---
