# AWS SAA Complete Practice Questions

## Question 1

A gaming company is implementing a shared storage solution for a gaming application that is hosted in an on-premises data center. The company needs the ability to use Lustre clients to access data. The solution must be fully managed. Which of the following options is correct?

### Options

- Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to the file share.
- Create an AWS Storage Gateway file gateway. Create a file share that uses the required client protocol. Connect the application server to the file share.
- Create an Amazon Elastic File System (Amazon EFS) file system, and configure it to support Lustre. Attach the file system to the origin server. Connect the application server to the file system.
- __Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.__

### Correct Answer

Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

### Explanation

Amazon FSx for Lustre is a fully managed high-performance file system that provides sub-millisecond latencies, up to hundreds of GBs/s of throughput, and millions of IOPS. It is POSIX-compliant, so you can use your current Linux-based applications without having to make any changes. FSx for Lustre also supports Lustre clients, so you can access your data from on-premises servers.

## Question 2

An e-commerce company runs an e-commerce application on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 auto-scaling group across multiple Availability Zones. The auto-scaling group scales based on CPU utilization metrics. The e-commerce application stores the transaction data in a MySQL 8.0 database that is hosted on a large EC2 instance. The database's performance degrades quickly as application load increases. The application handles more read requests than write transactions. The company wants a solution that will automatically scale the database to meet the demand of unpredictable read workloads while maintaining high availability. Which of the following options is correct?

### Options

- Use Amazon RDS with a Single-AZ deployment Configure Amazon RDS to add reader instances in a different Availability Zone.
- Use Amazon Redshift with a single node for leader and compute functionality.
- Use Amazon ElastiCache for Memcached with EC2 Spot Instances.
- __Use Amazon Aurora with a Multi-AZ deployment. Configure Aurora Auto Scaling with Aurora Replicas.__

### Correct Answer

Use Amazon Aurora with a Multi-AZ deployment. Configure Aurora Auto Scaling with Aurora Replicas.

### Explanation

Using Amazon Aurora with a Multi-AZ deployment and configuring Aurora Auto Scaling with Aurora Replicas will provide both read scalability and high availability. Aurora is a MySQL-compatible database that is designed to handle high read workloads. With Aurora's Multi-AZ deployment, a replica will be created in a different Availability Zone for disaster recovery purposes. Aurora Replicas can also be used to scale read workloads by adding read replicas.

## Question 3

Which IAM policy condition key should be used if the solution architect wants to check whether the request was sent using SSL?

### Options

- AWS: agent
- AWS: source IP
- __AWS: secure transport__
- AWS: secure IP

### Correct Answer

AWS: secure transport

### Explanation

The AWS:SecureTransport condition key returns true if the request was sent over HTTPS, and false if the request was sent over HTTP. You can use this condition key in an IAM policy to allow or deny actions based on whether the request was sent using SSL.

## Question 4

If a company wants to build its own payment application, it should take advantage of the richness and flexibility of _____________.

### Options

- Payoneer Pyment Services
- EBay Payment service
- PayPal Payment service
- __Amazon AWS FPS__

### Correct Answer

Amazon AWS FPS

### Explanation

Amazon FPS is a flexible and scalable payment processing service that allows you to accept payments from your customers using a variety of payment methods, including credit cards, debit cards, and bank accounts. You can use FPS to process one-time payments, recurring payments, and pre-paid payments. FPS is also very easy to use. You can integrate FPS into your application using the AWS APIs or the FPS SDKs for Java, Python, and PHP.

## Question 5

A solutions architect is designing a VPC with public and private subnets. The VPC and subnets use IPv4 CIDR blocks. There is one public subnet and one private subnet in each of three Availability Zones (AZs) for high availability. An internet gateway is used to provide internet access for the public subnets. The private subnets require access to the internet to allow Amazon EC2 instances to download software updates. What should the solutions architect do to enable Internet access for the private subnets?

### Options

- Create an egress-only internet gateway on one of the public subnets. Update the route table for the private subnets that forward non-VPC traffic to the egress-only Internet gateway.
- Create three NAT instances, one for each private subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT instance in its AZ.
- Create a second internet gateway on one of the private subnets. Update the route table for the private subnets that forward non-VPC traffic to the private internet gateway.
- __Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT gateway in its AZ.__

### Correct Answer

Create three NAT gateways, one for each public subnet in each AZ. Create a private route table for each AZ that forwards non-VPC traffic to the NAT gateway in its AZ.

### Explanation

To enable Internet access for the private subnets, the solutions architect should create three NAT gateways, one for each public subnet in each Availability Zone (AZ). NAT gateways allow private instances to initiate outbound traffic to the Internet but do not allow inbound traffic from the Internet to reach the private instances. The solutions architect should then create a private route table for each AZ that forwards non-VPC traffic to the NAT gateway in its AZ. This will allow instances in the private subnets to access the Internet through the NAT gateways in the public subnets.

## Question 6

A company runs a shopping application that uses Amazon DynamoDB to store customer information. In case of data corruption, a solutions architect needs to design a solution that meets a recovery point objective (RPO) of 15 minutes and a recovery time objective (RTO) of 1 hour. What should the solutions architect recommend to meet these requirements?

### Options

- __Configure DynamoDB point-in-time recovery. For RPO recovery, restore to the desired point in time.__
- Schedule Amazon Elastic Block Store (Amazon EBS) snapshots for the DynamoDB table every 15 minutes. For RPO recovery, restore the DynamoDB table by using the EBS snapshot.
- Configure DynamoDB global tables. For RPO recovery, point the application to a different AWS Region.
- Export the DynamoDB data to Amazon S3 Glacier on a daily basis. For RPO recovery, import the data from S3 Glacier to DynamoDB.

### Correct Answer

Configure DynamoDB point-in-time recovery. For RPO recovery, restore to the desired point in time.

### Explanation

DynamoDB point-in-time recovery (PITR) allows you to restore your DynamoDB table to any point in time within the past 35 days. This means that you can recover from data corruption with an RPO of 15 minutes. The RTO for DynamoDB PITR is typically less than 1 hour. This is because DynamoDB can restore your table to a new table in a different AWS Region. The new table will be in sync with the original table at the point in time that you specify.

## Question 7

A IT company performs monthly maintenance on its AWS infrastructure. During these maintenance activities, the company needs to rotate the credentials for its Amazon RDS for MySQL databases across multiple AWS Regions. Which of the following options is correct?

### Options

- Store the credentials in an Amazon S3 bucket that has server-side encryption (SSE) enabled. Use Amazon EventBridge (Amazon CloudWatch Events) to invoke an AWS Lambda function to rotate the credentials.
- Encrypt the credentials as secrets by using AWS Key Management Service (AWS KMS) multi-Region customer managed keys. Store the secrets in an Amazon DynamoDB global table. Use an AWS Lambda function to retrieve the secrets from DynamoDB. Use the RDS API to rotate the secrets.
- __Store the credentials as secrets in AWS Secrets Manager. Use multi-Region secret replication for the required Regions. Configure Secrets Manager to rotate the secrets on a schedule.__
- Store the credentials as secrets in AWS Systems Manager by creating a secure string parameter. Use multi-Region secret replication for the required Regions. Configure Systems Manager to rotate the secrets on a schedule.

### Correct Answer

Store the credentials as secrets in AWS Secrets Manager. Use multi-Region secret replication for the required Regions. Configure Secrets Manager to rotate the secrets on a schedule.

### Explanation

AWS Secrets Manager allows you to store, manage, and rotate secrets, such as database credentials, across multiple AWS Regions. By enabling multi-Region secret replication, you can replicate the secrets across the required Regions to allow for seamless rotation of the credentials during maintenance activities. Additionally, Secrets Manager provides automatic rotation of secrets on a schedule, which would minimize the operational overhead of rotating the credentials on a monthly basis.

## Question 8

An IT company is running a business-critical web application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances are in an Auto Scaling group. The application uses an Amazon Aurora PostgreSQL database that is deployed in a single Availability Zone. The company wants the application to be highly available with minimum downtime and minimum loss of data. Which of the following options is correct?

### Options

- Place the EC2 instances in different AWS Regions. Use Amazon Route 53 health checks to redirect traffic. Use Aurora PostgreSQL Cross-Region Replication.
- __Configure the Auto Scaling group to use multiple Availability Zones. Configure the database as Multi-AZ. Configure an Amazon RDS Proxy instance for the database.__
- Configure the Auto Scaling group to use one Availability Zone. Generate hourly snapshots of the database. Recover the database from the snapshots in the event of a failure.
- Configure the Auto Scaling group to use multiple AWS Regions. Write the data from the application to Amazon S3. Use S3 Event Notifications to launch an AWS Lambda function to write the data to the database.

### Correct Answer

Configure the Auto Scaling group to use multiple Availability Zones. Configure the database as Multi-AZ. Configure an Amazon RDS Proxy instance for the database.

### Explanation

The company wants the application to be highly available with minimum downtime and minimum loss of data. The best way to achieve this is to configure the Auto Scaling group to use multiple Availability Zones and configure the database as Multi-AZ. This will ensure that the application and database are always available, even if one Availability Zone fails. In addition, configuring an Amazon RDS Proxy instance for the database will further improve the availability of the application. An RDS Proxy instance is a lightweight, read-only proxy that sits between the application and the database. It can improve the performance of the application by caching queries and by routing traffic to healthy database instances.

## Question 9

A IT company’s security team requires that all data stored in the cloud be encrypted at rest at all times using encryption keys stored on premises. Which encryption options meet these requirements? (Select TWO).

### Options

