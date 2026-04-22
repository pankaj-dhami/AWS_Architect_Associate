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

Hibernating EC2 instances save the contents of instance memory to an Amazon Elastic Block Store (Amazon EBS) root volume. When the instances restart, the instance memory contents are reloaded. Reference: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Hibernate.html#enabling-hibernation.

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

The best solution to increase the application's performance is to import the SSL certificate into AWS Certificate Manager (ACM) and create an Application Load Balancer with an HTTPS listener that uses the SSL certificate from ACM. This solution will offload the SSL encryption and decryption from the EC2 instances to the Application Load Balancer. This will free up the EC2 instances to focus on serving the web application, which will improve the performance of the application.

## Question 4

A gaming company hosts its multi-tier applications on AWS. For compliance, governance, auditing, and security, the company must track configuration changes on its AWS resources and record a history of API calls made to these resources. Which of the following options is correct?

### Options

- __Use AWS Config to track configuration changes and AWS CloudTrail to record API calls.__
-  Use AWS CloudTrail to track configuration changes and Amazon CloudWatch to record API calls.
- Use AWS Config to track configuration changes and Amazon CloudWatch to record API calls.
- Use AWS CloudTrail to track configuration changes and AWS Config to record API calls.

### Correct Answer

Use AWS Config to track configuration changes and AWS CloudTrail to record API calls.

### Explanation

AWS Config tracks configuration changes on your AWS resources, and AWS CloudTrail records a history of API calls made to these resources. By using both services, you can track configuration changes and API calls in one place, which can help you to meet your compliance, governance, auditing, and security requirements.

## Question 5

A financial company needs to store its accounting records in Amazon S3. The records must be immediately accessible for 1 year and then must be archived for an additional 9 years. No one at the company, including administrative users and root users, can be able to delete the records during the entire 10-year period. The records must be stored with maximum resiliency. Which of the following options is correct?

### Options

- __ Use an S3 Lifecycle policy to transition the records from S3 Standard to S3 Glacier Deep Archive after 1 year. Use S3 Object Lock in compliance mode for a period of 10 years.__
-  Store the records by using S3 Intelligent-Tiering. Use an IAM policy to deny deletion of the records. After 10 years, change the IAM policy to allow deletion.
- Store the records in S3 Glacier for the entire 10-year period. Use an access control policy to deny deletion of the records for a period of 11 years.
- Use an S3 Lifecycle policy to transition the records from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 1 year. Use S3 Object Lock in governance mode for a period of 10 years.

### Correct Answer

 Use an S3 Lifecycle policy to transition the records from S3 Standard to S3 Glacier Deep Archive after 1 year. Use S3 Object Lock in compliance mode for a period of 10 years.

### Explanation

S3 Lifecycle policy will automatically transition the records from S3 Standard to S3 Glacier Deep Archive after 1 year. This will ensure that the records are archived and stored with maximum resiliency. S3 Object Lock in compliance mode will prevent anyone from deleting the records for a period of 10 years. This will ensure that the records are not deleted, even by administrative users or root users.

## Question 6

A food company needs guaranteed Amazon EC2 capacity in three specific Availability Zones in a specific AWS Region for an upcoming event that will last 1 week. What should the company do to guarantee the EC2 capacity?

### Options

- Create an On-Demand Capacity Reservation that specifies the Region needed.
-  Purchase Reserved Instances that specify the Region and three Availability Zones needed.
- Purchase Reserved Instances that specify the Region needed.
- __Create an On-Demand Capacity Reservation that specifies the Region and three Availability Zones needed.__

### Correct Answer

Create an On-Demand Capacity Reservation that specifies the Region and three Availability Zones needed.

### Explanation

The food company to create an On-Demand Capacity Reservation, which is a feature that provides capacity reservation for Amazon EC2 instances in specific Availability Zones within a given region. By specifying the Region and the three specific Availability Zones required for the event, the company ensures guaranteed capacity in those zones for the duration of the event.

## Question 7

You have just discovered that you can upload your objects to Amazon S3 using Multipart Upload API. You start to test it out and but are unsure of the benefits that it would provide. Which of the following is not a benefit of using multipart uploads?

### Options

- Begin an upload before you know the final object size
- Pause and resume object uploads
- __More secure than normal upload__
- Improved throughput

### Correct Answer

More secure than normal upload

### Explanation

Multipart uploads are a way to upload large objects to Amazon S3 in parts. This can be useful for improving throughput, pausing and resuming uploads, and uploading objects whose size is not known in advance. However, multipart uploads are not more secure than normal uploads. In fact, they can be more vulnerable to certain attacks, such as man-in-the-middle attacks.

## Question 8

A company uses Amazon S3 to store its confidential audit documents. The S3 bucket uses bucket policies to restrict access to audit team IAM user credentials according to the principle of least privilege. Company managers are worried about accidental deletion of documents in the S3 bucket and want a more secure solution. What should a solutions architect do to secure the audit documents?

### Options

- __Enable the versioning and MFA Delete features on the S3 bucket.__
- Add an S3 Lifecycle policy to the audit team's IAM user accounts to deny the s3:DeleteObject action during audit dates.
- Use AWS Key Management Service (AWS KMS) to encrypt the S3 bucket and restrict audit team IAM user accounts from accessing the KMS key.
- Enable multi-factor authentication (MFA) on the IAM user credentials for each audit team IAM user account.

### Correct Answer

Enable the versioning and MFA Delete features on the S3 bucket.

### Explanation

Versioning allows you to recover audit documents that are accidentally deleted or overwritten. MFA Delete requires users to enter an MFA code before they can delete objects in the bucket. This helps to prevent accidental deletions.

## Question 9

A company is building a web-based application running on Amazon EC2 instances in multiple Availability Zones. The web application will provide access to a repository of text documents totaling about 900 TB in size. The company anticipates that the web application will experience periods of high demand. A solutions architect must ensure that the storage component for the text documents can scale to meet the demand of the application at all times. The company is concerned about the overall cost of the solution. Which of the following options is most cost-effective?

### Options

- Amazon Elastic Block Store (Amazon EBS)
- __Amazon S3__
- Amazon OpenSearch Service (Amazon Elasticsearch Service)
- Amazon Elastic File System (Amazon EFS)

### Correct Answer

Amazon S3

### Explanation

Amazon S3 is an object storage service that is designed to store and retrieve any amount of data, from anywhere on the web. It is highly scalable, secure, and durable, and it offers very low pricing. Amazon S3 is also very easy to use. To store your text documents in Amazon S3, you simply upload them to an S3 bucket. Once your documents are uploaded, you can access them from anywhere in the world using the internet.

## Question 10

A company is migrating an application from on-premises servers to Amazon EC2 instances. As part of the migration design requirements, a solutions architect must implement infrastructure metric alarms. The company does not need to take action if CPU utilization increases to more than 50% for a short burst of time. However, if the CPU utilization increases to more than 50% and read IOPS on the disk are high at the same time, the company needs to act as soon as possible. The solutions architect also must reduce false alarms. Which of the following options is correct?

### Options

- Create Amazon CloudWatch dashboards to visualize the metrics and react to issues quickly.
- Create single Amazon CloudWatch metric alarms with multiple metric thresholds where possible.
- Create Amazon CloudWatch Synthetics canaries to monitor the application and raise an alarm.
- __Create Amazon CloudWatch composite alarms where possible.__

### Correct Answer

Create Amazon CloudWatch composite alarms where possible.

### Explanation

Composite alarms allow you to combine multiple alarms into a single alarm. You can use composite alarms to create complex alarm conditions that take into account multiple factors. In this case, the solutions architect can create a composite alarm that monitors both CPU utilization and read IOPS on the disk. The alarm will only go into alarm state if both metrics are above their thresholds. This will help to reduce false alarms.

## Question 11

An application allows users at a company's headquarters to access product data. The product data is stored in an Amazon RDS MySQL DB instance. The operations team has isolated an application performance slowdown and wants to separate read traffic from write traffic. A solutions architect needs to optimize the application's performance quickly. Which of the following options is correct?

### Options

- __Create read replicas for the database. Configure the read replicas with the same compute and storage resources as the source database.__
- Change the existing database to a Multi-AZ deployment. Serve the read requests from the secondary Availability Zone.
- Create read replicas for the database. Configure the read replicas with half of the compute and storage resources as the source database.
- Change the existing database to a Multi-AZ deployment. Serve the read requests from the primary Availability Zone.

### Correct Answer

Create read replicas for the database. Configure the read replicas with the same compute and storage resources as the source database.