- Use server-side encryption with AWS KMS managed encryption keys (SSE-KMS).
- Use server-side encryption with Amazon S3 managed encryption keys (SSE-S3).
- Use an AWS Lambda function invoked by Amazon S3 events to encrypt the data using the customer’s keys.
- __Use server-side encryption with customer-provided encryption keys (SSE-C).__ 
- __Use client-side encryption to provide at-rest encryption.__

### Correct Answer

Use server-side encryption with customer-provided encryption keys (SSE-C).

Use client-side encryption to provide at-rest encryption.

### Explanation

Server-side encryption with customer-provided keys (SSE-C) enables Amazon S3 to encrypt objects on the server side using an encryption key provided in the PUT request. The same key must be provided in the GET requests for Amazon S3 to decrypt the object. Customers also have the option to encrypt data on the client side before uploading it to Amazon S3, and then they can decrypt the data after downloading it. AWS software development kits (SDKs) provide an S3 encryption client that streamlines the process. Reference: https://docs.aws.amazon.com/AmazonS3/latest/userguide/ServerSideEncryptionCustomerKeys.html

## Question 10

A media company runs an online voting system for a weekly live television program. During broadcasts, users submit hundreds of thousands of votes within minutes to a front-end fleet of Amazon EC2 instances that run in an Auto Scaling group. The EC2 instances write the votes to an Amazon RDS database. However, the database is unable to keep up with the requests that come from the EC2 instances. A solutions architect must design a solution that processes the votes in the most efficient manner and without downtime. Which of the following options is correct?

### Options

- Use Amazon EventBridge (Amazon CloudWatch Events) to create a scheduled event to re-provision the database with larger, memory optimized instances during voting periods. When voting ends, re-provision the database to use smaller instances.
- __Configure the front-end application to send votes to an Amazon Simple Queue Service (Amazon SQS) queue. Provision worker instances to read the SQS queue and write the vote information to the database.__
- Scale the database horizontally by converting it to a Multi-AZ deployment. Configure the front-end application to write to both the primary and secondary DB instances.
- Migrate the front-end application to AWS Lambda. Use Amazon API Gateway to route user requests to the Lambda functions.

### Correct Answer

Configure the front-end application to send votes to an Amazon Simple Queue Service (Amazon SQS) queue. Provision worker instances to read the SQS queue and write the vote information to the database.

### Explanation

Decouple the ingestion of votes from the database to allow the voting system to continue processing votes without waiting for the database writes. Add dedicated workers to read from the SQS queue to allow votes to be entered into the database at a controllable rate. The votes will be added to the database as fast as the database can process them, but no votes will be lost.

## Question 11

My company is deploying a new public web application to AWS. The application will run behind an Application Load Balancer (ALB). The application needs to be encrypted at the edge with an SSL/TLS certificate that is issued by an external certificate authority (CA). The certificate must be rotated each year before the certificate expires. Which of the following options is correct?

### Options

- Use AWS Certificate Manager (ACM) to issue an SSL/TLS certificate. Apply the certificate to the ALB. Use the managed renewal feature to automatically rotate the certificate.
- Use AWS Certificate Manager (ACM) to issue an SSL/TLS certificate. Import the key material from the certificate. Apply the certificate to the ALUse the managed renewal feature to automatically rotate the certificate.
- Use AWS Certificate Manager (ACM) Private Certificate Authority to issue an SSL/TLS certificate from the root CA. Apply the certificate to the ALB. Use the managed renewal feature to automatically rotate the certificate.
- __Use AWS Certificate Manager (ACM) to import an SSL/TLS certificate. Apply the certificate to the ALB. Use Amazon EventBridge (Amazon CloudWatch Events) to send a notification when the certificate is nearing expiration. Rotate the certificate manually.__

### Correct Answer

Use AWS Certificate Manager (ACM) to import an SSL/TLS certificate. Apply the certificate to the ALB. Use Amazon EventBridge (Amazon CloudWatch Events) to send a notification when the certificate is nearing expiration. Rotate the certificate manually.

### Explanation

Company is deploying a new public web application to AWS. The application will run behind an Application Load Balancer (ALB). The application needs to be encrypted at the edge with an SSL/TLS certificate that is issued by an external certificate authority (CA). The certificate must be rotated each year before the certificate expires.

## Question 12

You successfully configure VPC Peering between VPC X and VPC Y. You then establish an IGW and a Direct Connect connection in VPC Y. Can instances in VPC X connect to your corporate office via the Direct Connect service, and connect to the Internet via the IGW. Which of the following options is correct?

### Options

- Yes: VPC Peering is designed to route traffic between the VPCs.
- __VPC peering does not support edge to edge routing.__
- Instances in VPC A will be able to access the corporate office, but not the Internet.
- Instances in VPC A will be able to access the Internet, but not the corporate office.

### Correct Answer

VPC peering does not support edge to edge routing.

### Explanation

VPC peering allows resources in two VPCs to communicate with each other as if they were on the same network. This means that instances in VPC X will be able to communicate with the corporate office via the Direct Connect connection in VPC Y. However, VPC peering does not support edge to edge routing, which means that instances in VPC X will not be able to access the Internet via the IGW in VPC Y. To allow instances in VPC X to access the Internet via the IGW in VPC Y, you would need to create a transit gateway. A transit gateway is a network appliance that provides a central hub for routing traffic between VPCs, on-premises networks, and AWS services.

## Question 13

ABC company is building an ecommerce web application on AWS. The application sends information about new orders to an Amazon API Gateway REST API to process. The company wants to ensure that orders are processed in the order that they are received. Which of the following options is correct?

### Options

- __Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) FIFO queue when the application receives an order. Configure the SQS FIFO queue to invoke an AWS Lambda function for processing.__
- Use an API Gateway integration to publish a message to an Amazon Simple Notification Service (Amazon SNS) topic when the application receives an order. Subscribe an AWS Lambda function to the topic to perform processing.
- Use an API Gateway authorizer to block any requests while the application processes an order.
- Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) standard queue when the application receives an order. Configure the SQS standard queue to invoke an AWS Lambda function for processing.

### Correct Answer

Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) FIFO queue when the application receives an order. Configure the SQS FIFO queue to invoke an AWS Lambda function for processing.

### Explanation

To ensure that orders are processed in the order that they are received, the best solution is to use an Amazon SQS FIFO (First-In-First-Out) queue. This type of queue maintains the exact order in which messages are sent and received. In this case, the application can send information about new orders to an Amazon API Gateway REST API, which can then use an API Gateway integration to send a message to an Amazon SQS FIFO queue for processing. The queue can then be configured to invoke an AWS Lambda function to perform the necessary processing on each order. This ensures that orders are processed in the exact order in which they are received.

## Question 14

You are building an automated transcription service in which "Amazon EC2 worker" instances process an uploaded audio file and generate a text file. You must store both of these files in the same durable storage until the text file is retrieved, but you do not know what the storage capacity requirements are. Which storage option is both cost-efficient and scalable?

### Options

- Multiple Amazon EBS volume with snapshots
- A single Amazon Glacier Vault
- __A single Amazon S3 bucket__
- Multiple instance stores

### Correct Answer

A single Amazon S3 bucket

### Explanation

Amazon S3 is a highly durable and scalable object storage service that can store objects of any size. It is also very cost-efficient, especially for storing large amounts of data. You can store both the audio and text files in the same S3 bucket. This will make it easy to manage your files and ensure that they are always available together.

## Question 15

A company has several web servers that need to frequently access a common Amazon RDS MySQL Multi-AZ DB instance. The company wants a secure method for the web servers to connect to the database while meeting a security requirement to rotate user credentials frequently. Which of the following options is correct?

### Options

- Store the database user credentials in files encrypted with AWS Key Management Service (AWS KMS) on the web server file system. The web server should be able to decrypt the files and access the database.
- __Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to access AWS Secrets Manager.__
- Store the database user credentials in AWS Systems Manager OpsCenter. Grant the necessary IAM permissions to allow the web servers to access OpsCenter.
- Store the database user credentials in a secure Amazon S3 bucket. Grant the necessary IAM permissions to allow the web servers to retrieve credentials and access the database.

### Correct Answer

Store the database user credentials in AWS Secrets Manager. Grant the necessary IAM permissions to allow the web servers to access AWS Secrets Manager.

### Explanation

AWS Secrets Manager is a secure and highly scalable service that allows you to store, manage, and rotate secrets such as database passwords, API keys, and SSH keys. Secrets Manager can be used to store database user credentials for your web servers. When you store database user credentials in Secrets Manager, you can rotate the credentials automatically on a regular schedule. This helps to protect your database from unauthorized access.

## Question 16

A mobile company needs to review its AWS Cloud deployment to ensure that its Amazon S3 buckets do not have unauthorized configuration changes. What should a solutions architect do to accomplish this goal?

### Options

- __Turn on AWS Config with the appropriate rules.__
- Turn on AWS Trusted Advisor with the appropriate checks.
- Turn on Amazon Inspector with the appropriate assessment template.
- Turn on Amazon S3 server access logging. Configure Amazon EventBridge (Amazon Cloud Watch Events).

### Correct Answer

Turn on AWS Config with the appropriate rules.

### Explanation

AWS Config is a service that tracks changes to your AWS resources. You can use Config to track changes to your Amazon S3 bucket configuration, including changes to bucket policies. This will allow you to see if any unauthorized changes have been made to your bucket configuration.

## Question 17

A financial company has more than 5 TB of file data on Windows file servers that run on premises. Users and applications interact with the data each day. The company is moving its Windows workloads to AWS. As the company continues this process, the company requires access to AWS and on-premises file storage with minimum latency. The company needs a solution that minimizes operational overhead and requires no significant changes to the existing file access patterns. The company uses an AWS Site-to-Site VPN connection for connectivity to AWS. Which of the following options is correct?