### Explanation

Creating read replicas is the most effective way to separate read traffic from write traffic in an Amazon RDS MySQL DB instance. Read replicas are synchronized with the source database in real time, so they always have access to the most up-to-date data.

## Question 12

An IT company wants to build a scalable key management infrastructure to support developers who need to encrypt data in their applications. What should a solutions architect do to reduce the operational burden?

### Options

- Use AWS Certificate Manager (ACM) to create, store, and assign the encryption keys.
- __Use AWS Key Management Service (AWS KMS) to protect the encryption keys.__
- Use multi-factor authentication (MFA) to protect the encryption keys.
- Use an IAM policy to limit the scope of users who have access permissions to protect the encryption keys.

### Correct Answer

Use AWS Key Management Service (AWS KMS) to protect the encryption keys.

### Explanation

AWS KMS is a managed service that makes it easy for you to create and manage customer master keys (CMKs). CMKs are encryption keys that you can use to encrypt your data. AWS KMS also provides features to help you protect your CMKs, such as key rotation, auditing, and logging.

## Question 13

In Amazon EC2 Container Service components, what is the name of a logical grouping of container instances on which you can place tasks?

### Options

- A EC2 instance
- A task definition
- __A cluster__
- A container

### Correct Answer

A cluster

### Explanation

A cluster is a collection of container instances that you can use to run and manage your containerized applications. You can create multiple clusters, each with its own set of container instances and tasks. This allows you to isolate your applications and manage them more effectively.

## Question 14

A financial services company needs to store data in Amazon S3 and must prevent the data from being changed. The company wants new objects that are uploaded to Amazon S3 to remain unchangeable for a nonspecific amount of time until the company decides to modify the objects. Only specific users in the company's AWS account can have the ability 10 delete the objects. Which of the following options is correct?

### Options

- __Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Add a legal hold to the objects. Add the s3:PutObjectLegalHold permission to the IAM policies of users who need to delete the objects.__
- Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Set a retention period of 100 years. Use governance mode as the S3 bucket’s default retention mode for new objects.
- Create an S3 bucket. Use AWS CloudTrail to track any S3 API events that modify the objects. Upon notification, restore the modified objects from any backup versions that the company has.
- Create an S3 Glacier vault. Apply a write-once, read-many (WORM) vault lock policy to the objects.

### Correct Answer

Create an S3 bucket with S3 Object Lock enabled. Enable versioning. Add a legal hold to the objects. Add the s3:PutObjectLegalHold permission to the IAM policies of users who need to delete the objects.

### Explanation

S3 Object Lock is a feature that allows you to specify retention periods and legal holds for objects in your S3 buckets. When you enable S3 Object Lock, you can specify a retention period for new objects that are uploaded to the bucket. This will prevent the objects from being deleted or overwritten for the specified period of time. You can also add a legal hold to objects, which will prevent them from being deleted or overwritten indefinitely. Versioning is a feature that creates a copy of each object that is uploaded to the bucket. This can be useful if you need to recover an object that was accidentally modified or deleted.

## Question 15

A large media company hosts a web application on AWS. The company wants to start caching confidential media files so that users around the world will have reliable access to the files. The content is stored in Amazon S3 buckets. The company must deliver the content quickly, regardless of where the requests originate geographically. Which of the following options is correct?

### Options

- Deploy AWS Global Accelerator to connect the S3 buckets to the web application.
- __Deploy Amazon CloudFront to connect the S3 buckets to CloudFront edge servers.__
- Use AWS DataSync to connect the S3 buckets to the web application.
- Use Amazon Simple Queue Service (Amazon SQS) to connect the S3 buckets to the web application.

### Correct Answer

Deploy Amazon CloudFront to connect the S3 buckets to CloudFront edge servers.

### Explanation

CloudFront is a content delivery network (CDN) that can be used to deliver content to users around the world with low latency and high availability. CloudFront works by caching content on edge servers that are located close to the users who request the content. This can reduce latency and improve performance for users who are located far away from the origin of the content.

## Question 16

A company is running an online transaction processing (OLTP) workload on AWS. This workload uses an unencrypted Amazon RDS DB instance in a Multi-AZ deployment. Daily database snapshots are taken from this instance. What should a solutions architect do to ensure the database and snapshots are always encrypted moving forward?

### Options

- __Encrypt a copy of the latest DB snapshot. Replace existing DB instance by restoring the encrypted snapshot.__
- Create a new encrypted Amazon Elastic Block Store (Amazon EBS) volume and copy the snapshots to it. Enable encryption on the DB instance.
- Copy the snapshots and enable encryption using AWS Key Management Service (AWS KMS) Restore encrypted snapshot to an existing DB instance.
- Copy the snapshots to an Amazon S3 bucket that is encrypted using server-side encryption with AWS Key Management Service (AWS KMS) managed keys (SSE-KMS).

### Correct Answer

Encrypt a copy of the latest DB snapshot. Replace existing DB instance by restoring the encrypted snapshot.

### Explanation

You can only encrypt an Amazon RDS DB instance when you create it, not after the DB instance is created. However, because you can encrypt a copy of an unencrypted snapshot, you can effectively add encryption to an unencrypted DB instance. That is, you can create a snapshot of your DB instance, and then create an encrypted copy of that snapshot. You can then restore a DB instance from the encrypted snapshot, and thus you have an encrypted copy of your original DB instance

## Question 17

A company is using a SQL database to store movie data that is publicly accessible. The database runs on an Amazon RDS Single-AZ DB instance. A script runs queries at random intervals each day to record the number of new movies that have been added to the database. The script must report a final total during business hours. The company's development team notices that the database performance is inadequate for development tasks when the script is running. A solutions architect must recommend a solution to resolve this issue. Which solution will meet this requirement with the LEAST operational overhead?

### Options

- Instruct the development team to manually export the entries in the database at the end of each day.
- Use Amazon ElastiCache to cache the common queries that the script runs against the database.
- Modify the DB instance to be a Multi-AZ deployment.
- __Create a read replica of the database. Configure the script to query only the read replica.__

### Correct Answer

Create a read replica of the database. Configure the script to query only the read replica.

### Explanation

Creating a read replica of the database will provide a separate database instance for the script to query, without impacting the performance of the primary database instance for development tasks. Read replicas are synchronized with the primary database instance in real time, so the script will always have access to the most up-to-date data.

## Question 18

An ecommerce company recently started using Amazon Aurora as the data store for its global ecommerce application. When large reports are run, developers report that the ecommerce application is performing poorly. After reviewing metrics in Amazon CloudWatch, a solutions architect finds that the ReadIOPS and CPU Utilizalion metrics are spiking when monthly reports run. What is the MOST cost-effective solution?

### Options

- __Migrate the monthly reporting to an Aurora Replica.__
- Migrate the Aurora database to a larger instance class.
- Increase the Provisioned IOPS on the Aurora instance.
- Migrate the monthly reporting to Amazon Redshift.

### Correct Answer

Migrate the monthly reporting to an Aurora Replica.

### Explanation

Migrating the monthly reporting to an Aurora Replica may be the most cost-effective solution because it involves creating a read-only copy of the database that can be used specifically for running large reports without impacting the performance of the primary database. This solution allows the company to scale the read capacity of the database without incurring additional hardware or I/O costs

## Question 19

A company is running a multi-tier web application on premises. The web application is containerized and runs on a number of Linux hosts connected to a PostgreSQL database that contains user records. The operational overhead of maintaining the infrastructure and capacity planning is limiting the company's growth. A solutions architect must improve the application's infrastructure. Which combination of actions should the solutions architect take to accomplish this? (Choose two.)

### Options

- Set up an Amazon CloudFront distribution for the web application content.
- __Migrate the web application to be hosted on AWS Fargate with Amazon Elastic Container Service (Amazon ECS).__
- __Migrate the PostgreSQL database to Amazon Aurora.__
- Set up Amazon ElastiCache between the web application and the PostgreSQL database.
- Migrate the web application to be hosted on Amazon EC2 instances.

### Correct Answer

Migrate the web application to be hosted on AWS Fargate with Amazon Elastic Container Service (Amazon ECS).  
Migrate the PostgreSQL database to Amazon Aurora.

### Explanation

Migrate the PostgreSQL database to Amazon Aurora- Amazon Aurora is a fully-managed, MySQL- and PostgreSQL-compatible relational database built for the cloud. It is up to five times faster than standard PostgreSQL databases, and it is much more durable and scalable- Migrate the web application to be hosted on AWS Fargate with Amazon Elastic Container Service (Amazon ECS). AWS Fargate is a serverless compute engine for Docker containers. It makes it easy to run containerized applications without having to manage servers or clusters.