### Options

- Deploy and configure an Amazon S3 File Gateway on premises. Move the on-premises file data to the S3 File Gateway. Reconfigure the on-premises workloads and the cloud workloads to use the S3 File Gateway.
- Deploy and configure Amazon FSx for Windows File Server on AWS. Deploy and configure an Amazon FSx File Gateway on premises. Move the on-premises file data to the FSx File Gateway. Configure the cloud workloads to use FSx for Windows File Server on AWS. Configure the on-premises workloads to use the FSx File Gateway.
- __Deploy and configure Amazon FSx for Windows File Server on AWS. Move the on-premises file data to FSx for Windows File Server. Reconfigure the workloads to use FSx for Windows File Server on AWS.__
- Deploy and configure an Amazon S3 File Gateway on premises. Move the on-premises file data to Amazon S3. Reconfigure the workloads to use either Amazon S3 directly or the S3 File Gateway. depending on each workload's location.

### Correct Answer

Deploy and configure Amazon FSx for Windows File Server on AWS. Move the on-premises file data to FSx for Windows File Server. Reconfigure the workloads to use FSx for Windows File Server on AWS.

### Explanation

The company needs a solution that minimizes operational overhead and requires no significant changes to the existing file access patterns. The solution should also provide access to AWS and on-premises file storage with minimum latency. Amazon FSx for Windows File Server is a fully managed file system that provides native Windows compatibility and high performance. It can be used to store and access file data from both on-premises and cloud workloads. Amazon FSx File Gateway is a hybrid file solution that allows on-premises applications to access Amazon S3 file storage over the SMB protocol. This can be used to provide low-latency access to on-premises applications to file data that is stored in Amazon S3. In this case, the solutions architect should deploy and configure Amazon FSx for Windows File Server on AWS. They should then deploy and configure an Amazon FSx File Gateway on premises. The on-premises file data should be moved to the FSx File Gateway. The cloud workloads should be configured to use Amazon FSx for Windows File Server on AWS. The on-premises workloads should be configured to use the FSx File Gateway.

## Question 18

An IT company runs workloads on AWS. The company needs to connect to a service from an external provider. The service is hosted in the provider's VPC. According to the company’s security team, the connectivity must be private and must be restricted to the target service. The connection must be initiated only from the company’s VPC. Which of the following options is correct?

### Options

- Ask the provider to create a virtual private gateway in its VPC. Use AWS PrivateLink to connect to the target service.
- __Ask the provider to create a VPC endpoint for the target service. Use AWS PrivateLink to connect to the target service.__
- Create a NAT gateway in a public subnet of the company’s VPUpdate the route table to connect to the target service.
- Create a VPC peering connection between the company's VPC and the provider's VPC. Update the route table to connect to the target service.

### Correct Answer

Ask the provider to create a VPC endpoint for the target service. Use AWS PrivateLink to connect to the target service.

### Explanation

AWS PrivateLink enables private connectivity between VPCs, AWS services, and services hosted by other AWS customers. PrivateLink connections are established using private IP addresses, and traffic flows within the AWS network.

## Question 19

XYZ company uses AWS Organizations to manage multiple AWS accounts for different departments. The management account has an Amazon S3 bucket that contains project reports. The company wants to limit access to this S3 bucket to only users of accounts within the organization in AWS Organizations without operational overhead? Which of the following options is correct?

### Options

- Use AWS CloudTrail to monitor the CreateAccount, InviteAccountToOrganization, LeaveOrganization, and RemoveAccountFromOrganization events. Update the S3 bucket policy accordingly.
- __Add the aws PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy.__
- Create an organizational unit (OU) for each department. Add the aws:PrincipalOrgPaths global condition key to the S3 bucket policy.
- Tag each user that needs access to the S3 bucket. Add the aws:PrincipalTag global condition key to the S3 bucket policy.

### Correct Answer

Add the aws PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy.

### Explanation

AWS:PrincipalOrgID – Simplifies specifying the Principal element in a resource-based policy. This global key provides an alternative to listing all the account IDs for all AWS accounts in an organization. Instead of listing all of the accounts that are members of an organization, you can specify the organization ID in the Condition element. aws:PrincipalOrgPaths – Use this condition key to match members of a specific organization root, an OU, or its children. The aws:PrincipalOrgPaths condition key returns true when the principal (root user, IAM user, or role) making the request is in the specified organization path. A path is a text representation of the structure of an AWS Organizations entity. Reference: https://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions_overview.html

## Question 20

A solutions architect is designing a two-tier web application. The application consists of a public-facing web tier hosted on Amazon EC2 in public subnets. The database tier consists of Microsoft SQL Server running on Amazon EC2 in a private subnet. Security is a high priority for the company. How should security groups be configured in this situation? (Select two.)

### Options

- Configure the security group for the database tier to allow inbound traffic on ports 443 and 1433 from the security group for the web tier.
- __Configure the security group for the database tier to allow inbound traffic on port 1433 from the security group for the web tier.__
- Configure the security group for the web tier to allow outbound traffic on port 443 from 0.0.0.0/0.
- Configure the security group for the database tier to allow outbound traffic on ports 443 and 1433 to the security group for the web tier.
- __Configure the security group for the web tier to allow inbound traffic on port 443 from 0.0.0.0/0.__

### Correct Answer

Configure the security group for the database tier to allow inbound traffic on port 1433 from the security group for the web tier.

Configure the security group for the web tier to allow inbound traffic on port 443 from 0.0.0.0/0.

### Explanation

The security group for the web tier should allow inbound traffic on port 443 from 0.0.0.0/0. This is because the web tier will be exposed to the public internet, and it needs to be able to accept incoming HTTPS connections. The security group for the database tier should allow inbound traffic on port 1433 from the security group for the web tier. This is because the database tier is only accessible from the web tier, and it needs to be able to accept incoming connections from the web tier on port 1433.

## Question 21

An IT company's HTTP application is behind a Network Load Balancer (NLB). The NLB's target group is configured to use an Amazon EC2 Auto Scaling group with multiple EC2 instances that run the web service. The company notices that the NLB is not detecting HTTP errors for the application. These errors require a manual restart of the EC2 instances that run the web service. The company needs to improve the application's availability without writing custom scripts or code. Which of the following options is correct?

### Options

- Enable HTTP health checks on the NLB, supplying the URL of the company's application.
- Create an Amazon Cloud Watch alarm that monitors the UnhealthyHostCount metric for the NLB. Configure an Auto Scaling action to replace unhealthy instances when the alarm is in the ALARM state.
- __Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Configure an Auto Scaling action to replace unhealthy instances.__
- Add a cron job to the EC2 instances to check the local application's logs once each minute. If HTTP errors are detected. the application will restart.

### Correct Answer

Replace the NLB with an Application Load Balancer. Enable HTTP health checks by supplying the URL of the company's application. Configure an Auto Scaling action to replace unhealthy instances.

### Explanation

The NLB can only perform TCP health checks, which do not look at the application's response code. In order to detect HTTP errors, the NLB needs to be replaced with an Application Load Balancer (ALB). The ALB can perform HTTP health checks, which will detect HTTP errors in the application. The ALB can also be configured to replace unhealthy instances, which will improve the application's availability.

## Question 22

A company uses AWS Organizations to create dedicated AWS accounts for each business unit to manage each business unit's account independently upon request. The root email recipient missed a notification that was sent to the root user email address of one account. The company wants to ensure that all future notifications are not missed. Future notifications must be limited to account administrators. Which of the following options is correct?

### Options

- Configure the company’s email server to forward notification email messages that are sent to the AWS account root user email address to all users in the organization.
- Configure all existing AWS accounts and all newly created accounts to use the same root user email address. Configure AWS account alternate contacts in the AWS Organizations console or programmatically.
- __Configure all AWS account root user email addresses as distribution lists that go to a few administrators who can respond to alerts. Configure AWS account alternate contacts in the AWS Organizations console or programmatically.__
- Configure all AWS account root user email messages to be sent to one administrator who is responsible for monitoring alerts and forwarding those alerts to the appropriate groups.

### Correct Answer

Configure all AWS account root user email addresses as distribution lists that go to a few administrators who can respond to alerts. Configure AWS account alternate contacts in the AWS Organizations console or programmatically.

### Explanation

Configure all AWS account root user email addresses as distribution lists that go to a few administrators who can respond to alerts. Configure AWS account alternate contacts in the AWS Organizations console or programmatically.

## Question 23

You have 10 CloudFormation templates; each template is for a different application architecture. This architecture varies between your web apps and your gaming apps. What determines the cost of using the CloudFormation templates. Which of the following options is correct?

### Options

- 0.20$ per template per month
- The time it takes to build the architecture with Cloud Formation.
- 0.101$ per template per month
- __Cloud Formation does not have any additional cost but you are charged for the underlying resources it builds.__

### Correct Answer

Cloud Formation does not have any additional cost but you are charged for the underlying resources it builds.

### Explanation

The cost of using CloudFormation templates is determined by the underlying resources that are created. The time it takes to build the architecture with CloudFormation does not affect the cost. CloudFormation does not have any additional cost.

## Question 24

A company needs to retain application log files for a critical application for 10 years. The application team regularly accesses logs from the past month for troubleshooting, but logs older than 1 month are rarely accessed. The application generates more than 10 TB of logs per month. Which storage option meets these requirements MOST cost-effectively?

### Options