## Question 20

If you launch an instance into a VPC that has an instance tenancy of a ______________, your instance is automatically a Dedicated Instance, regardless of the tenancy of the instance.

### Options

- New instance
- Spot instance
- EC2 Instance
- __Dedicated instance__

### Correct Answer

Dedicated instance

### Explanation

This is because Dedicated Instances are launched on hardware that is dedicated to a single customer. When you launch an instance into a VPC with a dedicated instance tenancy, you are essentially requesting that AWS launch your instance on dedicated hardware. Therefore, your instance will automatically be a Dedicated Instance.

## Question 21

A Solution architect has been tasked with identifying an appropriate storage solution for a NoSQL database that requires random I/O reads of greater than 100,000 4kB IOPS Which EC2 option will meet this requirement?

### Options

- __EBS provisioned IOPS__
- SSD instance store
- High Storage instance configured in RAID 10
- EBS optimized instances

### Correct Answer

EBS provisioned IOPS

### Explanation

EBS provisioned IOPS allows you to allocate a specific number of IOPS to an EBS volume. This is important for applications that require high IOPS performance, such as NoSQL databases.

## Question 22

An analytics company is planning to offer a web analytics service to its users. The service will require that the users’ webpages include a JavaScript script that makes authenticated GET requests to the company’s Amazon S3 bucket. What must a solutions architect do to ensure that the script will successfully execute?

### Options

- Enable S3 Versioning on the S3 bucket
- Provide the users with a signed URL for the script.
- Configure an S3 bucket policy to allow public execute privileges.
- __Enable cross-origin resource sharing (CORS) on the S3 bucket.__

### Correct Answer

Enable cross-origin resource sharing (CORS) on the S3 bucket.

### Explanation

Web browsers will block running a script that originates from a server with a domain name that is different from the webpage. Amazon S3 can be configured with CORS to send HTTP headers that allow the script to run. Reference: https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html

## Question 23

A solutions architect is developing a VPC architecture that includes multiple subnets. The architecture will host applications that use Amazon EC2 instances and Amazon RDS DB instances. The architecture consists of six subnets in two Availability Zones. Each Availability Zone includes a public subnet, a private subnet, and a dedicated subnet for databases. Only EC2 instances that run in the private subnets can have access to the RDS databases. Which of the following options is correct?

### Options

- Create a new route table that excludes the route to the public subnets' CIDR blocks. Associate the route table with the database subnets.
- Create a new peering connection between the public subnets and the private subnets. Create a different peering connection between the private subnets and the database subnets.
- Create a security group that denies inbound traffic from the security group that is assigned to instances in the public subnets. Attach the security group to the DB instances.
- __ Create a security group that allows inbound traffic from the security group that is assigned to instances in the private subnets. Attach the security group to the DB instances.__

### Correct Answer

Create a security group that allows inbound traffic from the security group that is assigned to instances in the private subnets. Attach the security group to the DB instances.

### Explanation

This solution will allow only EC2 instances that run in the private subnets to have access to the RDS databases. The security group will deny inbound traffic from any other source, including the public subnets.

## Question 24

A solution architect has started to use AWS Elastic Beanstalk to quickly deploy and manage applications in the AWS cloud. Again solution architect start to wonder if solution architect is being charged for this service? What is AWS’s billing policy for AWS Elastic Beanstalk?

### Options

- You pay only for the underlying AWS resources that your application consumes as long as they are all in the same availabilty zone.
- __You pay only for the underlying AWS resources that your application consumes.__
- NA
- You pay a one time yearly fee to use it.

### Correct Answer

You pay only for the underlying AWS resources that your application consumes.

### Explanation

AWS Elastic Beanstalk is a service that makes it easy to deploy and manage applications in the AWS cloud. It is billed based on the underlying AWS resources that your application consumes, such as EC2 instances, EBS volumes, and RDS instances. You are not charged for the Elastic Beanstalk service itself. If your application is deployed in multiple availability zones, you will be charged for the underlying resources in each availability zone.

## Question 25

An eBook company is hosting a static website on Amazon S3 and is using Amazon Route 53 for DNS. The website is experiencing increased demand from around the world. The company must decrease latency for users who access the website. Which solution meets these requirements MOST cost-effectively?

### Options

- Replicate the S3 bucket that contains the website to all AWS Regions. Add Route 53 geolocation routing entries.
- Enable S3 Transfer Acceleration on the bucket. Edit the Route 53 entries to point to the new endpoint.
- Provision accelerators in AWS Global Accelerator. Associate the supplied IP addresses with the S3 bucket. Edit the Route 53 entries to point to the IP addresses of the accelerators.
- __Add an Amazon CloudFront distribution in front of the S3 bucket. Edit the Route 53 entries to point to the CloudFront distribution.__

### Correct Answer

Add an Amazon CloudFront distribution in front of the S3 bucket. Edit the Route 53 entries to point to the CloudFront distribution.

### Explanation

Amazon CloudFront is a content delivery network (CDN) that can be used to deliver static and dynamic content to users all over the world. CloudFront caches content in edge locations around the world, which can significantly reduce latency for users who access the content from far away. In this case, the company is hosting a static website on Amazon S3. To decrease latency for users who access the website, the best solution is to add an Amazon CloudFront distribution in front of the S3 bucket. This will cache the website's content in edge locations around the world, which will reduce latency for users who access the website from far away. The other solutions are not as cost-effective as CloudFront. For example, replicating the S3 bucket to all AWS Regions would be very expensive, and enabling S3 Transfer Acceleration would only improve the performance of uploads and downloads, not the performance of website requests.

## Question 26

A solution architect tries to enable lifecycle policies on one of the S3 buckets created by the solution architect, but the solution architect is not able to do so on that particular bucket. What could be the reason?

### Options

- Bucket is corrupted.
- __Versioning is not enabled on that bucket.__
- Bucket type is not correct.
- Versioning is enabled on the bucket.

### Correct Answer

Versioning is not enabled on that bucket.

### Explanation

S3 lifecycle policies cannot be enabled on buckets with versioning enabled. This is because lifecycle policies can delete objects, and versioning prevents objects from being deleted. If you want to enable lifecycle policies on a bucket, you must first disable versioning. Once you have disabled versioning, you can create and enable lifecycle policies on the bucket.

## Question 27

A company has a highly dynamic batch processing job that uses many Amazon EC2 instances to complete it. The job is stateless in nature, can be started and stopped at any given time with no negative impact, and typically takes upwards of 60 minutes total to complete. The company has asked a solutions architect to design a scalable and cost-effective solution that meets the requirements of the job. Which of the following options is correct?

### Options

- __ Implement EC2 Spot Instances.__
- Implement the processing on AWS Lambda.
- Purchase EC2 Reserved Instances.
-  Implement EC2 On-Demand Instances.

### Correct Answer

Implement EC2 Spot Instances.

### Explanation

EC2 Spot Instances are unused EC2 capacity that AWS makes available at a significant discount compared to On-Demand Instance prices. Spot Instances are a good fit for batch processing jobs because they are typically less time-sensitive than other workloads and can be interrupted without impacting the overall job.

## Question 28

A company recently migrated a message processing system to AWS. The system receives messages into an ActiveMQ queue running on an Amazon EC2 instance. Messages are processed by a consumer application running on Amazon EC2. The consumer application processes the messages and writes results to a MySQL database running on Amazon EC2. The company wants this application to be highly available with low operational complexity. Which of the following options is correct?

### Options

- Add a second ActiveMQ server to another Availability Zone. Add an additional consumer EC2 instance in another Availability Zone. Replicate the MySQL database to another Availability Zone.
- Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an additional consumer EC2 instance in another Availability Zone. Replicate the MySQL database to another Availability Zone.
- Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an additional consumer EC2 instance in another Availability Zone. Use Amazon RDS for MySQL with Multi-AZ enabled.
- __Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an Auto Scaling group for the consumer EC2 instances across two Availability Zones. Use Amazon RDS for MySQL with Multi-AZ enabled.__

### Correct Answer

Use Amazon MQ with active/standby brokers configured across two Availability Zones. Add an Auto Scaling group for the consumer EC2 instances across two Availability Zones. Use Amazon RDS for MySQL with Multi-AZ enabled.

### Explanation

Amazon MQ is a managed message broker service that makes it easy to set up, operate, and manage message brokers in AWS. Amazon MQ supports ActiveMQ and RabbitMQ. Active/standby brokers provide high availability for your message broker by automatically switching over to the standby broker if the primary broker fails. An Auto Scaling group ensures that you always have enough consumer EC2 instances to process your messages. If a consumer EC2 instance fails, Auto Scaling will automatically launch a new instance. Amazon RDS for MySQL with Multi-AZ enabled provides high availability for your MySQL database by replicating your data to multiple Availability Zones.

## Question 29

A company is designing an application where users upload small files into Amazon S3. After a user uploads a file, the file requires one-time simple processing to transform the data and save the data in JSON format for later analysis. Each file must be processed as quickly as possible after it is uploaded. Demand will vary. On some days, users will upload a high number of files. On other days, users will upload a few files or no files. Which of the following options is correct?

### Options

- Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use Amazon EC2 instances to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.
- Configure Amazon EMR to read text files from Amazon S3. Run processing scripts to transform the data. Store the resulting JSON file in an Amazon Aurora DB cluster.
- Configure Amazon EventBridge (Amazon CloudWatch Events) to send an event to Amazon Kinesis Data Streams when a new file is uploaded. Use an AWS Lambda function to consume the event from the stream and process the data. Store the resulting JSON file in an Amazon Aurora DB cluster.
- __Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.__

### Correct Answer

Configure Amazon S3 to send an event notification to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function to read from the queue and process the data. Store the resulting JSON file in Amazon DynamoDB.

### Explanation

This solution is the most cost-effective and scalable solution for processing small files in real time. The Lambda function will be triggered whenever a new file is uploaded to S3. The Lambda function can then process the file and store the resulting JSON file in DynamoDB.

## Question 30

Our company plans to run a monitoring application on an Amazon EC2 instance in a VPC. Connections are made to the EC2 instance using the instance’s private IPv4 address. A solutions architect needs to design a solution that will allow traffic to be quickly directed to a standby EC2 instance if the application fails and becomes unreachable. Which of the following options is correct?

### Options

- Associate an Elastic IP address with the network interface of the primary EC2 instance. Disassociate the Elastic IP from the primary instance upon failure and associate it with a standby EC2 instance.
- __Attach a secondary elastic network interface to the EC2 instance configured with the private IP address. Move the network interface to the standby EC2 instance if the primary EC2 instance becomes unreachable.__
- Configure a custom DHCP option set. Configure DHCP to assign the same private IP address to the standby EC2 instance when the primary EC2 instance fails.
- Deploy an Application Load Balancer configured with a listener for the private IP address and register the primary EC2 instance with the load balancer. Upon failure, de-register the instance and register the standby EC2 instance.

### Correct Answer

Attach a secondary elastic network interface to the EC2 instance configured with the private IP address. Move the network interface to the standby EC2 instance if the primary EC2 instance becomes unreachable.

### Explanation

The better option for this scenario is to leverage an Elastic Load Balancer (ELB) with health check configured to monitor the application running on the EC2 instance. Here's why:

.

Fast Failover: ELB can be configured with health checks that ping the application on the EC2 instance. If the health checks fail, the ELB automatically removes the unhealthy instance from the traffic flow and directs traffic to the remaining healthy instances.

Private IPs: The application uses the EC2 instance's private IP for connections, eliminating the need for an Elastic IP (EIP) in this case.

Standby Instance: You can create a standby EC2 instance with the same application pre-configured. This standby instance can be part of an Auto Scaling group that automatically launches a new instance if the primary instance fails.

Minimal Downtime: With a properly configured ELB and Auto Scaling group, the failover to the standby instance should be quick, minimizing downtime for your monitoring application.

## Question 31

An IT company maintains a searchable repository of items on its website. The data is stored in an Amazon RDS for MySQL database table that contains more than 10 million rows. The database has 2 TB of General Purpose SSD storage. There are millions of updates against this data every day through the company's website. The company has noticed that some insert operations are taking 10 seconds or longer. The company has determined that the database storage performance is the problem. Which of the following options is correct?

### Options

- Enable Multi-AZ RDS read replicas with MySQL native asynchronous replication.
- __Change the storage type to Provisioned IOPS SSD.__
- Change the DB instance to a burstable performance instance class.
- Change the DB instance to a memory optimized instance class.

### Correct Answer

Change the storage type to Provisioned IOPS SSD.

### Explanation

General Purpose SSD storage is a good choice for most workloads, but it does not guarantee a minimum level of performance. Provisioned IOPS SSD storage, on the other hand, guarantees a minimum level of IOPS (input/output operations per second). This means that insert operations will be more consistent and less likely to take 10 seconds or longer. The other solutions are not as likely to address the performance issue. Changing the DB instance to a memory optimized instance class or a burstable performance instance class may improve performance, but it is not guaranteed. Enabling Multi-AZ RDS read replicas with MySQL native asynchronous replication will improve availability, but it will not improve performance

## Question 32

An application company wants to migrate its on-premises application to AWS. The application produces output files that vary in size from tens of gigabytes to hundreds of terabytes. The application data must be stored in a standard file system structure. The company wants a solution that scales automatically. is highly available, and requires minimum operational overhead. Which of the following options is correct?

### Options

- Migrate the application to run as containers on Amazon Elastic Container Service (Amazon ECS). Use Amazon S3 for storage.
- Migrate the application to run as containers on Amazon Elastic Kubernetes Service (Amazon EKS). Use Amazon Elastic Block Store (Amazon EBS) for storage.
- __ Migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. Use Amazon Elastic File System (Amazon EFS) for storage.__
-  Migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. Use Amazon Elastic Block Store (Amazon EBS) for storage.

### Correct Answer

Migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. Use Amazon Elastic File System (Amazon EFS) for storage.

### Explanation

Amazon EFS is a fully managed file system that can be used to store large amounts of data. It is highly scalable and available, and it can be used to store data in a standard file system structure. In this case, the company wants to migrate its on-premises application to AWS, and it wants a solution that scales automatically, is highly available, and requires minimum operational overhead. The best way to meet these requirements is to migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. This will ensure that the application is always available, and it will scale automatically to meet demand. Amazon EBS is a block storage service that can be used to store data on individual EC2 instances. However, EBS is not as scalable or available as EFS. Therefore, it is not the best choice for storing large amounts of data.

## Question 33

Which of the following approaches provides the lowest cost for Amazon elastic block store snapshots while giving you the ability to fully restore data?

### Options

- __Maintain two snapshots: the original snapshot and the latest incremental snapshot.__
- Maintain the most current snapshot; archive the original and increment to Amazon Glacier.
- Maintain a single snapshot; the latest snapshot is both incremental and complete.
- Maintain a volume snapshot; subsequent snapshots will overwrite one another.

### Correct Answer

Maintain two snapshots: the original snapshot and the latest incremental snapshot.

### Explanation

The best approach for providing the lowest cost for Amazon Elastic Block Store (EBS) snapshots while giving you the ability to fully restore data is to maintain two snapshots: the original snapshot and the latest incremental snapshot. EBS snapshots are incremental, meaning that they only contain the data that has changed since the previous snapshot. This can save you a lot of money, especially if your data changes frequently.

## Question 34

An application running on AWS uses an Amazon Aurora Multi-AZ DB cluster deployment for its database. When evaluating performance metrics, a solutions architect discovered that the database reads are causing high I/O and adding latency to the write requests against the database. What should the solutions architect do to separate the read requests from the write requests?

### Options

- Update the application to read from the Multi-AZ standby instance.
- __Create an Aurora replica and modify the application to use the appropriate endpoints__
- Enable read-through caching on the Aurora database.
- Create a second Aurora database and link it to the primary database as a read replica

### Correct Answer

Create an Aurora replica and modify the application to use the appropriate endpoints

### Explanation

Aurora Replicas provide a way to offload read traffic. Aurora Replicas share the same underlying storage as the main database, so lag time is generally very low. Aurora Replicas have their own endpoints, so the application will need to be configured to direct read traffic to the new endpoints.

## Question 35

A company hosts a containerized web application on a fleet of on-premises servers that process incoming requests. The number of requests is growing quickly. The on-premises servers cannot handle the increased number of requests. The company wants to move the application to AWS with minimum code changes and minimum development effort. Which of the following options is correct?

### Options