- __Store the logs in Amazon S3. Use S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.__
- Store the logs in Amazon CloudWatch Logs. Use AWS Backup to move logs more than 1 month old to S3 Glacier Deep Archive.
- Store the logs in Amazon S3. Use AWS Backup to move logs more than 1 month old to S3 Glacier Deep Archive.
- Store the logs in Amazon CloudWatch Logs. Use Amazon S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.

### Correct Answer

Store the logs in Amazon S3. Use S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.

### Explanation

Store the logs in Amazon S3. Use S3 Lifecycle policies to move logs more than 1-month-old to S3 Glacier Deep Archive) would meet these requirements in the most cost-effective manner.

## Question 25

XYZ company collects data for temperature, humidity, and atmospheric pressure in cities across multiple continents. The average volume of data that the company collects from each site daily is 500 GB. Each site has a high-speed Internet connection. The XYZ company wants to aggregate the data from all these global sites as quickly as possible in a single Amazon S3 bucket. The solution must minimize operational complexity. Which of the following options is correct?

### Options

- Upload the data from each site to an S3 bucket in the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3 bucket. Then remove the data from the origin S3 bucket.
- Schedule AWS Snowball Edge Storage Optimized device jobs daily to transfer data from each site to the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3 bucket.
- Upload the data from each site to an Amazon EC2 instance in the closest Region. Store the data in an Amazon Elastic Block Store (Amazon EBS) volume. At regular intervals, take an EBS snapshot and copy it to the Region that contains the destination S3 bucket. Restore the EBS volume in that Region.
- __Turn on S3 Transfer Acceleration on the destination S3 bucket. Use multipart uploads to directly upload site data to the destination S3 bucket.__

### Correct Answer

Turn on S3 Transfer Acceleration on the destination S3 bucket. Use multipart uploads to directly upload site data to the destination S3 bucket.

### Explanation

AWS Snowball Edge with AWS Snowball Edge Storage Optimized devices and AWS Snowball for egress

Here's why this option is ideal:

Offline Data Transfer: Once the data is collected on the Edge device, it can be securely transferred to S3 using Snowball for egress. Snowball devices are physical storage units shipped to AWS by the customer. This offline data transfer minimizes reliance on high-speed internet connections at each site, potentially reducing costs associated with constant high-bandwidth usage.

High-Speed Local Data Collection: Snowball Edge devices are deployed on-site at each location. They have high-speed storage and local processing capabilities. This allows for efficient collection and temporary storage of the large daily data volume (500 GB) from each site.

Reduced Operational Complexity: This solution minimizes operational complexity because:

Snowball Edge devices are preconfigured and managed by AWS, reducing the need for on-site IT expertise for managing the data collection hardware.

Offline data transfer reduces reliance on managing high-bandwidth internet connections at each site.

Centralized Storage: Snowball uploads the data to a designated S3 bucket in the AWS cloud. This provides a central location for all the aggregated data from all the global sites.

Other options and why they are not ideal:

High-Speed Internet with Direct S3 Upload: While high-speed internet connections exist at each site, constantly uploading 500 GB of data daily can be expensive and may not be feasible depending on data transfer costs.

AWS Direct Connect: Setting up and managing dedicated leased lines for each site can be complex and expensive.

AWS S3 Transfer Acceleration: This service can optimize data transfer speeds, but it still relies on high-bandwidth internet connections at each site, potentially leading to high costs.

Overall, Snowball Edge with Snowball for egress offers a cost-effective and operationally simple solution for XYZ company to collect and aggregate large data volumes from geographically dispersed locations with high-speed local data collection, offline data transfer, and centralized storage in S3.

## Question 26

A company wants to migrate its existing on-premises monolithic application to AWS. The company wants to keep as much of the front-end code and the backend code as possible. However, the company wants to break the application into smaller applications. A different team will manage each application. The company needs a highly scalable solution that minimizes operational overhead. Which of the following options is correct?

### Options

- __Host the application on Amazon Elastic Container Service (Amazon ECS). Set up an Application Load Balancer with Amazon ECS as the target.__
- Host the application on AWS Lambda. Integrate the application with Amazon API Gateway.
- Host the application on Amazon EC2 instances. Set up an Application Load Balancer with EC2 instances in an Auto Scaling group as targets.

### Correct Answer

Host the application on Amazon Elastic Container Service (Amazon ECS). Set up an Application Load Balancer with Amazon ECS as the target.

### Explanation

The best solution for the company is to host the application on Amazon Elastic Container Service (ECS) and set up an Application Load Balancer (ALB) with ECS as the target. Amazon ECS is a container orchestration service that makes it easy to run, scale, and deploy containerized applications. ECS allows you to package your code and dependencies in containers, which are lightweight and portable. You can then deploy your containers to ECS and ECS will manage them for you. Amazon ALB is a load balancer that distributes traffic across multiple ECS tasks. ALB can scale your application up and down automatically based on demand.

## Question 27

Which of the following Amazon S3 Storage Classes offer 99.999999999% (11 x 9s) durability?

### Options

- __Standard, Standard-Infrequent Access, One Zone-Infrequent Access__
- Standard, Glacier, Reduced Redundancy Storage
- Standard-Infrequent Access, One Zone-Infrequent Access, Reduced Redundancy Storage
- Reduced Redundancy Storage, Standard, One Zone-Infrequent Access

### Correct Answer

Standard, Standard-Infrequent Access, One Zone-Infrequent Access

### Explanation

Standard, Standard-Infrequent Access, One Zone-Infrequent Access

## Question 28

How can software determine the public and private IP addresses of the Amazon Elastic Cloud Compute instance that it is running on? Which of the following options is correct?

### Options

- __Query the local instance metadata__
- Query the appropriate Amazon CloudWatch metric
- Use an ipconfig or ifconfig command
- Query the local instance userdata

### Correct Answer

Query the local instance metadata

### Explanation

To determine the public and private IP addresses of the Amazon Elastic Cloud Compute (Amazon EC2) instance that it is running on, software can query the local instance metadata. The instance metadata is a dynamic data structure that provides information about the instance, such as its ID, type, AMI, and network interfaces.

## Question 29

A solutions architect must design a highly available infrastructure for a website. The website is powered by Windows web servers that run on Amazon EC2 instances. The solutions architect must implement a solution that can mitigate a large-scale DDoS attack that originates from thousands of IP addresses. Downtime is not acceptable for the website. Which actions should the solutions architect take to protect the website from such an attack? (Choose two.)

### Options

- Use EC2 Spot Instances in an Auto Scaling group with a target tracking scaling policy that is set to 80% CPU utilization.
- Use an AWS Lambda function to automatically add attacker IP addresses to VPC network ACLs.
- __Configure the website to use Amazon CloudFront for both static and dynamic content.__
- Configure Amazon GuardDuty to automatically block the attackers.
- __Use AWS Shield Advanced to stop the DDoS attack.__

### Correct Answer

Configure the website to use Amazon CloudFront for both static and dynamic content.

Use AWS Shield Advanced to stop the DDoS attack.

### Explanation

AWS Shield Advanced is a managed DDoS protection service that helps protect your applications from DDoS attacks. Shield Advanced can detect and mitigate a wide range of DDoS attacks, including volumetric attacks, application layer attacks, and new and emerging attacks. Amazon CloudFront is a content delivery network (CDN) that can help you deliver your website's content to users around the world with low latency and high availability. CloudFront can also help protect your website from DDoS attacks by distributing your content across a global network of servers.

## Question 30

An application runs on an Amazon EC2 instance in a VPC. The application processes logs that are stored in an Amazon S3 bucket. The EC2 instance needs to access the S3 bucket without connectivity to the internet. Which solution will provide private network connectivity to Amazon S3?

### Options

- __Create a gateway VPC endpoint to the S3 bucket.__
- Stream the logs to Amazon CloudWatch Logs. Export the logs to the S3 bucket.
- Create an Amazon API Gateway API with a private link to access the S3 endpoint.
- Create an instance profile on Amazon EC2 to allow S3 access.

### Correct Answer

Create a gateway VPC endpoint to the S3 bucket.

### Explanation

VPC Endpoint for Amazon S3: Create a VPC endpoint for Amazon S3 in your VPC. A VPC endpoint allows you to privately connect your VPC to supported AWS services. By creating a VPC endpoint for Amazon S3, you can access S3 buckets without requiring internet gateway, NAT devices. Once the VPC endpoint is created, the EC2 instance within the VPC can securely access the S3 bucket without going over the public internet. It's important to note that the VPC endpoint for Amazon S3 provides access to all S3 buckets within the AWS region. If you want to restrict access to specific S3 buckets, you can use bucket policies or IAM policies to control access further.

## Question 31

A company is preparing to store confidential data in Amazon S3. For compliance reasons, the data must be encrypted at rest. Encryption key usage must be logged for auditing purposes. Keys must be rotated every year. Which of the following options is correct?

### Options

- Server-side encryption with AWS KMS keys (SSE-KMS) with manual rotation
- Server-side encryption with Amazon S3 managed keys (SSE-S3)
- __Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation__
- Server-side encryption with customer-provided keys (SSE-C)

### Correct Answer

Server-side encryption with AWS KMS keys (SSE-KMS) with automatic rotation

### Explanation

SSE-KMS is the most secure way to encrypt data in Amazon S3. It uses AWS KMS, which is a highly secure key management service that is managed by AWS. AWS KMS logs all key usage, so the company can meet its compliance requirements. AWS KMS also rotates keys automatically, so the company does not have to worry about manually rotating keys.

## Question 32

An IT company is developing a two-tier web application on AWS. The company's developers have deployed the application on an Amazon EC2 instance that connects directly to a backend Amazon RDS database. The company must not hardcode database credentials in the application. The company must also implement a solution to automatically rotate the database credentials on a regular basis. Which of the following options is correct?