-  Use two Amazon EC2 instances to host the containerized web application. Use an Application Load Balancer to distribute the incoming requests.
- Use AWS Lambda with a new code that uses one of the supported languages. Create multiple Lambda functions to support the load. Use Amazon API Gateway as an entry point to the Lambda functions.
- Use a high performance computing (HPC) solution such as AWS ParallelCluster to establish an HPC cluster that can process the incoming requests at the appropriate scale.
- __Use AWS Fargate on Amazon Elastic Container Service (Amazon ECS) to run the containerized web application with Service Auto Scaling. Use an Application Load Balancer to distribute the incoming requests.__

### Correct Answer

Use AWS Fargate on Amazon Elastic Container Service (Amazon ECS) to run the containerized web application with Service Auto Scaling. Use an Application Load Balancer to distribute the incoming requests.

### Explanation

AWS Fargate is a serverless compute engine for Amazon ECS that makes it easy to run containerized applications without managing servers or clusters. Fargate scales your applications automatically, so you can focus on building and running your applications. Service Auto Scaling is a feature of Amazon ECS that automatically scales your services based on demand. Service Auto Scaling monitors your service's metrics and automatically scales the service up or down based on those metrics. An Application Load Balancer is a load balancer that distributes incoming traffic across multiple targets, such as EC2 instances or services running on Fargate. Application Load Balancers can scale automatically to handle increases in traffic.

## Question 36

A company runs multiple Windows workloads on AWS. The company's employees use Windows file shares that are hosted on two Amazon EC2 instances. The file shares synchronize data between themselves and maintain duplicate copies. The company wants a highly available and durable storage solution that preserves how users currently access the files. Which of the following options is correct?

### Options

- Extend the file share environment to Amazon Elastic File System (Amazon EFS) with a Multi-AZ configuration. Migrate all the data to Amazon EFS.
- __Extend the file share environment to Amazon FSx for Windows File Server with a Multi-AZ configuration. Migrate all the data to FSx for Windows File Server.__
- Migrate all the data to Amazon S3. Set up IAM authentication for users to access files.
- Set up an Amazon S3 File Gateway. Mount the S3 File Gateway on the existing EC2 instances.

### Correct Answer

Extend the file share environment to Amazon FSx for Windows File Server with a Multi-AZ configuration. Migrate all the data to FSx for Windows File Server.

### Explanation

Amazon FSx for Windows File Server is a fully managed, file-level storage service that makes it easy to deploy and manage Windows file servers on AWS. It provides a high-performance, scalable, and durable file storage solution that can be used to host file shares for Windows applications. In this case, the company wants a highly available and durable storage solution that preserves how users currently access the files. Amazon FSx for Windows File Server with a Multi-AZ configuration can provide this by replicating the file share data across multiple Availability Zones. This ensures that the file share will be available even if one Availability Zone fails.

## Question 37

A Database company has an on-premises application that generates a large amount of time-sensitive data that is backed up to Amazon S3. The application has grown and there are user complaints about internet bandwidth limitations. A solutions architect needs to design a long-term solution that allows for both timely backups to Amazon S3 and with minimal impact on internet connectivity for internal users. Which of the following options is correct?

### Options

- Establish AWS VPN connections and proxy all traffic through a VPC gateway endpoint.
- __ Establish a new AWS Direct Connect connection and direct backup traffic through this new connection.__
- Submit a support ticket through the AWS Management Console. Request the removal of S3 service limits from the account.
- Order daily AWS Snowball devices. Load the data onto the Snowball devices and return the devices to AWS each day.

### Correct Answer

Establish a new AWS Direct Connect connection and direct backup traffic through this new connection.

### Explanation

AWS Direct Connect is a dedicated network connection between your on-premises network and AWS. This connection can provide higher bandwidth and lower latency than internet-based connections. By establishing a new AWS Direct Connect connection, the company can direct backup traffic through this new connection, which will reduce the impact on internet connectivity for internal users.

## Question 38

A company uses a popular content management system (CMS) for its corporate website. However, the required patching and maintenance are burdensome. The company is redesigning its website and wants anew solution. The website will be updated four times a year and does not need to have any dynamic content available. The solution must provide high scalability and enhanced security. Which combination of changes will meet these requirements with the LEAST operational overhead? (Choose two.)

### Options

- Create and deploy an AWS Lambda function to manage and serve the website content.
- __ Create the new website and an Amazon S3 bucket. Deploy the website on the S3 bucket with static website hosting enabled.__
- __Configure Amazon CloudFront in front of the website to use HTTPS functionality.__
- Deploy an AWS WAF web ACL in front of the website to provide HTTPS functionality.
- Create the new website. Deploy the website by using an Auto Scaling group of Amazon EC2 instances behind an Application Load Balancer.

### Correct Answer

Create the new website and an Amazon S3 bucket. Deploy the website on the S3 bucket with static website hosting enabled.  
Configure Amazon CloudFront in front of the website to use HTTPS functionality.

### Explanation

Amazon CloudFront is a content delivery network (CDN) that can be used to deliver static content to users around the world with low latency and high availability. CloudFront can also be used to encrypt traffic using HTTPS, which can help to improve the security of the website. Amazon S3 is an object storage service that can be used to store static website content. S3 is a highly scalable and secure service, and it is very easy to use.

## Question 39

A security company is preparing to launch a public-facing web application in the AWS Cloud. The architecture consists of Amazon EC2 instances within a VPC behind an Elastic Load Balancer (ELB). A third-party service is used for the DNS. The company's solutions architect must recommend a solution to detect and protect against large-scale DDoS attacks. Which of the following options is correct?

### Options

- Enable Amazon GuardDuty on the account.
- Enable Amazon Inspector on the EC2 instances.
- __Enable AWS Shield Advanced and assign the ELB to it.__
- Enable AWS Shield and assign Amazon Route 53 to it.

### Correct Answer

Enable AWS Shield Advanced and assign the ELB to it.

### Explanation

AWS Shield Advanced is a managed DDoS protection service that provides protection against large-scale DDoS attacks. It can protect Amazon EC2 instances, Elastic Load Balancing (ELB) resources, Amazon CloudFront distributions, AWS Global Accelerator, and Amazon Route 53.

## Question 40

A company has a small Python application that processes JSON documents and outputs the results to an on-premises SQL database. The application runs thousands of times each day. The company wants to move the application to the AWS Cloud. The company needs a highly available solution that maximizes scalability and minimizes operational overhead. Which of the following options is correct?

### Options

- Place the JSON documents in an Amazon S3 bucket. Run the Python code on multiple Amazon EC2 instances to process the documents. Store the results in an Amazon Aurora DB cluster.
- Place the JSON documents in an Amazon Simple Queue Service (Amazon SQS) queue as messages. Deploy the Python code as a container on an Amazon Elastic Container Service (Amazon ECS) cluster that is configured with the Amazon EC2 launch type. Use the container to process the SQS messages. Store the results on an Amazon RDS DB instance.
- __Place the JSON documents in an Amazon S3 bucket. Create an AWS Lambda function that runs the Python code to process the documents as they arrive in the S3 bucket. Store the results in an Amazon Aurora DB cluster.__
- Place the JSON documents in an Amazon Elastic Block Store (Amazon EBS) volume. Use the EBS Multi-Attach feature to attach the volume to multiple Amazon EC2 instances. Run the Python code on the EC2 instances to process the documents. Store the results on an Amazon RDS DB instance.

### Correct Answer

Place the JSON documents in an Amazon S3 bucket. Create an AWS Lambda function that runs the Python code to process the documents as they arrive in the S3 bucket. Store the results in an Amazon Aurora DB cluster.

### Explanation

AWS Lambda is a serverless compute service that allows you to run code without provisioning or managing servers. This makes it a good choice for applications that need to be highly scalable and require minimal operational overhead. Amazon Aurora is a MySQL and PostgreSQL-compatible relational database that is built for the cloud. It is highly scalable and available, making it a good choice for applications that require high performance and reliability.

## Question 41

A company needs to save the results from a medical trial to an Amazon S3 repository. The repository must allow a few scientists to add new files and must restrict all other users to read-only access. No users can have the ability to modify or delete any files in the repository. The company must keep every file in the repository for a minimum of 1 year after its creation date. Which of the following options is correct?

### Options

- Use an IAM role to restrict all users from deleting or changing objects in the S3 bucket. Use an S3 bucket policy to only allow the IAM role.
- Configure the S3 bucket to invoke an AWS Lambda function every time an object is added. Configure the function to track the hash of the saved object so that modified objects can be marked accordingly.
- Use S3 Object Lock in governance mode with a legal hold of 1 year.
- __Use S3 Object Lock in compliance mode with a retention period of 365 days.__