### Options

- Store the database credentials as encrypted parameters in AWS Systems Manager Parameter Store. Turn on automatic rotation for the encrypted parameters. Attach the required permission to the EC2 role to grant access to the encrypted parameters.
- Store the database credentials in a configuration file in an encrypted Amazon S3 bucket. Use Amazon EventBridge (Amazon CloudWatch Events) rules to run a scheduled AWS Lambda function that updates the RDS credentials and the credentials in the configuration file at the same time. Use S3 Versioning to ensure the ability to fall back to previous values.
- __Store the database credentials as a secret in AWS Secrets Manager. Turn on automatic rotation for the secret. Attach the required permission to the EC2 role to grant access to the secret.__
- Store the database credentials in the instance metadata. Use Amazon EventBridge (Amazon CloudWatch Events) rules to run a scheduled AWS Lambda function that updates the RDS credentials and instance metadata at the same time.

### Correct Answer

Store the database credentials as a secret in AWS Secrets Manager. Turn on automatic rotation for the secret. Attach the required permission to the EC2 role to grant access to the secret.

### Explanation

Store the database credentials as a secret in AWS Secrets Manager. Turn on automatic rotation for the secret. Attach the required permission to the EC2 role to grant access to the secret.

## Question 33

A company’s website provides users with downloadable historical performance reports. The website needs a solution that will scale to meet the company’s website demands globally. The solution should be cost-effective, limit the provisioning of infrastructure resources, and provide the fastest possible response time. Which of the following options is correct?

### Options

- Application Load Balancer with Amazon EC2 Auto Scaling
- __Amazon CloudFront and Amazon S3__
- AWS Lambda and Amazon DynamoDB
- Amazon Route 53 with internal Application Load Balancers

### Correct Answer

Amazon CloudFront and Amazon S3

### Explanation

Amazon CloudFront is a content delivery network (CDN) that can be used to deliver static and dynamic web content, video streams, and APIs around the world, securely and at scale. CloudFront works by caching content at edge locations around the world, which are closer to end users than the origin server. This results in faster response times and lower latency for users. Amazon S3 is an object storage service that offers industry-leading scalability, data availability, security, and performance. S3 is a good choice for storing downloadable historical performance reports because it is highly scalable and cost-effective.

## Question 34

A solutions architect is designing the cloud architecture for a new application being deployed on AWS. The process should run in parallel while adding and removing application nodes as needed based on the number of jobs to be processed. The processor application is stateless. The solutions architect must ensure that the application is loosely coupled and the job items are durably stored. Which of the following options is correct?

### Options

- Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch configuration that uses the AMI. Create an Auto Scaling group using the launch configuration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on CPU usage.
- Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch configuration that uses the AMI. Create an Auto Scaling group using the launch configuration. Set the scaling policy for the Auto Scaling group to add and remove nodes based on network usage.
- __Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of items in the SQS queue.__
- Create an Amazon SNS topic to send the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of messages published to the SNS topic.

### Correct Answer

Create an Amazon SQS queue to hold the jobs that need to be processed. Create an Amazon Machine Image (AMI) that consists of the processor application. Create a launch template that uses the AMI. Create an Auto Scaling group using the launch template. Set the scaling policy for the Auto Scaling group to add and remove nodes based on the number of items in the SQS queue.

### Explanation

Durable job storage: Amazon SQS provides a message queue that guarantees messages are persisted even if the queue server fails. This ensures jobs aren't lost between processing cycles.

Dynamic scaling based on workload: By setting the scaling policy to react to the number of items in the SQS queue, the Auto Scaling group can add or remove application servers based on the current workload. This facilitates parallel processing of jobs.

Loose coupling: SQS decouples the job submission process from the application instances. The application instances simply pull jobs from the queue for processing, regardless of where they came from. SNS, in this scenario, wouldn't be directly involved in managing the job queue.

## Question 35

A gaming company is designing a highly available architecture. The application runs on a modified Linux kernel and supports only UDP-based traffic. The company needs the front-end tier to provide the best possible user experience. That tier must have low latency, route traffic to the nearest edge location, and provide static IP addresses for entry into the application endpoints. What should a solutions architect do to meet these requirements?

### Options

- Configure Amazon Route 53 to forward requests to an Application Load Balancer. Use AWS Lambda for the application in AWS Application Auto Scaling.
- Configure Amazon CloudFront to forward requests to a Network Load Balancer. Use AWS Lambda for the application in an AWS Application Auto Scaling group.
- Configure Amazon API Gateway to forward requests to an Application Load Balancer. Use Amazon EC2 instances for the application in an EC2 Auto Scaling group.
- __Configure AWS Global Accelerator to forward requests to a Network Load Balancer. Use Amazon EC2 instances for the application in an EC2 Auto Scaling group.__

### Correct Answer

Configure AWS Global Accelerator to forward requests to a Network Load Balancer. Use Amazon EC2 instances for the application in an EC2 Auto Scaling group.

### Explanation

AWS Global Accelerator is a service that improves the performance and availability of applications for global users by directing traffic to the optimal regional endpoint based on several factors, including the user's location, the health of the endpoint, and the endpoint weights that you configure. Global Accelerator supports UDP-based traffic and provides static IP addresses for entry into the application endpoints. It also has low latency, which is important for gaming applications.

## Question 36

A new hospital recently deployed a RESTful API with Amazon API Gateway and AWS Lambda. The hospital uses API Gateway and Lambda to upload reports that are in PDF format and JPEG format. The new hospital needs to modify the Lambda code to identify protected health information (PHI) in the reports. Which of the following options is correct?

### Options

- Use Amazon Textract to extract the text from the reports. Use Amazon SageMaker to identify the PHI from the extracted text.
- Use existing Python libraries to extract the text from the reports and to identify the PHI from the extracted text.
- Use Amazon Rekognition to extract the text from the reports. Use Amazon Comprehend Medical to identify the PHI from the extracted text.
- __Use Amazon Textract to extract the text from the reports. Use Amazon Comprehend Medical to identify the PHI from the extracted text.__

### Correct Answer

Use Amazon Textract to extract the text from the reports. Use Amazon Comprehend Medical to identify the PHI from the extracted text.

### Explanation

The hospital needs to modify the Lambda code to identify PHI in the reports. Amazon Textract can be used to extract text from PDF and JPEG files. Amazon Comprehend Medical can be used to identify PHI in the extracted text. Both Amazon Textract and Amazon Comprehend Medical are fully managed services, which means that the hospital does not have to worry about the operational overhead of managing the services. Amazon SageMaker is a machine learning platform that can be used to train and deploy machine learning models. However, it requires more operational overhead than Amazon Comprehend Medical. Amazon Rekognition is a computer vision service that can be used to identify objects in images. However, it cannot be used to identify PHI in text.

## Question 37

We have a client who is considering a move to AWS. In establishing a new account, what is the first thing the company should do?

### Options

- __Set up an account using their company email address.__
- Set up an account via ELB.
- Set up an account using Cloud Search.
- Set up an account via EC2

### Correct Answer

Set up an account using their company email address.

### Explanation

The first thing a company should do when setting up a new AWS account is to set up an account using their company email address. This will allow them to receive important account notifications and billing information from AWS.

## Question 38

A document management company runs its infrastructure on AWS and has a registered base of 700,000 users for its document management application. The company intends to create a product that converts large .pdf files to .jpg image files. The .pdf files average 5 MB in size. The company needs to store the original files and the converted files. A solutions architect must design a scalable solution to accommodate demand that will grow rapidly over time. Which option satisfies these requirements MOST affordably?

### Options

- Save the .pdf files to Amazon DynamoDUse the DynamoDB Streams feature to invoke an AWS Lambda function to convert the files to .jpg format and store them back in DynamoDB.
- __Save the .pdf files to Amazon S3. Configure an S3 PUT event to invoke an AWS Lambda function to convert the files to .jpg format and store them back in Amazon S3.__
- Upload the .pdf files to an AWS Elastic Beanstalk application that includes Amazon EC2 instances, Amazon Elastic File System (Amazon EFS) storage, and an Auto Scaling group. Use a program in the EC2 instances to convert the file to .jpg format. Save the .pdf files and the .jpg files in the EBS store.
- Upload the .pdf files to an AWS Elastic Beanstalk application that includes Amazon EC2 instances, Amazon Elastic Block Store (Amazon EBS) storage, and an Auto Scaling group. Use a program in the EC2 instances to convert the files to .jpg format. Save the .pdf files and the .jpg files in the EBS store.

### Correct Answer

Save the .pdf files to Amazon S3. Configure an S3 PUT event to invoke an AWS Lambda function to convert the files to .jpg format and store them back in Amazon S3.

### Explanation

This solution is most cost-effective because it uses Amazon S3, which is a highly scalable and durable object storage service. Amazon S3 also offers a pay-as-you-go pricing model, which means that the company only pays for the storage and bandwidth that it uses.

## Question 39

A data processing company has an AWS Glue extract, transform, and load (ETL) job that runs every day at the same time. The job processes XML data that is in an Amazon S3 bucket. New data is added to the S3 bucket every day. A solutions architect notices that AWS Glue is processing all the data during each run. What should the solutions architect do to prevent AWS Glue from reprocessing old data?

### Options

- Use a FindMatches machine learning (ML) transform.
- Edit the job to delete data after the data is processed.
- Edit the job by setting the NumberOfWorkers field to 1.
- __Edit the job to use job bookmarks.__

### Correct Answer

Edit the job to use job bookmarks.

### Explanation