### Correct Answer

Use S3 Object Lock in compliance mode with a retention period of 365 days.

### Explanation

S3 Object Lock is a feature that allows you to protect objects from being overwritten or deleted for a specific period of time. Compliance mode is the most restrictive mode of S3 Object Lock. It prevents all users, including the root user, from overwriting or deleting objects in the bucket.

## Question 42

A medical records company is hosting an application on Amazon EC2 instances. The application processes customer data files that are stored on Amazon S3. The EC2 instances are hosted in public subnets. The EC2 instances access Amazon S3 over the internet, but they do not require any other network access. A new requirement mandates that the network traffic for file transfers take a private route and not be sent over the internet. Which change to the network architecture should a solutions architect recommend to meet this requirement?

### Options

- Configure the security group for the EC2 instances to restrict outbound traffic so that only traffic to the S3 prefix list is permitted.
- Create a NAT gateway. Configure the route table for the public subnets to send traffic to Amazon S3 through the NAT gateway.
- Remove the internet gateway from the VPC. Set up an AWS Direct Connect connection, and route traffic to Amazon S3 over the Direct Connect connection.
- __Move the EC2 instances to private subnets. Create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets.__

### Correct Answer

Move the EC2 instances to private subnets. Create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets.

### Explanation

The best change to the network architecture to meet the requirement that the network traffic for file transfers take a private route and not be sent over the internet is to move the EC2 instances to private subnets and create a VPC endpoint for Amazon S3, and link the endpoint to the route table for the private subnets. This solution will allow the EC2 instances to access Amazon S3 without having to go over the internet. Instead, the traffic will be routed through the VPC endpoint, which is a secure and private connection between the VPC and Amazon S3.

## Question 43

In a VPC network, access control lists (ACLs) act as a firewall for associated subnets, controlling both inbound and outbound traffic at the __________ level.

### Options

- EC2
- VPC
- __Subnet__
- Database

### Correct Answer

Subnet

### Explanation

In a VPC network, access control lists (ACLs) act as a firewall for associated subnets, controlling both inbound and outbound traffic at the subnet level.

## Question 44

A company has a large Microsoft SharePoint deployment running on-premises that requires Microsoft Windows shared file storage. The company wants to migrate this workload to the AWS Cloud and is considering various storage options. The storage solution must be highly available and integrated with Active Directory for access control. Which of the following options is correct?

### Options

-  Create an SMB file share on an AWS Storage Gateway file gateway in two Availability Zones.
- Configure Amazon EFS storage and set the Active Directory domain for authentication.
- __Create an Amazon FSx for Windows File Server file system on AWS and set the Active Directory domain for authentication.__
- Create an Amazon S3 bucket and configure Microsoft Windows Server to mount it as a volume.

### Correct Answer

Create an Amazon FSx for Windows File Server file system on AWS and set the Active Directory domain for authentication.

### Explanation

Creating read replicas is the most effective way to separate read traffic from write traffic in an Amazon RDS MySQL DB instance. Read replicas are synchronized with the source database in real time, so they always have access to the most up-to-date data.

## Question 45

An IT company has registered its domain name with Amazon Route 53. The company uses Amazon API Gateway in the ca-central-1 Region as a public interface for its backend microservice APIs. Third-party services consume the APIs securely. The company wants to design its API Gateway URL with the company's domain name and corresponding certificate so that the third-party services can use HTTPS. Which of the following options is correct?

### Options

- Create stage variables in API Gateway with Name="Endpoint-URL" and Value="Company Domain Name" to overwrite the default URL. Import the public certificate associated with the company's domain name into AWS Certificate Manager (ACM).
- Create a Regional API Gateway endpoint. Associate the API Gateway endpoint with the company's domain name. Import the public certificate associated with the company's domain name into AWS Certificate Manager (ACM) in the us-east-1 Region. Attach the certificate to the API Gateway APIs. Create Route 53 DNS records with the company's domain name. Point an A record to the company's domain name.
- Create Route 53 DNS records with the company's domain name. Point the alias record to the Regional API Gateway stage endpoint. Import the public certificate associated with the company's domain name into AWS Certificate Manager (ACM) in the us-east-1 Region.
- __Create a Regional API Gateway endpoint. Associate the API Gateway endpoint with the company's domain name. Import the public certificate associated with the company's domain name into AWS Certificate Manager (ACM) in the same Region. Attach the certificate to the API Gateway endpoint. Configure Route 53 to route traffic to the API Gateway endpoint.__

### Correct Answer

Create a Regional API Gateway endpoint. Associate the API Gateway endpoint with the company's domain name. Import the public certificate associated with the company's domain name into AWS Certificate Manager (ACM) in the same Region. Attach the certificate to the API Gateway endpoint. Configure Route 53 to route traffic to the API Gateway endpoint.

### Explanation

This solution will allow the company to use its own domain name and certificate for its API Gateway endpoint. The certificate will be imported into ACM in the same Region as the API Gateway endpoint, so that it can be used to secure the endpoint. Route 53 will be configured to route traffic to the API Gateway endpoint, so that third-party services can access the APIs securely.

## Question 46

An application runs on Amazon EC2 instances across multiple Availability Zonas. The instances run in an Amazon EC2 Auto Scaling group behind an Application Load Balancer. The application performs best when the CPU utilization of the EC2 instances is at or near 40%. What should a solutions architect do to maintain the desired performance across all instances in the group?

### Options

- Use an AWS Lambda function ta update the desired Auto Scaling group capacity.
- __Use a target tracking policy to dynamically scale the Auto Scaling group.__
- Use a simple scaling policy to dynamically scale the Auto Scaling group.
- Use scheduled scaling actions to scale up and scale down the Auto Scaling group.

### Correct Answer

Use a target tracking policy to dynamically scale the Auto Scaling group.

### Explanation

A target tracking policy is a type of dynamic scaling policy that allows you to specify a target metric and a target value. Amazon EC2 Auto Scaling will then automatically scale the Auto Scaling group to maintain the target metric at the target value. In this case, the target metric should be the CPU utilization of the EC2 instances in the Auto Scaling group. The target value should be 40%. Amazon EC2 Auto Scaling will then automatically scale the Auto Scaling group up or down to maintain the CPU utilization of the EC2 instances at or near 40%. This will ensure that the application always has the resources it needs to perform at its best.

## Question 47

Which of the following strategies does AWS use to deliver the promised levels of DynamoDB performance? (Select two)

### Options

- AWS deploys Read Replicas of the database to balance the load.
- __The Database is partitioned across a number of nodes.__
- AWS deploy caching instances in front of the DynamoDB cluster.
- __Data is stored on Solid State Drives (SSDs).__
- DynamoDB instances can be configured with EBS-Optimised connections.

### Correct Answer

The Database is partitioned across a number of nodes.  
Data is stored on Solid State Drives (SSDs).

### Explanation

The Database is partitioned across a number of nodes. This helps to distribute the load across multiple nodes, which improves performance and scalability. Data is stored on Solid State Drives (SSDs). SSDs provide much faster read and write speeds than traditional hard disk drives (HDDs), which improves performance.

## Question 48

A company has an Amazon S3 bucket that contains critical data. The company must protect the data from accidental deletion. Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)

### Options

- __Enable versioning on the S3 bucket.__
- Create a lifecycle policy for the objects in the S3 bucket.
- Create a bucket policy on the S3 bucket.
- __Enable MFA Delete on the S3 bucket.__
-  Enable default encryption on the S3 bucket.

### Correct Answer

Enable versioning on the S3 bucket.  
Enable MFA Delete on the S3 bucket.

### Explanation

Enable versioning on the S3 bucket- This will create a historical copy of every object that is deleted from the bucket. This means that even if an object is deleted, it can be restored from the version history. Enable MFA Delete on the S3 bucket- This will require the user to enter their MFA token in order to delete an object from the bucket. This helps to prevent accidental deletion of objects.

## Question 49

A company has created an image analysis application in which users can upload photos and add photo frames to their images. The users upload images and metadata to indicate which photo frames they want to add to their images. The application uses a single Amazon EC2 instance and Amazon DynamoDB to store the metadata. The application is becoming more popular, and the number of users is increasing. The company expects the number of concurrent users to vary significantly depending on the time of day and day of week. The company must ensure that the application can scale to meet the needs of the growing user base. Which of the following options is correct?

### Options