The solutions architect should edit the job to use job bookmarks. Job bookmarks allow AWS Glue to keep track of the data that has already been processed and only process new data during each run. To use job bookmarks, you need to specify a bookmark key in your AWS Glue script. The bookmark key is a column in your data that is unique to each row. AWS Glue will use the bookmark key to track which rows have already been processed.

## Question 40

A company is running a popular social media website. The website gives users the ability to upload images to share with other users. The company wants to make sure that the images do not contain inappropriate content. The company needs a solution that minimizes development effort. Which of the following options is correct?

### Options

- __Use Amazon Rekognition to detect inappropriate content. Use human review for low-confidence predictions.__
- Use AWS Fargate to deploy a custom machine learning model to detect inappropriate content. Use ground truth to label low-confidence predictions.
- Use Amazon SageMaker to detect inappropriate content. Use ground truth to label low-confidence predictions.
- Use Amazon Comprehend to detect inappropriate content. Use human review for low-confidence predictions.

### Correct Answer

Use Amazon Rekognition to detect inappropriate content. Use human review for low-confidence predictions.

### Explanation

Amazon Rekognition is a machine learning service that can be used to detect inappropriate content in images. It is a good choice for this use case because it is a managed service, which means that the company does not need to develop or manage their own machine learning model. The company can use Amazon Rekognition to detect inappropriate content in images uploaded to the social media website. If the Rekognition model is not confident in its prediction, the company can use human review to confirm the prediction. This will help to ensure that the social media website does not contain inappropriate content.

## Question 41

A company wants to reduce the cost of its existing three-tier web architecture. The web, application, and database servers are running on Amazon EC2 instances for the development, test, and production environments. The EC2 instances average 30% CPU utilization during peak hours and 10% CPU utilization during non-peak hours. The production EC2 instances run 24 hours a day. The development and test EC2 instances run for at least 8 hours each day. The company plans to implement automation to stop the development and test EC2 instances when they are not in use. Which EC2 instance purchasing solution will meet the company's requirements MOST cost-effectively?

### Options

- Use Spot blocks for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.
- Use On-Demand Instances for the production EC2 instances. Use Spot blocks for the development and test EC2 instances.
- __Use Reserved Instances for the production EC2 instances. Use On-Demand Instances for the development and test EC2 instances.__
- Use Spot Instances for the production EC2 instances. Use Reserved Instances for the development and test EC2 instances.

### Correct Answer

Use Reserved Instances for the production EC2 instances. Use On-Demand Instances for the development and test EC2 instances.

### Explanation

Production EC2 instances should use Reserved Instances because they offer the lowest price per hour if you commit to a 1 or 3 year term. The production EC2 instances run 24 hours a day, so you can get the most benefit from Reserved Instances. Development and test EC2 instances should use On-Demand Instances because they offer the most flexibility. The development and test EC2 instances run for at least 8 hours each day, but they may not be used all the time. On-Demand Instances allow you to pay only for the instances that you use.

## Question 42

A Web company is preparing to deploy a new serverless workload. A solutions architect must use the principle of least privilege to configure permissions that will be used to run an AWS Lambda function. An Amazon EventBridge (Amazon CloudWatch Events) rule will invoke the function. Which of the following options is correct?

### Options

- Add an execution role to the function with lambda:InvokeFunction as the action and * as the principal.
- __Add a resource-based policy to the function with lambda:InvokeFunction as the action and Service: events.amazonaws.com as the principal.__
- Add an execution role to the function with lambda:InvokeFunction as the action and Service: lambda.amazonaws.com as the principal.
- Add a resource-based policy to the function with lambda:* as the action and Service: events.amazonaws.com as the principal.

### Correct Answer

Add a resource-based policy to the function with lambda:InvokeFunction as the action and Service: events.amazonaws.com as the principal.

### Explanation

To use the principle of least privilege to configure permissions for a Lambda function, you should only grant the function the permissions that it needs to perform its task. In this case, the Lambda function only needs the permission to be invoked by Amazon EventBridge.

## Question 43

An IT company has two accounts for perform testing and each account has a single VPC: VPC-TEST100 and VPC-TEST200. The operations team require a method of securely copying files between Amazon EC2 instances in these VPCs. The connectivity should not have any single points of failure or bandwidth constraints. Which of the following options is correct?

### Options

- Attach a Direct Connect gateway to VPC-TEST100 and VPC-TEST200 and enable routing.
- __Create a VPC peering connection between VPC-TEST100 and VPC-TEST200.__
- Create a VPC gateway endpoint for each EC2 instance and update route tables.
- Attach a virtual private gateway to VPC-TEST100 and VPC-TEST200 and enable routing.

### Correct Answer

Create a VPC peering connection between VPC-TEST100 and VPC-TEST200.

### Explanation

In this case, the company has two accounts, so they need to create a VPC peering connection between VPC-TEST100 in account 1 and VPC-TEST200 in account 2. This will allow the operations team to securely copy files between EC2 instances in these VPCs without any single points of failure or bandwidth constraints.

## Question 44

You want to implement a HPC ( High performance computing ) system with low-latency network performance. In order to establish this, which AWS feature can be used?

### Options

- __Placement groups__
- EC2 and DynamoDB
- ElasticMapReduce
- ELB and Auto scaling

### Correct Answer

Placement groups

### Explanation

Placement groups are the AWS feature that can be used to implement a HPC system with low-latency network performance. Placement groups allow you to group EC2 instances together in the same Availability Zone (AZ). This ensures that the instances are close to each other on the physical network, which can improve network performance. Placement groups are often used for HPC applications because they require low-latency communication between the instances.

## Question 45

In the event of a planned or an unplanned outage of your primary DB instance, Amazon RDS automatically switches to a standby replica in another Availability Zone if you have enabled_________.

### Options

- More than one read replica
- More than one write replica
- __Multiple Availability Zones__
- Multi Regions Deployment

### Correct Answer

Multiple Availability Zones

### Explanation

Amazon Relational Database Service (RDS) Multi-AZ deployments provide high availability and disaster recovery for your database instances. When you enable Multi-AZ, RDS automatically creates and maintains a standby replica of your database instance in another Availability Zone. If there is a planned or unplanned outage of your primary database instance, RDS will automatically switch to the standby replica. This ensures that your database is always available and that you do not lose any data.

## Question 46

XYZ company uses AWS Organizations to manage multiple AWS accounts for different departments. The management account has an Amazon S3 bucket that contains project reports. The company wants to limit access to this S3 bucket to only users of accounts within the organization in AWS Organizations without operational overhead? Which of the following options is correct?

### Options

- Create an organizational unit (OU) for each department. Add the aws:PrincipalOrgPaths global condition key to the S3 bucket policy.
- Tag each user that needs access to the S3 bucket. Add the aws:PrincipalTag global condition key to the S3 bucket policy.
- Use AWS CloudTrail to monitor the CreateAccount, InviteAccountToOrganization, LeaveOrganization, and RemoveAccountFromOrganization events. Update the S3 bucket policy accordingly.
- __Add the aws PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy.__

### Correct Answer

Add the aws PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy.

### Explanation

AWS:PrincipalOrgID – Simplifies specifying the Principal element in a resource-based policy. This global key provides an alternative to listing all the account IDs for all AWS accounts in an organization. Instead of listing all of the accounts that are members of an organization, you can specify the organization ID in the Condition element. aws:PrincipalOrgPaths – Use this condition key to match members of a specific organization root, an OU, or its children. The aws:PrincipalOrgPaths condition key returns true when the principal (root user, IAM user, or role) making the request is in the specified organization path. A path is a text representation of the structure of an AWS Organizations entity. Reference: https://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions_overview.html

## Question 47

An ecommerce company wants to launch a one-deal-a-day website on AWS. Each day will feature exactly one product on sale for a period of 24 hours. The company wants to be able to handle millions of requests each hour with millisecond latency during peak hours. Which of the following options is correct?

### Options

- __Use an Amazon S3 bucket to host the website's static content. Deploy an Amazon CloudFront distribution. Set the S3 bucket as the origin. Use Amazon API Gateway and AWS Lambda functions for the backend APIs. Store the data in Amazon DynamoDB.__
- Use Amazon S3 to host the full website in different S3 buckets. Add Amazon CloudFront distributions. Set the S3 buckets as origins for the distributions. Store the order data in Amazon S3.
- Migrate the full application to run in containers. Host the containers on Amazon Elastic Kubernetes Service (Amazon EKS). Use the Kubernetes Cluster Autoscaler to increase and decrease the number of pods to process bursts in traffic. Store the data in Amazon RDS for MySQL.
- Deploy the full website on Amazon EC2 instances that run in Auto Scaling groups across multiple Availability Zones. Add an Application Load Balancer (ALB) to distribute the website traffic. Add another ALB for the backend APIs. Store the data in Amazon RDS for MySQL.

### Correct Answer

Use an Amazon S3 bucket to host the website's static content. Deploy an Amazon CloudFront distribution. Set the S3 bucket as the origin. Use Amazon API Gateway and AWS Lambda functions for the backend APIs. Store the data in Amazon DynamoDB.

### Explanation

DynamoDB, S3, CloudFront, API Gateway are managed servers and they are highly scalable. CloudFront can cache static and dynamic data.

## Question 48

How can an instance be copied to another region. Which of the following options is correct?

### Options

- There is no way to copy an instance to another region
- By stopping instance and using copy option
- First instance's root volume is detached. Then a new instance is created in another region. Finally detached volume can be attached to new instance as root device
- __By creating an AMI and copy it to another region__

### Correct Answer

By creating an AMI and copy it to another region

### Explanation

There is no way to directly copy an existing EC2 instance to another region. However, you can create an AMI of the instance and then copy the AMI to the other region. Once the AMI has been copied to the other region, you can launch a new instance from the AMI.