- Use AWS Lambda to process the photos. Store the photos and metadata in DynamoDB.
- Increase the number of EC2 instances to three. Use Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volumes to store the photos and metadata.
- __ Use AWS Lambda to process the photos. Store the photos in Amazon S3. Retain DynamoDB to store the metadata.__
- Use Amazon Kinesis Data Firehose to process the photos and to store the photos and metadata.

### Correct Answer

Use AWS Lambda to process the photos. Store the photos in Amazon S3. Retain DynamoDB to store the metadata.

### Explanation

This architecture is highly available because it has multiple components that are designed to fail over to a secondary component if the primary component fails. For example, if the primary ActiveMQ broker fails, the standby broker will automatically take over. If a consumer EC2 instance fails, Auto Scaling will automatically launch a new instance. If the primary MySQL database fails, the secondary MySQL database will automatically take over.

## Question 50

My company has an application that runs on Amazon EC2 instances and uses an Amazon Aurora database. The EC2 instances connect to the database by using user names and passwords that are stored locally in a file. The company wants to minimize the operational overhead of credential management. Which of the following options is correct?

### Options

- Create an encrypted Amazon Elastic Block Store (Amazon EBS) volume for each EC2 instance. Attach the new EBS volume to each EC2 instance. Migrate the credential file to the new EBS volume. Point the application to the new EBS volume.
- Create an Amazon S3 bucket to store objects that are encrypted with an AWS Key Management Service (AWS KMS) encryption  key. Migrate the credential file to the S3 bucket. Point the application to the S3 bucket.
- __Use AWS Secrets Manager. Turn on automatic rotation.__
- Use AWS Systems Manager Parameter Store. Turn on automatic rotation.

### Correct Answer

Use AWS Secrets Manager. Turn on automatic rotation.

### Explanation

To minimize operational overhead in managing credentials, a solutions architect should use AWS Secrets Manager to securely store and manage the database credentials, and modify the application code to retrieve the credentials dynamically from Secrets Manager instead of storing them locally in a file.

## Question 51

An IT company is launching a new application and will display application metrics on an Amazon CloudWatch dashboard. The company's product manager needs to access this dashboard periodically. The product manager does not have an AWS account. A solutions architect must provide access to the product manager by following the principle of least privilege. Which of the following options is correct?

### Options

- Create an IAM user specifically for the product manager. Attach the CloudWatchReadOnlyAccess AWS managed policy to the user. Share the new login credentials with the product manager. Share the browser URL of the correct dashboard with the product manager.
- __Share the dashboard from the CloudWatch console. Enter the product manager's email address, and complete the sharing steps. Provide a shareable link for the dashboard to the product manager.__
- Deploy a bastion server in a public subnet. When the product manager requires access to the dashboard, start the server and share the RDP credentials. On the bastion server, ensure that the browser is configured to open the dashboard URL with cached AWS credentials that have appropriate permissions to view the dashboard.
- Create an IAM user for the company's employees. Attach the ViewOnlyAccess AWS managed policy to the IAM user. Share the new login credentials with the product manager. Ask the product manager to navigate to the CloudWatch console and locate the dashboard by name in the Dashboards section.

### Correct Answer

Share the dashboard from the CloudWatch console. Enter the product manager's email address, and complete the sharing steps. Provide a shareable link for the dashboard to the product manager.

### Explanation

This solution will allow the product manager to access the dashboard without having to create an AWS account or IAM user. The product manager will only be able to view the dashboard, and they will not be able to make any changes to it. This meets the principle of least privilege, because the product manager is only given the permissions that they need to access the dashboard.

## Question 52

A company recently launched a variety of new workloads on Amazon EC2 instances in its AWS account. The company needs to create a strategy to access and administer the instances remotely and securely. The company needs to implement a repeatable process that works with native AWS services and follows the AWS Well-Architected Framework. Which of the following options is correct?

### Options

- __Attach the appropriate IAM role to each existing instance and new instance. Use AWS Systems Manager Session Manager to establish a remote SSH session.__
- Establish an AWS Site-to-Site VPN connection. Instruct administrators to use their local on-premises machines to connect directly to the instances by using SSH keys across the VPN tunnel.
- Use the EC2 serial console to directly access the terminal interface of each instance for administration.
- Create an administrative SSH key pair. Load the public key into each EC2 instance. Deploy a bastion host in a public subnet to provide a tunnel for administration of each instance.

### Correct Answer

Attach the appropriate IAM role to each existing instance and new instance. Use AWS Systems Manager Session Manager to establish a remote SSH session.

### Explanation

AWS Systems Manager Session Manager is a fully-managed service that allows you to securely access your EC2 instances, on-premises instances, and virtual machines (VMs) through an interactive one-click browser-based shell or through the AWS CLI. Session Manager uses the SSM Agent, which is installed on your instances, to create a secure tunnel to your browser or CLI. This eliminates the need to open inbound ports on your instances, which can improve your security posture. To use Session Manager, you simply need to attach the appropriate IAM role to your instances. This role will grant you permission to access your instances using Session Manager. Once you have attached the role, you can start a session by clicking on the Session Manager button in the AWS Management Console. Session Manager is a highly scalable and reliable service. It is also very easy to use, making it the best solution for accessing and administering your EC2 instances remotely and securely with the LEAST operational overhead.

## Question 53

Each EC2 instance has a default network interface that is assigned a primary private IP address on your Amazon VPC network. What is the name given to the additional network interfaces that can be created and attached to any Amazon EC2 instance in your VPC?

### Options

- AWS Network ACL
- AWS Elastic Interface
- __Elastic Network Interface__
- Elastic IP Address

### Correct Answer

Elastic Network Interface

### Explanation

The additional network interfaces that can be created and attached to any Amazon EC2 instance in your VPC are called Elastic Network Interfaces (ENIs). ENIs are virtual network interfaces that can be attached to EC2 instances to provide additional network connectivity.

## Question 54

A company wants to use high performance computing (HPC) infrastructure on AWS for financial risk modeling. The company’s HPC workloads run on Linux. Each HPC workflow runs on hundreds of Amazon EC2 Spot Instances, is short-lived, and generates thousands of output files that are ultimately stored in persistent storage for analytics and long-term future use. The company seeks a cloud storage solution that permits the copying of on-premises data to long-term persistent storage to make data available for processing by all EC2 instances. The solution should also be a high performance file system that is integrated with persistent storage to read and write datasets and output files. Which combination of AWS services meets these requirements?

### Options

- Amazon FSx for Windows File Server integrated with Amazon S3
- Amazon S3 bucket with a VPC endpoint integrated with an Amazon Elastic Block Store (Amazon EBS) General Purpose SSD (gp2) volume
- Amazon S3 Glacier integrated with Amazon Elastic Block Store (Amazon EBS)
- __Amazon FSx for Lustre integrated with Amazon S3__

### Correct Answer

Amazon FSx for Lustre integrated with Amazon S3

### Explanation

Amazon FSx for Lustre is a fully managed, high-performance file system that is optimized for compute-intensive workloads such as HPC and machine learning. It provides a scalable and reliable file system that can be used to store and access large datasets. Amazon S3 is a highly scalable, object storage service that is designed for storing and retrieving any amount of data from anywhere. It is a cost-effective and durable storage option for long-term data retention.

## Question 55

An IT solutions architect is using Amazon S3 to design the storage architecture of a new digital media application. The media files must be resilient to the loss of an Availability Zone. Some files are accessed frequently while other files are rarely accessed in an unpredictable pattern. The solutions architect must minimize the costs of storing and retrieving the media files. Which of the following options is correct?

### Options

- __S3 Intelligent-Tiering__
- S3 One Zone-Infrequent Access (S3 One Zone-IA)
- S3 Standard-Infrequent Access (S3 Standard-IA)
- S3 Standard

### Correct Answer

S3 Intelligent-Tiering

### Explanation

S3 Standard-IA is designed for infrequently accessed data, which is a good fit for the media files that are rarely accessed in an unpredictable pattern. S3 Standard-IA is also cross-Region replicated, providing resilience to the loss of an Availability Zone. Additionally, S3 Standard-IA has a lower storage and retrieval cost compared to S3 Standard and S3 Intelligent-Tiering, which makes it a cost-effective option for storing infrequently accessed data.

## Question 56

A company is developing a file-sharing application that will use an Amazon S3 bucket for storage. The company wants to serve all the files through an Amazon CloudFront distribution. The company does not want the files to be accessible through direct navigation to the S3 URL. Which of the following options is correct?

### Options