## Question 49

XYZ company is hosting a web application on AWS using a single Amazon EC2 instance that stores user-uploaded documents in an Amazon EBS volume. For better scalability and availability, the company duplicated the architecture and created a second EC2 instance and EBS volume in another Availability Zone, placing both behind an Application Load Balancer. After completing this change, users reported that, each time they refreshed the website, they could see one subset of their documents or the other, but never all of the documents at the same time. What should a solutions architect propose to ensure users see all of their documents at once?

### Options

- Configure the Application Load Balancer to send the request to both servers. Return each document from the correct server
- Copy the data so both EBS volumes contain all the documents
- __Copy the data from both EBS volumes to Amazon EFS. Modify the application to save new documents to Amazon EFS__
- configure the Application Load Balancer to direct a user to the server with the documents

### Correct Answer

Copy the data from both EBS volumes to Amazon EFS. Modify the application to save new documents to Amazon EFS

### Explanation

Amazon Elastic File System (EFS) is a fully managed file storage service that enables users to store and access data in the Amazon cloud. EFS is accessible over the network and can be mounted on multiple Amazon EC2 instances. By copying the data from both EBS volumes to EFS and modifying the application to save new documents to EFS, users will be able to access all of their documents at the same time.

## Question 50

Which of the following is a component of IAM? (Select two)

### Options

- Organizational Units
- __Users__
- EC2
- __Groups__
- SNS

### Correct Answer

Users

Groups

### Explanation

Groups- Groups are used to organize IAM users and manage their permissions. User- Users are the individual entities that authenticate with AWS and have permissions to access resources.

## Question 51

A gaming company that hosts its web application on AWS wants to ensure all Amazon EC2 instances. Amazon RDS DB instances. and Amazon Redshift clusters are configured with tags. The company wants to minimize the effort of configuring and operating this check. What should a solutions architect do this?

### Options

- Write API calls to check all resources for proper tag allocation. Schedule an AWS Lambda function through Amazon CloudWatch to periodically run the code.
- Use Cost Explorer to display resources that are not properly tagged. Tag those resources manually.
- __Use AWS Config rules to define and detect resources that are not properly tagged__
- Write API calls to check all resources for proper tag allocation. Periodically run the code on an EC2 instance.

### Correct Answer

Use AWS Config rules to define and detect resources that are not properly tagged

### Explanation

AWS Config is a service that allows you to track the configuration of your AWS resources. You can use AWS Config to create rules that check for specific configurations. For example, you could create a rule that checks to see if all of your EC2 instances are tagged. Once you have created a rule, AWS Config will track the configuration of your resources and notify you if any of the resources do not meet the rule. This will allow you to quickly identify any resources that are not configured correctly and take corrective action. AWS Config rules templates are pre-defined rules that you can use to quickly and easily create rules. There are a number of rules templates available for EC2 instances, RDS DB instances, and Redshift clusters.

## Question 52

An eCommerce company's dynamic website is hosted using on-premises servers in the United States. The eCommerce company is launching its product in Europe, and it wants to optimize site loading times for new European users. The site's backend must remain in the United States. The product is being launched in a few days, and an immediate solution is needed. Which of the following options is correct?

### Options

- Move the website to Amazon S3. Use Cross-Region Replication between Regions.
- Launch an Amazon EC2 instance in us-east-1 and migrate the site to it.
- Use an Amazon Route 53 geoproximity routing policy pointing to on-premises servers.
- __Use Amazon CloudFront with a custom origin pointing to the on-premises servers.__

### Correct Answer

Use Amazon CloudFront with a custom origin pointing to the on-premises servers.

### Explanation

Amazon CloudFront is a content delivery network (CDN) that can be used to deliver static and dynamic content to users with low latency and high availability. It has edge locations around the world, so it can serve content to users from the closest location, which will improve loading times. In this case, the company's backend servers will remain in the United States, but CloudFront can be used to cache the website's static content in edge locations in Europe. This will allow European users to access the website's static content from a closer location, which will improve loading times.

## Question 53

An IT company is designing an application. The application uses an AWS Lambda function to receive information through Amazon API Gateway and to store the information in an Amazon Aurora PostgreSQL database.During the proof-of-concept stage, the company has to increase the Lambda quotas significantly to handle the high volumes of data that the company needs to load into the database. A solutions architect must recommend a new design to improve scalability and minimize the configuration effort. Which of the following options is correct?

### Options

- Refactor the Lambda function code to Apache Tomcat code that runs on Amazon EC2 instances. Connect the database by using native Java Database Connectivity (JDBC) drivers.
- Set up two Lambda functions. Configure one function to receive the information. Configure the other function to load the information into the database. Integrate the Lambda functions by using Amazon Simple Notification Service (Amazon SNS).
- __Set up two Lambda functions. Configure one function to receive the information. Configure the other function to load the information into the database. Integrate the Lambda functions by using an Amazon Simple Queue Service (Amazon SQS) queue.__
- Change the platform from Aurora to Amazon DynamoDProvision a DynamoDB Accelerator (DAX) cluster. Use the DAX client SDK to point the existing DynamoDB API calls at the DAX cluster.

### Correct Answer

Set up two Lambda functions. Configure one function to receive the information. Configure the other function to load the information into the database. Integrate the Lambda functions by using an Amazon Simple Queue Service (Amazon SQS) queue.

### Explanation

Set up two Lambda functions: One Lambda function will be responsible for receiving the information from API Gateway. The other Lambda function will be responsible for storing the information in the database. Integrate the Lambda functions using an SQS queue: The two Lambda functions will be integrated using an SQS queue. This will allow the two functions to scale independently. When the first Lambda function receives information from API Gateway, it will put the information in the SQS queue. The second Lambda function will then poll the SQS queue for information and store it in the database. Minimize configuration effort: By using a single SQS queue, the solutions architect can minimize the configuration effort. The two Lambda functions will not need to be configured to communicate with each other directly. They will only need to be configured to access the SQS queue.

## Question 54

A company wants to run its critical applications in containers to meet requirements for scalability and availability. The company prefers to focus on maintenance of the critical applications. The company does not want to be responsible for provisioning and managing the underlying infrastructure that runs the containerized workload. Which of the following options is correct?

### Options

- __Use Amazon Elastic Container Service (Amazon ECS) on AWS Fargate.__
- Use Amazon Elastic Container Service (Amazon ECS) on Amazon EC2 worker nodes.
- Use Amazon EC2 instances from an Amazon Elastic Container Service (Amazon ECS)-optimized Amazon Machine Image (AMI).
- Use Amazon EC2 instances, and install Docker on the instances.

### Correct Answer

Use Amazon Elastic Container Service (Amazon ECS) on AWS Fargate.

### Explanation

AWS Fargate is a serverless compute engine for containers that allows you to run containers without provisioning or managing servers. This is a good fit for the company because it allows them to focus on maintenance of the critical applications and not have to worry about provisioning and managing the underlying infrastructure. Amazon ECS is a container orchestration service that allows you to run and manage containers on Amazon Elastic Compute Cloud (Amazon EC2) instances or AWS Fargate. This means that you can use Amazon ECS to run your critical applications on AWS Fargate without having to worry about provisioning or managing Amazon EC2 instance.

## Question 55

A IT company has a two-tier application architecture that runs in public and private subnets. Amazon EC2 instances running the web application are in the public subnet and an EC2 instance for the database runs on the private subnet. The web application instances and the database are running in a single Availability Zone (AZ). Which combination of steps should a solutions architect take to provide high availability for this architecture? (Select TWO.)

### Options

- Create new public and private subnets in a new AZ. Create a database using an EC2 instance in the public subnet in the new AZ. Migrate the old database contents to the new database.
- __Create new public and private subnets in the same VPC, each in a new AZ. Create an Amazon RDS Multi-AZ DB instance in the private subnets. Migrate the old database contents to the new DB instance__
- Add the existing web application instances to an Auto Scaling group behind an Application Load Balancer
- Create new public and private subnets in the same AZ.
- __Create an Amazon EC2 Auto Scaling group and Application Load Balancer spanning multiple AZs for the web application instances.__

### Correct Answer

Create new public and private subnets in the same VPC, each in a new AZ. Create an Amazon RDS Multi-AZ DB instance in the private subnets. Migrate the old database contents to the new DB instance

Create an Amazon EC2 Auto Scaling group and Application Load Balancer spanning multiple AZs for the web application instances.

### Explanation

Create new subnets in a new Availability Zone (AZ) to provide a redundant network. Create an Auto Scaling group with instances in two AZs behind the load balancer to ensure high availability of the web application and redistribution of web traffic between the two public AZs. Create an RDS DB instance in the two private subnets to make the database tier highly available too.

## Question 56

A solutions architect is designing a new hybrid architecture to extend a company's on-premises infrastructure to AWS. The company requires a highly available connection with consistent low latency to an AWS Region. The company needs to minimize costs and is willing to accept slower traffic if the primary connection fails. Which of the following options is correct?

### Options

- Provision an AWS Direct Connect connection to a Region. Use the Direct Connect failover attribute from the AWS CLI to automatically create a backup connection if the primary Direct Connect connection fails.
- __Provision an AWS Direct Connect connection to a Region. Provision a VPN connection as a backup if the primary Direct Connect connection fails.__
- Provision a VPN tunnel connection to a Region for private connectivity. Provision a second VPN tunnel for private connectivity and as a backup if the primary VPN connection fails.
- Provision an AWS Direct Connect connection to a Region. Provision a second Direct Connect connection to the same Region as a backup if the primary Direct Connect connection fails.

### Correct Answer