- Write individual policies for each S3 bucket to grant read permission for only CloudFront access.
- __Create an origin access identity (OAI). Assign the OAI to the CloudFront distribution. Configure the S3 bucket permissions so that only the OAI has read permission.__
- Write an S3 bucket policy that assigns the CloudFront distribution ID as the Principal and assigns the target S3 bucket as the Amazon Resource Name (ARN).
- Create an IAM user. Grant the user read permission to objects in the S3 bucket. Assign the user to CloudFront.

### Correct Answer

Create an origin access identity (OAI). Assign the OAI to the CloudFront distribution. Configure the S3 bucket permissions so that only the OAI has read permission.

### Explanation

To meet the requirements, the solutions architect should create an origin access identity (OAI) and assign it to the CloudFront distribution. The S3 bucket permissions should be configured so that only the OAI has read permission. An OAI is a special CloudFront user that is associated with a CloudFront distribution and is used to give CloudFront access to the files in an S3 bucket. By using an OAI, the company can serve the files through the CloudFront distribution while preventing direct access to the S3 bucket.

## Question 57

A my company is storing backup files by using Amazon S3 Standard storage. The files are accessed frequently for 1 month. However, the files are not accessed after 1 month. The company must keep the files indefinitely. Which of the following options is correct?

### Options

- Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) after 1 month.
- Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 1 month.
- __ Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 Glacier Deep Archive after 1 month.__
- Configure S3 Intelligent-Tiering to automatically migrate objects.

### Correct Answer

Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 Glacier Deep Archive after 1 month.

## Question 58

A development team needs to host a website that will be accessed by sales teams. The website contents consist of HTML, CSS, client-side JavaScript, and images. Which method is the MOST cost-effective for hosting the website?

### Options

- __ Create an Amazon S3 bucket and host the website there.__
- Configure an Application Load Balancer with an AWS Lambda target that uses the Express.js framework.
- Containerize the website and host it in AWS Fargate.
- Deploy a web server on an Amazon EC2 instance to host the website.

### Correct Answer

Create an Amazon S3 bucket and host the website there.

### Explanation

Amazon S3 is a highly scalable and cost-effective object storage service. It is a good choice for hosting static websites, as it does not require any server infrastructure. You can simply upload your website files to an S3 bucket and make them public.

## Question 59

A website runs a custom web application that receives a burst of traffic each day at noon. The users upload new pictures and content daily, but have been complaining of timeouts. The architecture uses Amazon EC2 Auto Scaling groups, and the application consistently takes 1 minute to initiate upon boot up before responding to user requests. How should a solutions architect redesign the architecture to better respond to changing traffic?

### Options

- Configure Amazon CloudFront to use an Application Load Balancer as the origin.
- Configure a Network Load Balancer with a slow start configuration.
- Configure Amazon ElastiCache for Redis to offload direct requests from the EC2 instances.
- __Configure an  Auto Scaling step scaling policy with an EC2 instance warmup condition.__

### Correct Answer

Configure an Auto Scaling step scaling policy with an EC2 instance warmup condition.

### Explanation

The current configuration puts new EC2 instances into service before they are able to respond to transactions. This could also cause the instances to overscale. With a step scaling policy, you can specify the number of seconds that it takes for a newly launched instance to warm up. Until its specified warm-up time has expired, an EC2 instance is not counted toward the aggregated metrics of the Auto Scaling group. While scaling out, the Auto Scaling logic does not consider EC2 instances that are warming up as part of the current capacity of the Auto Scaling group. Therefore, multiple alarm breaches that fall in the range of the same step adjustment result in a single scaling activity. This ensures that you do not add more instances than you need.

## Question 60

A company has applications that run on Amazon EC2 instances in a VPC. One of the applications needs to call the Amazon S3 API to store and read objects. According to the company's security regulations, no traffic from the applications is allowed to travel across the internet. Which of the following options is correct?

### Options

- __Configure an S3 gateway endpoint.__
- Configure a NAT gateway in the same subnet as the EC2 instances.
- Create an S3 bucket in a private subnet.
- Create an S3 bucket in the same AWS Region as the EC2 instances.

### Correct Answer

Configure an S3 gateway endpoint.

### Explanation

An S3 gateway endpoint is a VPC endpoint that allows you to route traffic to S3 from within your VPC without having to go through the public internet. This is a good solution for companies that need to meet strict security requirements

## Question 61

An Application company wants to run applications in containers in the AWS Cloud. These applications are stateless and can tolerate disruptions within the underlying infrastructure. The company needs a solution that minimizes cost and operational overhead. Which of the following options is correct?

### Options

- __Use Spot Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.__
- Use Spot Instances in an Amazon EC2 Auto Scaling group to run the application containers.
- Use On-Demand Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.
- Use On-Demand Instances in an Amazon EC2 Auto Scaling group to run the application containers.

### Correct Answer

Use Spot Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.

### Explanation

Spot Instances are unused EC2 capacity that AWS makes available at a significant discount compared to On-Demand Instance prices. Spot Instances are a good fit for stateless applications that can tolerate disruptions, such as the company's application containers./Amazon EKS is a managed Kubernetes service that makes it easy to run Kubernetes on AWS. Amazon EKS managed node groups are groups of EC2 instances that are managed by Amazon EKS.

## Question 62

An IT company uses Amazon EC2 Reserved Instances to run its data processing workload. The nightly job typically takes 7 hours to run and must finish within a 10-hour time window. The company anticipates temporary increases in demand at the end of each month that will cause the job to run over the time limit with the capacity of the current resources. Once started, the processing job cannot be interrupted before completion. The company wants to implement a solution that would provide increased resource capacity as cost-effectively as possible. Which of the following options is correct?

### Options

- Increase the EC2 instance size in the EC2 reservation to support the increased workload.
- Create a second EC2 reservation for additional instances.
- __Deploy On-Demand Instances during periods of high demand.__
- Deploy Spot Instances during periods of high demand.

### Correct Answer

Deploy On-Demand Instances during periods of high demand.

### Explanation

While Spot Instances would be the least costly option, they are not suitable for jobs that cannot be interrupted or must complete within a certain time period. On-Demand Instances would be billed for the number of seconds they are running. Reference: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-on-demand-instances.html

## Question 63

Our company runs a highly available image-processing application on Amazon EC2 instances in a single VPC. The EC2 instances run inside several subnets across multiple Availability Zones. The EC2 instances do not communicate with each other. However, the EC2 instances download images from Amazon S3 and upload images to Amazon S3 through a single NAT gateway. The company is concerned about data transfer charges. What is the MOST cost-effective way for the company to avoid Regional data transfer charges?

### Options

- Launch the NAT gateway in each Availability Zone.
- Replace the NAT gateway with a NAT instance.
- Provision an EC2 Dedicated Host to run the EC2 instances.
- __ Deploy a gateway VPC endpoint for Amazon S3.__

### Correct Answer

Deploy a gateway VPC endpoint for Amazon S3.

### Explanation

A gateway VPC endpoint is a private network endpoint for Amazon S3 that allows you to access S3 resources without incurring any internet or regional data transfer charges. When you deploy a gateway VPC endpoint, you create a route in your VPC routing table that points to the endpoint. This route will be used by your EC2 instances to access S3 resources, and no data will be transferred over the internet.The other solutions are not as cost-effective as deploying a gateway VPC endpoint. For example, launching the NAT gateway in each Availability Zone would increase the cost of the NAT gateway, and replacing the NAT gateway with a NAT instance would not eliminate regional data transfer charges.

## Question 64

What services are required for Auto Scaling ? (choose 3 correct answers)

### Options

- SNS
- __ELB__
- __EC2__
- SQS
- __Cloudwatch__

### Correct Answer

ELB  
EC2  
Cloudwatch

### Explanation

Amazon CloudWatch: Auto Scaling uses CloudWatch metrics to monitor the performance of your application and scale it up or down based on demand. Elastic Load Balancing (ELB): ELB distributes traffic across multiple targets, such as EC2 instances, Auto Scaling groups, and containers. This helps to ensure that your application is available and scalable during high demand. Amazon EC2: Auto Scaling scales your application by launching and terminating EC2 instances.

## Question 65

AWS requires ____________ when you need to specify a resource uniquely across all of AWS, such as in IAM policies, Amazon Relational Database Service (Amazon RDS) tags, and API calls.

### Options

- __Amazon Resource Names__
- User IAM Policy
- User ID
- Account Id

### Correct Answer

Amazon Resource Names

### Explanation

AWS requires Amazon Resource Names (ARNs) when you need to specify a resource uniquely across all of AWS, such as in IAM policies, Amazon Relational Database Service (Amazon RDS) tags, and API calls.