Provision an AWS Direct Connect connection to a Region. Provision a VPN connection as a backup if the primary Direct Connect connection fails.

### Explanation

AWS Direct Connect is a dedicated private connection between an on-premises network and an AWS Region. It provides a reliable and secure connection with consistent low latency. Direct Connect can be used to connect to multiple Regions, which can provide high availability and redundancy. VPN is a secure tunnel that can be used to connect an on-premises network to an AWS Region. VPN is not as reliable as Direct Connect, and it can have higher latency. However, VPN is a good option for organizations that need to connect to multiple Regions or that have a limited budget. In this case, the solutions architect should provision an AWS Direct Connect connection to a Region. They should then provision a VPN connection as a backup if the primary Direct Connect connection fails. This will provide the company with a highly available connection with consistent low latency, while also minimizing costs.

## Question 57

A persistent database must be migrated from an on-premises server to an Amazon EC2 instances. The database requires 64,000 IOPS and, if possible, should be stored on a single Amazon EBS volume. Which of the following options is correct?

### Options

- Use an instance from the I3 I/O optimized family and leverage instance store storage to achieve the IOPS requirement.
- Create an Amazon EC2 instance with two Amazon EBS Provisioned IOPS SSD (i01) volumes attached. Provision 32,000 IOPS per volume and create a logical volume using the OS that aggregates the capacity.
- __Create a Nitro-based Amazon EC2 instance with an Amazon EBS Provisioned IOPS SSD (i01) volume__
- Create an Amazon EC2 instance with four Amazon EBS General Purpose SSD (gp2) volumes attached. Max out the IOPS on each volume and use a RAID 0 stripe set.

### Correct Answer

Create a Nitro-based Amazon EC2 instance with an Amazon EBS Provisioned IOPS SSD (i01) volume

### Explanation

In this case, the database requires 64,000 IOPS and should be stored on a single Amazon EBS volume. Amazon EBS Provisioned IOPS SSD (i01) volumes are the best option for meeting these requirements. Nitro-based Amazon EC2 instances are also a good choice for this workload because they provide high performance and low latency.

## Question 58

A company runs a photo processing application that needs to frequently upload and download pictures from Amazon S3 buckets that are located in the same AWS Region. A solutions architect has noticed an increased cost in data transfer fees and needs to implement a solution to reduce these costs. Which of the following options is correct?

### Options

- Deploy the application into a public subnet and allow it to route through an internet gateway to access the S3 buckets.
- __Deploy an S3 VPC gateway endpoint into the VPC and attach an endpoint policy that allows access to the S3 buckets.__
- Deploy Amazon API Gateway into a public subnet and adjust the route table to route S3 calls through it.
- Deploy a NAT gateway into a public subnet and attach an endpoint policy that allows access to the S3 buckets.

### Correct Answer

Deploy an S3 VPC gateway endpoint into the VPC and attach an endpoint policy that allows access to the S3 buckets.

### Explanation

this case, the photo processing application needs to frequently upload and download pictures from Amazon S3 buckets that are located in the same AWS Region. Deploying an S3 VPC gateway endpoint into the VPC and attaching an endpoint policy that allows access to the S3 buckets will allow the application to access the S3 buckets without going over the public internet. This will help to reduce data transfer costs.

## Question 59

In Amazon EC2 Container Service components, what is the name of a logical grouping of container instances on which you can place tasks?

### Options

- A container
- __A cluster__
- A container instance
- A task definition

### Correct Answer

A cluster

### Explanation

A cluster is a logical grouping of container instances on which you can place tasks. A cluster can be made up of Amazon EC2 instances or AWS Fargate. When you create a cluster, you specify the number of container instances that you want in the cluster and the type of instances that you want to use.

## Question 60

Which of the following should be referred to if you want to map Amazon Elastic Block Store to an Amazon EC2 instance for AWS CloudFormation resources?

### Options

- Reference the physical IDs of the instance
- The logical IDs of the instance
- __Reference the logical IDs of both the block stores and the instance__
- Reference the physical IDs of the both the block stores and the instance

### Correct Answer

Reference the logical IDs of both the block stores and the instance

## Question 61

XYZ company runs a public-facing three-tier web application in a VPC across multiple Availability Zones. Amazon EC2 instances for the application tier running in private subnets need to download software patches from the internet. However, the EC2 instances cannot be directly accessible from the internet. Which actions should be taken to allow the EC2 instances to download the needed patches? (Select TWO.)

### Options

- __Define a custom route table with a route to the NAT gateway for internet traffic and associate it with the private subnets for the application tier.__
- Configure a NAT instance in a private subnet.
- Define a custom route table with a route to the internet gateway for internet traffic and associate it with the private subnets for the application tier.
- Assign Elastic IP addresses to the EC2 instances.
- __Configure a NAT gateway in a public subnet.__

### Correct Answer

Define a custom route table with a route to the NAT gateway for internet traffic and associate it with the private subnets for the application tier.

Configure a NAT gateway in a public subnet.

### Explanation

A NAT gateway forwards traffic from the EC2 instances in the private subnet to the internet or other AWS services, and then sends the response back to the instances. After a NAT gateway is created, the route tables for private subnets must be updated to point internet traffic to the NAT gateway. Reference: https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html

## Question 62

If you want to use an SSL protocol but do not want to terminate the connection on your load balancer, you can use a __________ protocol for connection from the client to your load balancer?

### Options

- DNS
- HTTPS
- __TCP__
- DHCP

### Correct Answer

TCP

### Explanation

If you want to use an SSL protocol but do not want to terminate the connection on your load balancer, you can use a TCP protocol for connection from the client to your load balancer. SSL termination is the process of decrypting and verifying HTTPS traffic at the load balancer. This can improve performance and security, but it also means that the load balancer needs to be configured to handle SSL traffic. If you do not want to terminate SSL traffic on your load balancer, you can use a TCP protocol for connection from the client to your load balancer. This will mean that the SSL traffic is encrypted all the way to your backend servers.

## Question 63

ABC company is running an SMB file server in its data center. The file server stores large files that are accessed frequently for the first few days after the files are created. After 7 days the files are rarely accessed.The total data size is increasing and is close to the company's total storage capacity. A solutions architect must increase the company's available storage space without losing low-latency access to the most recently accessed files. The solutions architect must also provide file lifecycle management to avoid future storage issues. Which of the following options is correct?

### Options

- Use AWS DataSync to copy data that is older than 7 days from the SMB file server to AWS.
- Install a utility on each user's computer to access Amazon S3. Create an S3 Lifecycle policy to transition the data to S3 Glacier Flexible Retrieval after 7 days.
- __Create an Amazon S3 File Gateway to extend the company's storage space. Create an S3 Lifecycle policy to transition the data to S3 Glacier Deep Archive after 7 days__
- Create an Amazon FSx for Windows File Server file system to extend the company's storage space.

### Correct Answer

Create an Amazon S3 File Gateway to extend the company's storage space. Create an S3 Lifecycle policy to transition the data to S3 Glacier Deep Archive after 7 days

### Explanation

File gateway provides caching and low latency access to the S3 bucket. S3 lifecycle policy can transfer file to Glacier after 7 days.

## Question 64

A data processing company has a production web application in which users upload documents through a web interface or a mobile app. According to a new regulatory requirement. new documents cannot be modified or deleted after they are stored. Which of the following options is correct?

### Options

- Store the uploaded documents on an Amazon Elastic File System (Amazon EFS) volume. Access the data by mounting the volume in read-only mode.
- Store the uploaded documents in an Amazon S3 bucket with S3 Versioning enabled. Configure an ACL to restrict all access to read-only.
- Store the uploaded documents in an Amazon S3 bucket. Configure an S3 Lifecycle policy to archive the documents periodically.
- __Store the uploaded documents in an Amazon S3 bucket with S3 Versioning and S3 Object Lock enabled.__

### Correct Answer

Store the uploaded documents in an Amazon S3 bucket with S3 Versioning and S3 Object Lock enabled.

### Explanation

S3 Versioning allows you to keep multiple versions of an object, so that you can restore a previous version if an object is accidentally deleted or modified. S3 Object Lock allows you to prevent objects from being deleted or overwritten for a fixed amount of time or indefinitely. This meets the regulatory requirement that new documents cannot be modified or deleted after they are stored.

## Question 65

A news company runs a web-based portal that provides users with global breaking news, local alerts, and weather updates. The portal delivers each user a personalized view by using mixture of static and dynamic content. Content is served over HTTPS through an API server running on an Amazon EC2 instance behind an Application Load Balancer (ALB). The company wants the portal to provide this content to its users across the world as quickly as possible. How should a solutions architect design the application to ensure the LEAST amount of latency for all users?

### Options

- Deploy the application stack in two AWS Regions. Use an Amazon Route 53 geolocation routing policy to serve all content from the ALB in the closest Region.
- __Deploy the application stack in two AWS Regions. Use an Amazon Route 53 latency routing policy to serve all content from the ALB in the closest Region.__
- Deploy the application stack in a single AWS Region. Use Amazon CloudFront to serve all static and dynamic content by specifying the ALB as an origin.
- Deploy the application stack in a single AWS Region. Use Amazon CloudFront to serve the static content. Serve the dynamic content directly from the ALB.

### Correct Answer

Deploy the application stack in two AWS Regions. Use an Amazon Route 53 latency routing policy to serve all content from the ALB in the closest Region.

### Explanation

To ensure the least amount of latency for all users, the company should deploy the application stack in two AWS Regions and use an Amazon Route 53 latency routing policy to serve all content from the ALB in the closest Region. This will ensure that users are always routed to the ALB in the Region that is closest to them, which will minimize latency.

