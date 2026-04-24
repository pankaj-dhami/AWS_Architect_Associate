# AWS SAA Complete Practice Questions

## Question 1

A company hosted a web application in an Auto Scaling group of EC2 instances. The IT manager is concerned about the over-provisioning of the resources that can cause higher operating costs. A Solutions Architect has been instructed to create a cost-effective solution without affecting the performance of the application.

Which dynamic scaling policy should be used to satisfy this requirement?

### Options

- __Use target tracking scaling.__
- Use scheduled scaling.
- Use simple scaling.
- Use suspend and resume scaling.

### Correct Answer

Use target tracking scaling.

### Explanation

An Auto Scaling group contains a collection of Amazon EC2 instances that are treated as a logical grouping for the purposes of automatic scaling and management. An Auto Scaling group also enables you to use Amazon EC2 Auto Scaling features such as health check replacements and scaling policies. Both maintaining the number of instances in an Auto Scaling group and automatic scaling are the core functionality of the Amazon EC2 Auto Scaling service. The size of an Auto Scaling group depends on the number of instances that you set as the desired capacity. You can adjust its size to meet demand, either manually or by using automatic scaling.

Step scaling policies and simple scaling policies are two of the dynamic scaling options available for you to use. Both require you to create CloudWatch alarms for the scaling policies. Both require you to specify the high and low thresholds for the alarms. Both require you to define whether to add or remove instances, and how many, or set the group to an exact size. The main difference between the policy types is the step adjustments that you get with step scaling policies. When step adjustments are applied, and they increase or decrease the current capacity of your Auto Scaling group, the adjustments vary based on the size of the alarm breach.

The primary issue with simple scaling is that after a scaling activity is started, the policy must wait for the scaling activity or health check replacement to complete and the cooldown period to expire before responding to additional alarms. Cooldown periods help to prevent the initiation of additional scaling activities before the effects of previous activities are visible.

With a target tracking scaling policy, you can increase or decrease the current capacity of the group based on a target value for a specific metric. This policy will help resolve the over-provisioning of your resources. The scaling policy adds or removes capacity as required to keep the metric at, or close to, the specified target value. In addition to keeping the metric close to the target value, a target tracking scaling policy also adjusts to changes in the metric due to a changing load pattern.

Hence, the correct answer is: Use target tracking scaling.

The option that says: Use simple scaling is incorrect because you need to wait for the cooldown period to complete before initiating additional scaling activities. Target tracking or step scaling policies can trigger a scaling activity immediately without waiting for the cooldown period to expire.

The option that says: Use scheduled scaling is incorrect because this policy is mainly used for predictable traffic patterns. You need to use the target tracking scaling policy to optimize the cost of your infrastructure without affecting the performance.

The option that says: Use suspend and resume scaling is incorrect because this type is used to temporarily pause scaling activities triggered by your scaling policies and scheduled actions.

---

## Question 2

A Docker application, which is running on an Amazon ECS cluster behind a load balancer, is heavily using Amazon DynamoDB. The application requires improved database performance by distributing the workload evenly and utilizing the provisioned throughput efficiently.

Which of the following should be implemented for the DynamoDB table?

### Options

- Avoid using a composite primary key, which is composed of a partition key and a sort key.
- __Use partition keys with high-cardinality attributes, which have a large number of distinct values for each item.__
- Use partition keys with low-cardinality attributes, which have a few number of distinct values for each item.
- Reduce the number of partition keys in the DynamoDB table.

### Correct Answer

Use partition keys with high-cardinality attributes, which have a large number of distinct values for each item.

### Explanation

The partition key portion of a table's primary key determines the logical partitions in which a table's data is stored. This in turn affects the underlying physical partitions. Provisioned I/O capacity for the table is divided evenly among these physical partitions. Therefore a partition key design that doesn't distribute I/O requests evenly can create "hot" partitions that result in throttling and use your provisioned I/O capacity inefficiently.

The optimal usage of a table's provisioned throughput depends not only on the workload patterns of individual items, but also on the partition-key design. This doesn't mean that you must access all partition key values to achieve an efficient throughput level, or even that the percentage of accessed partition key values must be high. It does mean that the more distinct partition key values that your workload accesses, the more those requests will be spread across the partitioned space. In general, you will use your provisioned throughput more efficiently as the ratio of partition key values accessed to the total number of partition key values increases.

Hence, the correct answer is: Use partition keys with high-cardinality attributes, which have a large number of distinct values for each item.

The option that says: Reducing the number of partition keys in the DynamoDB table is incorrect. Instead of doing this, you should actually add more to improve its performance to distribute the I/O requests evenly and not simply avoid "hot" partitions.

The option that says: Using partition keys with low-cardinality attributes, which have a few number of distinct values for each item is incorrect because this is only the exact opposite of the correct answer. Remember that the more distinct partition key values your workload accesses, the more those requests will be spread across the partitioned space. Conversely, the less distinct partition key values, the less evenly spread it would be across the partitioned space, which effectively slows the performance.

The option that says: Avoid using a composite primary key, which is composed of a partition key and a sort key is incorrect because as mentioned, a composite primary key will provide more partition for the table and in turn, improves the performance. Hence, it should be used and not avoided.

---

## Question 3

A tech company has a CRM application hosted on an Auto Scaling group of On-Demand EC2 instances with different instance types and sizes. The application is extensively used during office hours from 9 in the morning to 5 in the afternoon. Their users are complaining that the performance of the application is slow during the start of the day but then works normally after a couple of hours.

Which of the following is the MOST operationally efficient solution to implement to ensure the application works properly at the beginning of the day?

### Options

- Configure a Dynamic scaling policy for the Auto Scaling group to launch new instances based on the CPU utilization.
- __Configure a Scheduled scaling policy for the Auto Scaling group to launch new instances before the start of the day.__
- Configure a Predictive scaling policy for the Auto Scaling group to automatically adjust the number of Amazon EC2 instances
- Configure a Dynamic scaling policy for the Auto Scaling group to launch new instances based on the Memory utilization.

### Correct Answer

Configure a Scheduled scaling policy for the Auto Scaling group to launch new instances before the start of the day.

### Explanation

Scaling based on a schedule allows you to scale your application in response to predictable load changes. For example, every week the traffic to your web application starts to increase on Wednesday, remains high on Thursday, and starts to decrease on Friday. You can plan your scaling activities based on the predictable traffic patterns of your web application.

To configure your Auto Scaling group to scale based on a schedule, you create a scheduled action. The scheduled action tells Amazon EC2 Auto Scaling to perform a scaling action at specified times. To create a scheduled scaling action, you specify the start time when the scaling action should take effect and the new minimum, maximum, and desired sizes for the scaling action. At the specified time, Amazon EC2 Auto Scaling updates the group with the values for minimum, maximum, and desired size specified by the scaling action. You can create scheduled actions for scaling one time only or for scaling on a recurring schedule.

Hence, configuring a Scheduled scaling policy for the Auto Scaling group to launch new instances before the start of the day is the correct answer. You need to configure a Scheduled scaling policy. This will ensure that the instances are already scaled up and ready before the start of the day since this is when the application is used the most.

---

## Question 4

A content management system (CMS) is hosted on a fleet of auto-scaled, On-Demand Amazon EC2 instances that use Amazon Aurora as its database. Currently, the system stores the file documents that users upload in one of the attached Amazon EBS volumes. The system's performance has been observed to be slow, and the manager has instructed the team to improve the architecture.

In this scenario, which solution should be implemented to achieve a scalable, highly available, POSIX-compliant shared file system?

### Options

- Leverage Amazon ElastiCache to cache frequently accessed data and reduce latency
- __Use Amazon EFS to provide a shared file system for concurrent access to data__
- Upgrade your existing EBS volumes to Provisioned IOPS SSD volumes
- Create an Amazon S3 bucket and use this as the storage for the CMS

### Correct Answer

Use Amazon EFS to provide a shared file system for concurrent access to data

### Explanation

Amazon Elastic File System (Amazon EFS) provides simple, scalable, elastic file storage for use with AWS Cloud services and on-premises resources. When mounted on Amazon EC2 instances, an Amazon EFS file system provides a standard file system interface and file system access semantics, allowing you to seamlessly integrate Amazon EFS with your existing applications and tools. Multiple Amazon EC2 instances can access an Amazon EFS file system at the same time, allowing Amazon EFS to provide a common data source for workloads and applications running on more than one Amazon EC2 instance.

This particular scenario tests your understanding of EBS, EFS, and S3. In this scenario, there is a fleet of On-Demand EC2 instances that store file documents from the users to one of the attached EBS Volumes. The system performance is quite slow because the architecture doesn't provide the EC2 instances parallel shared access to the file documents.

Amazon Elastic File System (Amazon EFS)

Although an EBS Volume can be attached to multiple EC2 instances, you can only do so on instances within an availability zone. What we need is highly available storage that can span multiple availability zones. Take note as well that the type of storage needed here is file storage, which means that S3 is not the best service to use because it is primarily used for object storage.

Hence, the correct answer is: Use Amazon EFS to provide a shared file system for concurrent access to data.

---

## Question 5

A company has a web application that uses Internet Information Services (IIS) for Windows Server. A file share is used to store the application data on the network-attached storage of the company’s on-premises data center. To achieve a highly available system, the company plans to migrate the application and file share to AWS.

Which of the following can be used to fulfill this requirement?

### Options

- Migrate the existing file share configuration to Amazon EFS.
- __Migrate the existing file share configuration to Amazon FSx for Windows File Server.__
- Migrate the existing file share configuration to Amazon EBS.
- Migrate the existing file share configuration to AWS Storage Gateway.

### Correct Answer

Migrate the existing file share configuration to Amazon FSx for Windows File Server.

### Explanation

Amazon FSx for Windows File Server provides fully managed Microsoft Windows file servers, backed by a fully native Windows file system. Amazon FSx for Windows File Server has the features, performance, and compatibility to easily lift and shift enterprise applications to the AWS Cloud. It is accessible from Windows, Linux, and macOS compute instances and devices. Thousands of compute instances and devices can access a file system concurrently.

In this scenario, you need to migrate your existing file share configuration to the cloud. Among the options given, the best possible answer is Amazon FSx. A file share is a specific folder in your file system, including the folder's subfolders, which you make accessible to your compute instances via the SMB protocol. To migrate file share configurations from your on-premises file system, you must migrate your files first to Amazon FSx before migrating your file share configuration.

Hence, the correct answer is: Migrate the existing file share configuration to Amazon FSx for Windows File Server.

---

## Question 6

A company has a cloud architecture composed of Linux and Windows Amazon EC2 instances that process high volumes of financial data 24 hours a day, 7 days a week. To ensure high availability of the systems, the Solutions Architect must create a solution that enables monitoring of memory and disk utilization metrics for all instances.

Which of the following is the most suitable monitoring solution to implement?

### Options

- Enable the Enhanced Monitoring option in EC2 and install Amazon CloudWatch agent to all the EC2 instances to be able to view the memory and disk utilization in the CloudWatch dashboard.
- __Install the Amazon CloudWatch agent to all the EC2 instances that gather the memory and disk utilization data. View the custom metrics in the CloudWatch console.__
- Use the default Amazon CloudWatch configuration to EC2 instances where the memory and disk utilization metrics are already available. Install the AWS Systems Manager (SSM) Agent on all the EC2 instances and enable AWS Systems Manager Inventory to track instance configuration and metadata.
- Use Amazon Inspector and install the Inspector agent to all EC2 instances.

### Correct Answer

Install the Amazon CloudWatch agent to all the EC2 instances that gather the memory and disk utilization data. View the custom metrics in the CloudWatch console.

### Explanation

Amazon CloudWatch has available Amazon EC2 Metrics for you to use for monitoring CPU utilization, Network utilization, Disk performance, and Disk Reads/Writes. In case you need to monitor the below items, you need to prepare a custom metric using a Perl or other shell script, as there are no ready-to-use metrics for the following:

Memory utilization

Disk swap utilization

Disk space utilization

Page file utilization

Log collection

Take note that there is a multi-platform CloudWatch agent which can be installed on both Linux and Windows-based instances. You can use a single agent to collect both system metrics and log files from Amazon EC2 instances and on-premises servers. This agent supports both Windows Server and Linux and enables you to select the metrics to be collected, including sub-resource metrics such as per-CPU core. It is recommended that you use the new agent instead of the older monitoring scripts to collect metrics and logs.

---

## Question 7

A company collects atmospheric data such as temperature, air pressure, and humidity from different countries. Each site location is equipped with various weather instruments and a high-speed Internet connection. The average collected data in each location is around 500 GB and will be analyzed by a weather forecasting application hosted in Northern Virginia. The Solutions Architect must determine the fastest way to aggregate all the data.

Which of the following options can satisfy the given requirement?

### Options

- Set up a Site-to-Site VPN connection.
- Upload the data to the closest Amazon S3 bucket. Set up a cross-region replication and copy the objects to the destination bucket.
- __Enable Transfer Acceleration in the destination bucket and upload the collected data using Multipart Upload.__
- Use AWS Snowball Edge to transfer large amounts of data.

### Correct Answer

Enable Transfer Acceleration in the destination bucket and upload the collected data using Multipart Upload.

### Explanation

Amazon S3 is object storage built to store and retrieve any amount of data from anywhere on the Internet. It’s a simple storage service that offers industry-leading durability, availability, performance, security, and virtually unlimited scalability at very low costs. Amazon S3 is also designed to be highly flexible. Store any type and amount of data that you want; read the same piece of data a million times or only for emergency disaster recovery; build a simple FTP application or a sophisticated web application.

Since the weather forecasting application is located in N.Virginia, you need to transfer all the data in the same AWS Region. With Amazon S3 Transfer Acceleration, you can speed up content transfers to and from Amazon S3 by as much as 50-500% for long-distance transfer of larger objects. Multipart upload allows you to upload a single object as a set of parts. After all the parts of your object are uploaded, Amazon S3 then presents the data as a single object. This approach is the fastest way to aggregate all the data.

---

## Question 8

An online learning company hosts its Microsoft .NET e-Learning application on a Windows Server in its on-premises data center. The application uses an Oracle Database Standard Edition as its backend database.

The company wants a high-performing solution to migrate this workload to the AWS cloud to take advantage of the cloud’s high availability. The migration process should minimize development changes, and the environment should be easier to manage.

Which of the following options should be implemented to meet the company requirements? (Select TWO.)

### Options

- Refactor the application to .NET Core and run it as a serverless container service using Amazon Elastic Kubernetes Service (Amazon EKS) with AWS Fargate.
- __Rehost the on-premises .NET application to an AWS Elastic Beanstalk Multi-AZ environment which runs in multiple Availability Zones.__
- Provision and replatform the application to Amazon Elastic Container Service (Amazon ECS) with Amazon EC2 worker nodes. Use the Windows Server Amazon Machine Image (AMI) and deploy the .NET application using to the ECS cluster via the ECS Anywhere service.
- Use AWS Application Migration Service (AWS MGN) to migrate the on-premises Oracle database server to a new Amazon EC2 instance.
- __Perform a homogeneous migration by moving the Oracle database to Amazon RDS for Oracle in a Multi-AZ deployment using AWS Database Migration Service (AWS DMS).__

### Correct Answer

Rehost the on-premises .NET application to an AWS Elastic Beanstalk Multi-AZ environment which runs in multiple Availability Zones.

Perform a homogeneous migration by moving the Oracle database to Amazon RDS for Oracle in a Multi-AZ deployment using AWS Database Migration Service (AWS DMS).

### Explanation

AWS Database Migration Service (AWS DMS) is a cloud service that makes it easy to migrate relational databases, data warehouses, NoSQL databases, and other types of data stores. You can use AWS DMS to migrate your data into the AWS Cloud or between combinations of cloud and on-premises setups.

With AWS DMS, you can perform one-time migrations, and you can replicate ongoing changes to keep sources and targets in sync. If you want to migrate to a different database engine, you can use the AWS Schema Conversion Tool (AWS SCT) to translate your database schema to the new platform. You then use AWS DMS to migrate the data.

AWS Elastic Beanstalk reduces management complexity without restricting choice or control. You simply upload your application, and Elastic Beanstalk automatically handles the details of capacity provisioning, load balancing, scaling, and application health monitoring. Elastic Beanstalk supports applications developed in Go, Java, .NET, Node.js, PHP, Python, and Ruby. When you deploy your application, Elastic Beanstalk builds the selected supported platform version and provisions one or more AWS resources, such as Amazon EC2 instances, to run your application.

---

## Question 9

A medical records company is planning to store sensitive clinical trial data in an Amazon S3 repository with the object-level versioning feature enabled. The Solutions Architect is tasked with ensuring that no object can be overwritten or deleted by any user in a period of one year only. To meet the strict compliance requirements, the root user of the company’s AWS account must also be restricted from making any changes to an object in the S3 bucket.

Which of the following is the most secure way of storing the data in S3?

### Options

- Enable S3 Object Lock in governance mode with a legal hold of one year.
- __Enable S3 Object Lock in compliance mode with a retention period of one year.__
- Enable S3 Object Lock in governance mode with a retention period of one year.
- Enable S3 Object Lock in compliance mode with a legal hold of one year.

### Correct Answer

Enable S3 Object Lock in compliance mode with a retention period of one year.

### Explanation

With S3 Object Lock, you can store objects using a write-once-read-many (WORM) model. Object Lock can help prevent objects from being deleted or overwritten for a fixed amount of time or indefinitely. You can use Object Lock to help meet regulatory requirements that require WORM storage or to simply add another layer of protection against object changes and deletion.

S3 Object Lock provides two retention modes: Governance mode and Compliance mode. In compliance mode, a protected object version can't be overwritten or deleted by any user, including the root user in your AWS account.

---

## Question 10

An application consists of multiple Amazon EC2 instances in private subnets in different availability zones. The application uses a single NAT Gateway for downloading software patches from the Internet to the instances. There is a requirement to protect the application from a single point of failure when the NAT Gateway encounters a failure or if its availability zone goes down.

How should the Solutions Architect redesign the architecture to be more highly available and cost-effective?

### Options

- Create two NAT Gateways in each availability zone. Configure the route table in each public subnet to ensure that instances use the NAT Gateway in the same availability zone.
- __Create a NAT Gateway in each availability zone. Configure the route table in each private subnet to ensure that instances use the NAT Gateway in the same availability zone__
- Create three NAT Gateways in each availability zone. Configure the route table in each private subnet to ensure that instances use the NAT Gateway in the same availability zone.
- Create a NAT Gateway in each availability zone. Configure the route table in each public subnet to ensure that instances use the NAT Gateway in the same availability zone.

### Correct Answer

Create a NAT Gateway in each availability zone. Configure the route table in each private subnet to ensure that instances use the NAT Gateway in the same availability zone

### Explanation

A NAT Gateway is a highly available, managed Network Address Translation (NAT) service for your resources in a private subnet to access the Internet. NAT gateway is created in a specific Availability Zone and implemented with redundancy in that zone.

If you have resources in multiple Availability Zones and they share one NAT gateway, and if the NAT gateway’s Availability Zone is down, resources in the other Availability Zones lose Internet access. To create an Availability Zone-independent architecture, create a NAT gateway in each Availability Zone and configure your routing to ensure that resources use the NAT gateway in the same Availability Zone.

## Question 11

A company requires all the data stored in the cloud to be encrypted at rest. To easily integrate this with other AWS services, they must have full control over the encryption of the created keys and also the ability to immediately remove the key material from AWS KMS. The solution should also be able to audit the key usage independently of AWS CloudTrail.

Which of the following options will meet this requirement?

### Options

- Use AWS Key Management Service to create a KMS key in a custom key store and store the non-extractable key material in Amazon S3.
- __Use AWS Key Management Service to create a KMS key in a custom key store and store the non-extractable key material in AWS CloudHSM.__
- Use AWS Key Management Service to create AWS owned Keys and store the non-extractable key material in AWS CloudHSM.
- Use AWS Key Management Service to create AWS managed keys and store the non-extractable key material in AWS CloudHSM.

### Correct Answer

Use AWS Key Management Service to create a KMS key in a custom key store and store the non-extractable key material in AWS CloudHSM.

### Explanation

The AWS Key Management Service (KMS) custom key store feature combines the controls provided by AWS CloudHSM with the integration and ease of use of AWS KMS. You can configure your own CloudHSM cluster and authorize AWS KMS to use it as a dedicated key store for your keys rather than the default AWS KMS key store. When you create keys in AWS KMS you can choose to generate the key material in your CloudHSM cluster. KMS Keys that are generated in your custom key store never leave the HSMs in the CloudHSM cluster in plaintext and all AWS KMS operations that use those KMS keys are only performed on your HSMs.

AWS KMS can help you integrate with other AWS services to encrypt the data that you store in these services and control access to the keys that decrypt it. To immediately remove the key material from AWS KMS, you can use a custom key store. Take note that each custom key store is associated with an AWS CloudHSM cluster in your AWS account. Therefore, when you create an AWS KMS Key in a custom key store, AWS KMS generates and stores the non-extractable key material for the KMS key in an AWS CloudHSM cluster that you own and manage. This is also suitable if you want to be able to audit the usage of all your keys independently of AWS KMS or AWS CloudTrail.

Since you control your AWS CloudHSM cluster, you have the option to manage the lifecycle of your KMS keys independently of AWS KMS.

---

## Question 12

A government agency plans to store confidential tax documents on AWS. Due to the sensitive information in the files, the Solutions Architect must restrict the data access requests made to the storage solution to a specific Amazon VPC only. The solution should also prevent the files from being deleted or overwritten to meet the regulatory requirement of having a write-once-read-many (WORM) storage model.

Which combination of the following options should the Architect implement? (Select TWO.)

### Options

- Set up a new Amazon S3 bucket to store the tax documents and integrate it with AWS Network Firewall. Configure the Network Firewall to only accept data access requests from a specific VPC.
- Enable Object Lock but disable Object Versioning on the new Amazon S3 bucket to comply with the write-once-read-many (WORM) storage model requirement.
- __Create a new Amazon S3 bucket with the S3 Object Lock feature enabled. Store the documents in the bucket and set the Legal Hold option for object retention.__
- Store the tax documents in the Amazon S3 Glacier Instant Retrieval storage class. Use the PutBucketPolicy API to apply a bucket policy that restricts access requests to a specific VPC.
- __Configure an Amazon S3 Access Point for the S3 bucket to restrict data access to a particular VPC only.__

### Correct Answer

Create a new Amazon S3 bucket with the S3 Object Lock feature enabled. Store the documents in the bucket and set the Legal Hold option for object retention.

Configure an Amazon S3 Access Point for the S3 bucket to restrict data access to a particular VPC only.

### Explanation

Amazon S3 access points simplify data access for any AWS service or customer application that stores data in S3. Access points are named network endpoints that are attached to buckets that you can use to perform S3 object operations, such as GetObject and PutObject.

Each access point has distinct permissions and network controls that S3 applies for any request that is made through that access point. You can configure any access point to accept requests only from a virtual private cloud (VPC) to restrict Amazon S3 data access to a private network.

With S3 Object Lock, you can store objects using a write-once-read-many (WORM) model. Object Lock can help prevent objects from being deleted or overwritten for a fixed amount of time or indefinitely.

---

## Question 13

A cryptocurrency trading platform is using an API built in AWS Lambda and API Gateway. Due to the recent news and rumors about the upcoming price surge of Bitcoin, Ethereum and other cryptocurrencies, it is expected that the trading platform would have a significant increase in site visitors and new users in the coming days ahead.

In this scenario, how can you protect the backend systems of the platform from traffic spikes?

### Options

- Switch from using AWS Lambda and API Gateway to a more scalable and highly available architecture using EC2 instances, ELB, and Auto Scaling.
- Move the Lambda function in a VPC.
- __Enable throttling limits and result caching in API Gateway.__
- Use CloudFront in front of the API Gateway to act as a cache.

### Correct Answer

Enable throttling limits and result caching in API Gateway.

### Explanation

Amazon API Gateway provides throttling at multiple levels including global and by service call. Throttling limits can be set for standard rates and bursts. Amazon API Gateway tracks the number of requests per second and requests exceeding the limit receive a 429 HTTP response.

You can add caching to API calls by provisioning an Amazon API Gateway cache and specifying its size. This improves performance and reduces the traffic sent to your backend systems.

---

## Question 14

An online shopping platform is hosted on an Auto Scaling group of Amazon EC2 Spot instances and utilizes Amazon Aurora PostgreSQL as its database. It is required to optimize database workloads in the cluster by directing the production traffic to high-capacity instances and routing the reporting queries from the internal staff to the low-capacity instances.

Which is the most suitable configuration for the application as well as the Aurora database cluster to achieve this requirement?

### Options

- Do nothing since by default Aurora automatically directs traffic appropriately.
- Configure your application to use the reader endpoint for both production traffic and reporting queries.
- __Create a custom endpoint in Aurora based on the specified criteria for the production traffic and another custom endpoint to handle the reporting queries.__
- Use the instance endpoint for production traffic and the cluster endpoint for reporting queries.

### Correct Answer

Create a custom endpoint in Aurora based on the specified criteria for the production traffic and another custom endpoint to handle the reporting queries.

### Explanation

Amazon Aurora uses endpoints to abstract connections to DB instances. Custom endpoints allow you to route traffic to specific subsets of instances in a cluster. This enables directing production traffic to high-capacity instances while routing reporting queries to lower-capacity instances.

---

## Question 15

A company is using AWS Fargate to run a batch job whenever an object is uploaded to an Amazon S3 bucket. The minimum ECS task count is initially set to 1 to save on costs and should only be increased based on new objects uploaded to the S3 bucket.

Which is the most suitable option to implement with the LEAST amount of effort?

### Options

- __Set up an Amazon EventBridge (Amazon CloudWatch Events) rule to detect S3 object PUT operations and set the target to the ECS cluster to run a new ECS task.__
- Use CloudWatch alarms and CloudTrail events to trigger ECS tasks.
- Use CloudWatch alarms to scale ECS task count.
- Trigger a Lambda function that calls StartTask API.

### Correct Answer

Set up an Amazon EventBridge (Amazon CloudWatch Events) rule to detect S3 object PUT operations and set the target to the ECS cluster to run a new ECS task.

### Explanation

Amazon EventBridge enables event-driven architectures by routing events from AWS services. An EventBridge rule can detect S3 PUT events and directly trigger ECS tasks, providing the simplest implementation.

---

## Question 16

A tech company evaluated Amazon S3 for employee document storage. The solution must provide single sign-on from corporate AD/LDAP and restrict each user to their own folder.

Which options should be implemented? (Select TWO.)

### Options

- Set up IAM users for all employees.
- __Set up a Federation proxy or Identity Provider and use AWS Security Token Service (STS) to generate temporary tokens.__
- Use third-party SSO providers only.
- Map each user using Amazon WorkDocs.
- __Configure an IAM role and an IAM policy to access the bucket.__

### Correct Answer

Set up a Federation proxy or Identity Provider and use AWS Security Token Service (STS) to generate temporary tokens.

Configure an IAM role and an IAM policy to access the bucket.

### Explanation

Enterprise identity federation allows users to authenticate through existing directory services and obtain temporary AWS credentials via AWS STS. IAM roles and policies control access to S3 folders.

---

## Question 17

A company has 3 DevOps engineers. One engineer accidentally deleted a file hosted in Amazon S3 causing disruption of service.

What can be done to prevent this from happening again?

### Options

- __Enable S3 Versioning and Multi-Factor Authentication Delete on the bucket.__
- Create an IAM bucket policy that disables delete operations.
- Use signed URLs.
- Use S3 Infrequent Access storage.

### Correct Answer

Enable S3 Versioning and Multi-Factor Authentication Delete on the bucket.

### Explanation

Versioning preserves multiple versions of objects and allows recovery from accidental deletion. MFA Delete adds an extra authentication step before permanently deleting object versions.

---

## Question 18

There was an incident where user data stored in Amazon S3 was accidentally deleted by a DevOps engineer.

What combination protects S3 objects from accidental deletion and overwriting? (Select TWO.)

### Options

- __Enable Multi-Factor Authentication Delete__
- __Enable Versioning__
- Provide access through pre-signed URLs
- Enable S3 Intelligent-Tiering
- Disallow S3 Delete via bucket policy

### Correct Answer

Enable Versioning

Enable Multi-Factor Authentication Delete

### Explanation

Versioning maintains multiple object versions and enables recovery. MFA Delete adds additional security to permanently delete objects.

---

## Question 19

A company stores frequently accessed data in Amazon S3. When objects are created or deleted, notifications must be sent to development and operations teams.

Which solution satisfies this requirement?

### Options

- __Create an Amazon SNS topic and configure two SQS queues to subscribe to the topic. Grant S3 permission to send notifications to SNS and update the bucket to use the new SNS topic.__
- Configure queues to poll an SNS topic.
- Add a second SQS queue directly to S3 events.
- Create another SNS topic.

### Correct Answer

Create an Amazon SNS topic and configure two SQS queues to subscribe to the topic. Grant S3 permission to send notifications to SNS and update the bucket to use the new SNS topic.

### Explanation

Using SNS fanout allows a single event to be delivered to multiple SQS queues so different teams can process the same notification independently.

---

## Question 20

A pharmaceutical company has resources on-premises and in AWS. Architects must access resources using credentials stored in Active Directory.

Which option fulfills this requirement?

### Options

- Set up SAML federation using Web Identity Federation
- __Set up SAML 2.0-Based Federation using Microsoft Active Directory Federation Services__
- Use Amazon VPC
- Use IAM users

### Correct Answer

Set up SAML 2.0-Based Federation using Microsoft Active Directory Federation Services

### Explanation

AWS supports identity federation using SAML 2.0. Microsoft AD FS can act as the identity provider allowing users to authenticate with existing Active Directory credentials and access AWS resources without creating IAM users.

## Question 21

A company plans to launch an Amazon EC2 instance in a private subnet for its internal corporate web portal. For security purposes, the EC2 instance must send data to Amazon DynamoDB and Amazon S3 via private endpoints that don't pass through the public Internet.

Which of the following can meet the above requirements?

### Options

- Use AWS VPN CloudHub to route all access to S3 and DynamoDB via private endpoints.
- Enable DynamoDB Encryption at Rest with the default AWS-managed key and S3 Server-Side Encryption with the default AWS KMS key to route all traffic to DynamoDB and S3 via private endpoints.
- Use AWS Direct Connect to route all access to S3 and DynamoDB via private endpoints.
- __Use a DynamoDB VPC endpoint and an S3 VPC endpoint to route all access to these services via private endpoints.__

### Correct Answer

Use a DynamoDB VPC endpoint and an S3 VPC endpoint to route all access to these services via private endpoints.

### Explanation

A VPC endpoint allows you to privately connect your VPC to supported AWS and VPC endpoint services powered by AWS PrivateLink without needing an Internet gateway, NAT computer, VPN connection, or AWS Direct Connect connection. Instances in your VPC do not require public IP addresses to communicate with resources in the service. Traffic between your VPC and the other service does not leave the Amazon network.

In the scenario, you are asked to configure private endpoints to send data to Amazon DynamoDB and Amazon S3 without accessing the public Internet. Among the options given, VPC endpoint is the most suitable service that will allow you to use private IP addresses to access both DynamoDB and S3 without any exposure to the public internet.

---

## Question 22

A Solutions Architect identified a series of DDoS attacks while monitoring the Amazon VPC. The Architect needs to fortify the current cloud infrastructure to protect the data of the clients.

Which of the following is the most suitable solution to mitigate these kinds of attacks?

### Options

- Set up a web application firewall using AWS WAF to filter, monitor, and block HTTP traffic.
- __Use AWS Shield Advanced to detect and mitigate DDoS attacks.__
- A combination of Security Groups and Network Access Control Lists to only allow authorized traffic to access your VPC.
- Using the AWS Firewall Manager, set up a security layer that will prevent SYN floods, UDP reflection attacks, and other DDoS attacks.

### Correct Answer

Use AWS Shield Advanced to detect and mitigate DDoS attacks.

### Explanation

For higher levels of protection against attacks targeting your applications running on Amazon Elastic Compute Cloud (EC2), Elastic Load Balancing (ELB), Amazon CloudFront, and Amazon Route 53 resources, you can subscribe to AWS Shield Advanced. In addition to the network and transport layer protections that come with Standard, AWS Shield Advanced provides additional detection and mitigation against large and sophisticated DDoS attacks, near real-time visibility into attacks, and integration with AWS WAF.

---

## Question 23

A business has recently migrated its applications to AWS. The audit team must be able to assess whether the services the company is using meet common security and regulatory standards. A solutions architect needs to provide the team with a report of all compliance-related documents for their account.

Which action should a solutions architect consider?

### Options

- Run an Amazon Macie job to view the Service Organization Control (SOC), Payment Card Industry (PCI), and other compliance reports from AWS Certificate Manager (ACM).
- View all of the AWS security compliance reports from AWS Security Hub.
- Run an Amazon Inspector assessment job to download all of the AWS compliance-related information.
- __Use AWS Artifact to view the security reports as well as other AWS compliance-related information.__

### Correct Answer

Use AWS Artifact to view the security reports as well as other AWS compliance-related information.

### Explanation

AWS Artifact is your go-to, central resource for compliance-related information that matters to you. It provides on-demand access to AWS’ security and compliance reports and select online agreements. Reports available in AWS Artifact include Service Organization Control (SOC) reports, Payment Card Industry (PCI) reports, and certifications from accreditation bodies across geographies and compliance verticals that validate the implementation and operating effectiveness of AWS security controls.

---

## Question 24

A popular social media website uses a Amazon CloudFront web distribution to serve static content to millions of users around the globe. Recently, the website has received a number of complaints about long login times. Additionally, there are instances where users encounter HTTP 504 errors. The manager has instructed the team to significantly reduce login time and further optimize the system.

Which of the following options should be used together to set up a cost-effective solution that improves the application's performance? (Select TWO.)

### Options

- __Implement an origin failover by creating an origin group that includes two origins. Assign one as the primary origin and the other as secondary, which enables CloudFront to automatically switch to if the primary origin encounters specific HTTP status code failure responses.__
- Configure your origin to add a Cache-Control max-age directive to your objects, and specify the longest practical value for max-age to increase the cache hit ratio of your CloudFront distribution.
- __Customize the content that the CloudFront web distribution delivers to your users using Lambda@Edge, which allows your AWS Lambda functions to execute the authentication process in AWS locations closer to the users.__
- Deploy your application to multiple AWS regions to accommodate your users around the world. Set up a Route 53 record with latency routing policy to route incoming traffic to the region that provides the best latency to the user.
- Establish multiple Amazon VPCs in different AWS regions and configure a transit VPC to interconnect all of your resources.

### Correct Answer

Implement an origin failover by creating an origin group that includes two origins. Assign one as the primary origin and the other as secondary.

Customize the content that the CloudFront web distribution delivers to your users using Lambda@Edge.

### Explanation

Lambda@Edge lets you run Lambda functions to customize the content that CloudFront delivers, executing the functions in AWS locations closer to the viewer. You can also configure origin failover so CloudFront automatically switches to a secondary origin when the primary origin fails.

---

## Question 25

A financial services company plans to migrate its trading application from on-premises Microsoft Windows Server to AWS. The solution must ensure high availability across multiple Availability Zones and offer low-latency access to block storage.

Which of the following solutions will fulfill these requirements?

### Options

- Configure the trading application on Amazon EC2 Windows instances across two Availability Zones. Use Amazon S3 for storage.
- __Configure the trading application on Amazon EC2 Windows Server instances across two Availability Zones. Use Amazon FSx for NetApp ONTAP to create a Multi-AZ file system and access the data via iSCSI protocol.__
- Deploy the trading application on Amazon EC2 Windows Server instances across two Availability Zones using Amazon FSx for Windows File Server.
- Deploy the trading application on Amazon EC2 Windows Server instances across two Availability Zones using Amazon EFS.

### Correct Answer

Configure the trading application on Amazon EC2 Windows Server instances across two Availability Zones. Use Amazon FSx for NetApp ONTAP to create a Multi-AZ file system and access the data via iSCSI protocol.

### Explanation

Amazon FSx for NetApp ONTAP provides high-performance, scalable storage supporting both file and block protocols. It offers Multi-AZ deployments and sub‑millisecond latency, making it suitable for Windows workloads requiring block storage.

---

## Question 26

A company has a highly available architecture consisting of an Elastic Load Balancer and multiple Amazon EC2 instances configured with Auto Scaling across three Availability Zones. The company needs to monitor EC2 instances based on a specific metric that is not readily available in Amazon CloudWatch.

Which of the following is a custom metric in CloudWatch that requires manual setup?

### Options

- CPU Utilization of an EC2 instance
- Network packets out of an EC2 instance
- Disk Read activity of an EC2 instance
- __Memory Utilization of an EC2 instance__

### Correct Answer

Memory Utilization of an EC2 instance

### Explanation

CloudWatch provides default metrics such as CPU utilization, network utilization, and disk activity. However, memory utilization is not collected by default and must be configured using the CloudWatch agent or custom scripts.

---

## Question 27

A retail company receives raw .csv data files into its Amazon S3 bucket from multiple sources on an hourly basis, with an average file size of 2 GB.

An automated process must convert these .csv files into Apache Parquet format and store them in another S3 bucket. The process must automatically start whenever a new file is uploaded.

Which option should be implemented with the LEAST operational overhead?

### Options

- __Utilize an AWS Glue ETL job to process and convert the .csv files to Apache Parquet format and store the output files into the target S3 bucket. Configure an Amazon EventBridge rule to trigger the Glue job on S3 Object Created events.__
- Set up an Apache Spark job on an Amazon EC2 instance and trigger it using EventBridge.
- Use an AWS Lambda function triggered by S3 events to convert the files.
- Create a scheduled AWS Glue crawler that runs every hour.

### Correct Answer

Utilize an AWS Glue ETL job and configure EventBridge to trigger the job on S3 Object Created events.

### Explanation

AWS Glue is a serverless ETL service designed for large-scale data processing. EventBridge can trigger the job automatically whenever new objects are created in the S3 bucket, enabling an event-driven pipeline.

---

## Question 28

A telecommunications company plans to grant AWS Console access to developers. Company policy requires identity federation and role-based access control using an existing corporate Active Directory.

Which services can provide developers access to the AWS console? (Select TWO.)

### Options

- IAM Groups
- AWS Lambda
- __AWS Directory Service AD Connector__
- AWS Directory Service Simple AD
- __IAM Roles__

### Correct Answer

AWS Directory Service AD Connector

IAM Roles

### Explanation

AWS Directory Service AD Connector allows AWS to use an existing on‑premises Active Directory for authentication. IAM roles can then be assigned to AD users or groups to provide controlled access to AWS resources.

---

## Question 29

A company uses API Gateway and AWS Lambda for its web services. The company expects massive global traffic due to a product announcement.

How can the backend systems be protected from traffic spikes?

### Options

- API Gateway will automatically scale without configuration.
- Deploy Multi-AZ in API Gateway with read replicas.
- Manually upgrade the EC2 instances used by API Gateway.
- __Use throttling limits in API Gateway.__

### Correct Answer

Use throttling limits in API Gateway.

### Explanation

Amazon API Gateway supports request throttling with configurable rate and burst limits. Requests exceeding the configured limit return HTTP 429 responses, helping protect backend services from traffic spikes.

---

## Question 30

A Solutions Architect is designing a highly available relational database solution to mitigate multi‑region failures. The database must meet an RPO of 1 second and an RTO of less than 1 minute.

Which AWS feature fulfills this requirement?

### Options

- Amazon RDS for PostgreSQL with cross-region read replicas
- __Amazon Aurora Global Database__
- Amazon DynamoDB Global table
- Amazon Timestream for Analytics

### Correct Answer

Amazon Aurora Global Database

### Explanation

Amazon Aurora Global Database provides cross‑region replication with latency typically under 1 second. In case of a region failure, a secondary region can be promoted to primary within less than one minute, meeting strict RPO and RTO requirements.

## Question 31

An online cryptocurrency exchange platform is hosted in AWS, utilizing an Amazon ECS Cluster and Amazon RDS in a Multi-AZ Deployments configuration. The application heavily uses the RDS instance to process complex read and write database operations. To maintain reliability, availability, and performance, it is necessary to closely monitor how the different processes or threads on a DB instance use the CPU, including the percentage of CPU bandwidth and total memory consumed by each process.

Which of the following is the most suitable solution to monitor the database properly?

### Options

- Use Amazon CloudWatch to monitor the CPU Utilization of your database.
- Create a script that collects and publishes custom metrics to Amazon CloudWatch, which tracks the real-time CPU Utilization of the RDS instance, and then set up a custom CloudWatch dashboard to view the metrics.
- Check the CPU% and MEM% metrics which are readily available in the RDS console that shows the percentage of the CPU bandwidth and total memory consumed by each database process of your RDS instance.
- __Enable Enhanced Monitoring in RDS.__

### Correct Answer

Enable Enhanced Monitoring in RDS.

### Explanation

Amazon RDS offers a powerful feature known as Enhanced Monitoring, which provides detailed metrics in real-time about the operating system (OS) underlying your database instances. This feature allows users to monitor performance at a granular level through the AWS Management Console or by accessing the Enhanced Monitoring JSON output via CloudWatch Logs.

Enhanced Monitoring differs from standard CloudWatch metrics in that it gathers data directly from an agent installed on the instance rather than from the hypervisor. This provides detailed insight into how individual processes or threads utilize CPU and memory resources.

---

## Question 32

An e-commerce company utilizes a regional Amazon API Gateway to host its public REST APIs. The API Gateway endpoint is accessed through a custom domain name set up with an Amazon Route 53 alias record. To support continuous improvement, the company intends to launch a new version of its APIs with enhanced features and performance optimizations.

How can the company reduce customer disruption and ensure MINIMAL data loss during the update process in the MOST cost-effective way?

### Options

- Implement a blue-green deployment strategy for the API Gateway, deploying the latest version of the APIs to the green environment. Route some user traffic to it, validate the new APIs, and once thoroughly validated, promote the green environment to production.
- __Implement a canary release deployment strategy for the API Gateway. Deploy the latest version of the APIs to a canary stage and direct a portion of the user traffic to this stage. Verify the new APIs. Gradually increase the traffic percentage, monitor for any issues, and promote the canary stage to production.__
- Modify the existing API Gateway with the updated version of the APIs using the import-to-update operation.
- Create a new API Gateway with the updated version of the APIs while keeping the same custom domain name.

### Correct Answer

Implement a canary release deployment strategy for the API Gateway.

### Explanation

A canary deployment releases a new API version to a small percentage of users. If the update performs correctly, traffic can gradually increase to the new version. This reduces risk, minimizes disruption, and avoids downtime during upgrades.

---

## Question 33

An organization requires a persistent block storage volume to support its mission-critical workloads. The backup data will be stored in an object storage service and, after 30 days, transitioned to an archival storage service for long-term retention. The team has already configured an Amazon EBS snapshot retention rule for point-in-time recovery.

What should be done to meet the above requirement?

### Options

- __Attach an EBS volume to your Amazon EC2 instance. Use Amazon S3 to store your backup data and configure a lifecycle policy to transition your objects to S3 Glacier Flexible Retrieval.__
- Attach an EBS volume to your Amazon EC2 instance. Use Amazon S3 and transition objects to S3 One Zone‑IA.
- Attach an instance store volume and use Amazon S3 with lifecycle policies to Glacier.
- Attach an instance store volume and transition objects to S3 One Zone‑IA.

### Correct Answer

Attach an EBS volume to your Amazon EC2 instance. Use Amazon S3 to store your backup data and configure a lifecycle policy to transition your objects to S3 Glacier Flexible Retrieval.

### Explanation

Amazon EBS provides persistent block storage for EC2 instances. Backup data can be stored in Amazon S3, which supports lifecycle policies that automatically transition data to archival storage such as S3 Glacier Flexible Retrieval for long-term retention.

---

## Question 34

A company uses an Application Load Balancer (ALB) for its public-facing multi-tier web applications. The security team has reported a surge of SQL injection attacks affecting multiple web applications across different AWS accounts.

What solution should be implemented to prevent these attacks and centrally manage protections?

### Options

- Use Amazon GuardDuty and Security Hub.
- Use Amazon Macie and AWS Audit Manager.
- __Use AWS WAF with a managed SQL injection rule set and integrate it with AWS Firewall Manager.__
- Use AWS Network Firewall with rule groups.

### Correct Answer

Use AWS WAF with a managed SQL injection rule set and integrate it with AWS Firewall Manager.

### Explanation

AWS WAF protects web applications from common web exploits such as SQL injection. Managed rule groups can detect and block malicious requests. AWS Firewall Manager allows centralized rule management across multiple AWS accounts.

---

## Question 35

A newly hired Solutions Architect analyzes the following IAM policy applied to an S3 bucket.

```
{
 "Version": "2012-10-17",
 "Statement": [
  {
   "Effect": "Allow",
   "Action": [
    "s3:Get*",
    "s3:List*"
   ],
   "Resource": "*"
  },
  {
   "Effect": "Allow",
   "Action": "s3:PutObject",
   "Resource": "arn:aws:s3:::boracay/*"
  }
 ]
}
```

What does this IAM policy allow? (Select THREE.)

### Options

- __An IAM user with this IAM policy is allowed to write objects into the boracay S3 bucket.__
- An IAM user with this IAM policy is allowed to read and delete objects from the boracay S3 bucket.
- __An IAM user with this IAM policy is allowed to read objects from all S3 buckets owned by the account.__
- An IAM user with this IAM policy is allowed to change access rights for the boracay S3 bucket.
- __An IAM user with this IAM policy is allowed to read objects from the boracay S3 bucket.__
- An IAM user with this IAM policy is allowed to read objects in the boracay bucket but not list them.

### Correct Answer

- An IAM user with this IAM policy is allowed to write objects into the boracay S3 bucket.  
- An IAM user with this IAM policy is allowed to read objects from all S3 buckets owned by the account.  
- An IAM user with this IAM policy is allowed to read objects from the boracay S3 bucket.

### Explanation

The policy allows:

- `s3:Get*` and `s3:List*` on all S3 resources.
- `s3:PutObject` specifically to the `boracay` bucket.

This enables reading from all buckets and writing to the boracay bucket.

---

## Question 36

A Solutions Architect must ensure that an EC2 instance can only be accessed via SSH from the IP address **110.238.98.71**.

Which configuration will satisfy this requirement?

### Options

- Security Group Outbound Rule: UDP 22 to 0.0.0.0/0
- __Security Group Inbound Rule: TCP 22 from 110.238.98.71/32__
- Security Group Outbound Rule: TCP 22 to 110.238.98.71/32
- Security Group Inbound Rule: UDP 22 from 110.238.98.71/32

### Correct Answer

Security Group Inbound Rule: TCP 22 from 110.238.98.71/32

### Explanation

SSH uses TCP on port 22. Security groups are stateful, so allowing inbound SSH traffic from a specific IP automatically allows return traffic.

---

## Question 37

A healthcare organization collects real-time data containing Personally Identifiable Information (PII). The PII must be anonymized before it is stored in a NoSQL database.

Which solution meets the requirement?

### Options

- Stream the data into DynamoDB and anonymize using DynamoDB Streams.
- __Ingest real-time data using Amazon Kinesis Data Streams and process it with AWS Lambda to anonymize the PII before storing it in Amazon DynamoDB.__
- Store data in Amazon S3 and anonymize using Lambda triggers.
- Use Amazon Kinesis Data Firehose and deliver anonymized data to Amazon Redshift.

### Correct Answer

Ingest real-time data using Amazon Kinesis Data Streams and process it with AWS Lambda to anonymize the PII before storing it in Amazon DynamoDB.

### Explanation

Kinesis Data Streams captures streaming data in real time. AWS Lambda can process the stream and anonymize PII before storing the processed data in DynamoDB.

---

## Question 38

An e-commerce company uses an Amazon Aurora database. As traffic increases, the read replica struggles to keep up with read requests during peak periods.

Which solution resolves the issue most cost‑effectively?

### Options

- Implement read scaling with Aurora Global Database.
- Set up a cross‑region read replica.
- __Use automatic scaling for the Aurora read replicas using Aurora Auto Scaling.__
- Increase the size of the Aurora DB cluster.

### Correct Answer

Use automatic scaling for the Aurora read replicas using Aurora Auto Scaling.

### Explanation

Aurora Auto Scaling automatically adds or removes read replicas based on demand, ensuring optimal performance during peak traffic while minimizing cost during lower usage periods.

---

## Question 39

An application records weather data every minute and uses a MySQL RDS database instance. Currently the database runs in a single Availability Zone.

Which feature enables synchronous replication to another instance for high availability?

### Options

- Amazon DynamoDB Read Replica
- __RDS DB instance running as a Multi-AZ deployment__
- RDS Read Replica
- Amazon CloudFront Multi‑AZ deployment

### Correct Answer

RDS DB instance running as a Multi-AZ deployment.

### Explanation

Multi‑AZ deployments create a synchronous standby replica in another Availability Zone. In the event of failure, RDS automatically performs failover to the standby instance.

---

## Question 40

A company with a hybrid architecture requires durable backups for on‑premises documents. Files must be accessible via SMB, cached locally for low latency, and archived for long‑term retention.

Which solution is the most cost‑effective?

### Options

- Establish Direct Connect and store documents on EBS volumes.
- Use AWS DataSync to transfer files directly to Amazon S3.
- __Launch a file gateway using AWS Storage Gateway and store the files in Amazon S3 with lifecycle policies to move them to Glacier.__
- Launch a tape gateway using AWS Storage Gateway.

### Correct Answer

Launch a file gateway using AWS Storage Gateway and store the files in Amazon S3 with lifecycle policies to move them to Glacier.

### Explanation

AWS Storage Gateway File Gateway provides SMB and NFS access to Amazon S3 with local caching for low‑latency access. S3 lifecycle policies can automatically archive data to Glacier for long‑term storage.

## Question 41

A company has recently migrated its microservices-based application to Amazon Elastic Kubernetes Service (Amazon EKS). As part of the migration, the company must ensure that all sensitive configuration data and credentials, such as database passwords and API keys, are stored securely and encrypted within the Amazon EKS cluster's etcd key-value store.

What is the most suitable solution to meet the company's requirements?

### Options

- Use AWS Secrets Manager with a new AWS KMS key to securely manage and store sensitive data within the EKS cluster's etcd key-value store.
- Enable default Amazon EBS volume encryption for the account with a new AWS KMS key to ensure encryption of sensitive data within the Amazon EKS cluster.
- Use Amazon EKS default options and the Amazon Elastic Block Store (Amazon EBS) Container Storage Interface (CSI) driver as an add-on to securely store sensitive data within the Amazon EKS cluster.
- __Enable secret encryption with a new AWS KMS key on an existing Amazon EKS cluster to encrypt sensitive data stored in the EKS cluster's etcd key-value store.__

### Correct Answer

Enable secret encryption with a new AWS KMS key on an existing Amazon EKS cluster to encrypt sensitive data stored in the EKS cluster's etcd key-value store.

### Explanation

Enabling secret encryption with AWS KMS ensures that sensitive Kubernetes secrets stored in the EKS etcd datastore are encrypted at rest. This integrates AWS KMS with EKS so secrets are encrypted before being persisted in etcd.

---

## Question 42

A startup is using Amazon RDS to store data from a web application. Most of the time, the application has low user activity but it receives bursts of traffic within seconds whenever there is a new product announcement. The Solutions Architect needs to create a solution that will allow users around the globe to access the data using an API.

What should the Solutions Architect do to meet the above requirement?

### Options

- Create an API using Amazon API Gateway and use the Amazon ECS cluster with Service Auto Scaling to handle bursts of traffic.
- __Create an API using Amazon API Gateway and use AWS Lambda to handle bursts of traffic.__
- Create an API using Amazon API Gateway and use Amazon Elastic Beanstalk with Auto Scaling.
- Create an API using Amazon API Gateway and use an Auto Scaling group of EC2 instances.

### Correct Answer

Create an API using Amazon API Gateway and use AWS Lambda to handle bursts of traffic.

### Explanation

AWS Lambda scales automatically and can handle sudden bursts of traffic within seconds. Combined with API Gateway, it provides a fully serverless solution that handles unpredictable workloads efficiently.

---

## Question 43

A company hosted an e-commerce website on an Auto Scaling group of Amazon EC2 instances behind an Application Load Balancer. The website receives a high number of illegitimate external requests from multiple systems with frequently changing IP addresses.

Which option fulfills the requirement to block malicious requests while minimizing impact on legitimate traffic?

### Options

- Create a regular rule in AWS WAF and associate the web ACL with the ALB.
- Create a custom rule in the security group of the ALB.
- __Create a rate-based rule in AWS WAF and associate the web ACL with the ALB.__
- Create a custom network ACL and associate it with the ALB subnet.

### Correct Answer

Create a rate-based rule in AWS WAF and associate the web ACL with the ALB.

### Explanation

AWS WAF rate‑based rules track request rates per IP address and automatically block IPs that exceed defined request limits. This helps mitigate request flooding attacks while allowing legitimate traffic.

---

## Question 44

A development team uses AWS Lambda functions that store sensitive database credentials and API keys as environment variables.

How can this sensitive information be secured so other developers cannot view them in plaintext?

### Options

- __Create a new AWS KMS key and enable encryption helpers to encrypt the sensitive information.__
- Lambda does not provide encryption for environment variables.
- Lambda already encrypts environment variables by default so nothing needs to be done.
- Enable SSL encryption using AWS CloudHSM.

### Correct Answer

Create a new AWS KMS key and enable encryption helpers to encrypt the sensitive information.

### Explanation

Lambda environment variables are encrypted using AWS KMS. Using a customer‑managed KMS key with encryption helpers allows tighter access control, auditing, and improved security of sensitive environment variables.

---

## Question 45

A logistics company needs to upload confidential documents using SFTP. Files must be encrypted at rest, highly available, and automatically deleted after one month.

Which solution meets the requirements with the least operational overhead?

### Options

- Create an S3 bucket and configure AWS Transfer for SFTP. Delete files using SFTP retention policies.
- __Create an S3 bucket with encryption enabled. Launch AWS Transfer for SFTP and configure an S3 lifecycle rule to delete files after one month.__
- Use Amazon EFS with AWS Transfer for SFTP and lifecycle policies.
- Launch an EC2 instance with SFTP and delete files using cron jobs.

### Correct Answer

Create an S3 bucket with encryption enabled. Launch AWS Transfer for SFTP and configure an S3 lifecycle rule to delete files after one month.

### Explanation

AWS Transfer Family provides managed SFTP endpoints that store uploaded files directly in Amazon S3. S3 lifecycle policies automatically delete files after the configured retention period.

---

## Question 46

A company hosts a web application that allows users to upload files. Files older than two years must be moved to a different storage class.

Which solutions can fulfill this requirement? (Select TWO.)

### Options

- __Use Amazon S3 and create a lifecycle policy to move objects to S3 Glacier after two years.__
- Use RAID 0 with Amazon EBS volumes and schedule snapshots.
- __Use Amazon S3 and create a lifecycle policy to move objects to S3 Standard‑IA after two years.__
- Use Amazon EFS lifecycle policies to move files after two years.
- Use Amazon EBS volumes with Data Lifecycle Manager snapshots.

### Correct Answer

- Use Amazon S3 and create a lifecycle policy to move objects to S3 Glacier after two years.  
- Use Amazon S3 and create a lifecycle policy to move objects to S3 Standard‑IA after two years.

### Explanation

Amazon S3 lifecycle rules allow automatic transitions of objects to lower‑cost storage tiers such as Standard‑IA or Glacier for long‑term storage while maintaining durability.

---

## Question 47

A web application runs in an Auto Scaling group across multiple Availability Zones. A scale‑in policy is triggered due to reduced traffic.

Which EC2 instance will be terminated first using the default termination policy?

### Options

- The instance will be randomly selected.
- The EC2 instance running the longest.
- The EC2 instance with the least user sessions.
- __The EC2 instance launched from the oldest launch template.__

### Correct Answer

The EC2 instance launched from the oldest launch template.

### Explanation

The default Auto Scaling termination policy selects instances from the Availability Zone with the most instances and prioritizes terminating instances launched using the oldest launch configuration or launch template.

---

## Question 48

A company needs to query data from multiple AWS accounts into a central data lake. Each account stores data in its own Amazon S3 bucket.

Which solution minimizes overhead and cost?

### Options

- __Use AWS Lake Formation to consolidate data from multiple accounts.__
- Use AWS Control Tower to centrally manage S3 buckets.
- Use Lambda and EventBridge to transfer data between accounts.
- Use Amazon Data Firehose to consolidate data.

### Correct Answer

Use AWS Lake Formation to consolidate data from multiple accounts.

### Explanation

AWS Lake Formation simplifies building centralized data lakes. It integrates with S3 and AWS Glue and provides centralized governance and access control across multiple AWS accounts.

---

## Question 49

A banking portal uses Amazon ElastiCache for Redis for distributed session management. Engineers must authenticate before executing Redis commands.

Which action meets the requirement?

### Options

- __Authenticate users using Redis AUTH by enabling --transit-encryption-enabled and --auth-token.__
- Generate IAM authentication tokens for Redis access.
- Enable Redis at‑rest encryption.
- Enable Redis in‑transit encryption.

### Correct Answer

Authenticate users using Redis AUTH by enabling --transit-encryption-enabled and --auth-token.

### Explanation

Redis AUTH enforces password authentication for Redis commands. When combined with in‑transit encryption and auth tokens, it ensures secure access to the Redis cluster.

---

## Question 50

A company migrates an application to AWS and requires outbound IPv6 internet access while preventing inbound connections. Traffic inspection and filtering are also required.

Which architecture meets the requirements?

### Options

- __Launch EC2 in a private subnet, attach an Egress‑Only Internet Gateway, and use AWS Network Firewall for inspection and filtering.__
- Launch EC2 in a private subnet with AWS PrivateLink and GuardDuty.
- Launch EC2 in a private subnet with a NAT Gateway and Firewall Manager.
- Launch EC2 in a public subnet with an Internet Gateway and Traffic Mirroring.

### Correct Answer

Launch EC2 in a private subnet, attach an Egress‑Only Internet Gateway, and use AWS Network Firewall.

### Explanation

An Egress‑Only Internet Gateway allows outbound IPv6 internet traffic while blocking inbound connections. AWS Network Firewall provides traffic inspection and filtering for enhanced security.

## Question 51

A popular social network is hosted in AWS and is using a Amazon DynamoDB table as its database. There is a requirement to implement a 'follow' feature where users can subscribe to certain updates made by a particular user and be notified via email.

Which of the following is the most suitable solution to implement to meet the requirement?

### Options

- Create an AWS Lambda function that uses DynamoDB Streams Amazon Kinesis Adapter which will fetch data from the DynamoDB Streams endpoint. Set up an Amazon SNS Topic that will notify the subscribers via email when there is an update made by a particular user.
- __Enable DynamoDB Stream and create an AWS Lambda trigger, as well as the IAM role which contains all of the permissions that the Lambda function will need at runtime. The data from the stream record will be processed by the Lambda function which will then publish a message to Amazon SNS Topic that will notify the subscribers via email.__
- Set up a DAX cluster to access the source DynamoDB table. Create a new DynamoDB trigger and an AWS Lambda function. For every update made in the user data, the trigger will send data to the Lambda function which will then notify the subscribers via email using Amazon SNS.
- Using the Amazon Kinesis Client Library (KCL), write an application that leverages on DynamoDB Streams Kinesis Adapter that will fetch data from the DynamoDB Streams endpoint. When there are updates made by a particular user, notify the subscribers via email using Amazon SNS.

### Correct Answer

Enable DynamoDB Stream and create an AWS Lambda trigger, as well as the IAM role which contains all of the permissions that the Lambda function will need at runtime. The data from the stream record will be processed by the Lambda function which will then publish a message to Amazon SNS Topic that will notify the subscribers via email.

### Explanation

A DynamoDB stream is an ordered flow of information about changes to items in an Amazon DynamoDB table. When you enable a stream on a table, DynamoDB captures information about every modification to data items in the table.

Whenever an application creates, updates, or deletes items in the table, DynamoDB Streams writes a stream record with the primary key attribute(s) of the items that were modified. A stream record contains information about a data modification to a single item in a DynamoDB table. You can configure the stream so that the stream records capture additional information, such as the "before" and "after" images of modified items.

Amazon DynamoDB is integrated with AWS Lambda so that you can create triggers—pieces of code that automatically respond to events in DynamoDB Streams. With triggers, you can build applications that react to data modifications in DynamoDB tables.

If you enable DynamoDB Streams on a table, you can associate the stream ARN with a Lambda function that you write. Immediately after an item in the table is modified, a new record appears in the table's stream. AWS Lambda polls the stream and invokes your Lambda function synchronously when it detects new stream records. The Lambda function can perform any actions you specify, such as sending a notification or initiating a workflow.

Streams and Triggers

Hence, the correct answer is: Enable DynamoDB Stream and create an AWS Lambda trigger, as well as the IAM role which contains all of the permissions that the Lambda function will need at runtime. The data from the stream record will be processed by the Lambda function which will then publish a message to Amazon SNS Topic that will notify the subscribers via email.

The option that says: Using the Amazon Kinesis Client Library (KCL), write an application that leverages on DynamoDB Streams Kinesis Adapter that will fetch data from the DynamoDB Streams endpoint. When there are updates made by a particular user, notify the subscribers via email using Amazon SNS is incorrect. Although this is a valid solution, it is missing a vital step which is to enable DynamoDB Streams. With the DynamoDB Streams Kinesis Adapter in place, you can begin developing applications via the KCL interface, with the API calls seamlessly directed at the DynamoDB Streams endpoint. Remember that the DynamoDB Stream feature is not enabled by default.

The option that says: Create an AWS Lambda function that uses DynamoDB Streams Amazon Kinesis Adapter which will fetch data from the DynamoDB Streams endpoint. Set up an Amazon SNS Topic that will notify the subscribers via email when there is an update made by a particular user is incorrect because just like in the above, you have to manually enable DynamoDB Streams first before you can use its endpoint.

The option that says: Set up a DAX cluster to access the source DynamoDB table. Create a new DynamoDB trigger and an AWS Lambda function. For every update made in the user data, the trigger will send data to the Lambda function which will then notify the subscribers via email using Amazon SNS is incorrect because the DynamoDB Accelerator (DAX) feature is primarily used to significantly improve the in-memory read performance of your database, and not to capture the time-ordered sequence of item-level modifications. You should use DynamoDB Streams in this scenario instead.

---

## Question 52

An online medical system hosted in AWS stores sensitive Personally Identifiable Information (PII) of the users in an Amazon S3 bucket. Both the master keys and the unencrypted data should never be sent to AWS to comply with the strict compliance and regulatory requirements of the company.

Which S3 encryption technique should the Architect use?

### Options

- Use S3 server-side encryption with customer provided key.
- Use S3 server-side encryption with an AWS KMS key.
- __Use S3 client-side encryption with a client-side master key.__
- Use S3 client-side encryption with an AWS KMS key.

### Correct Answer

Use S3 client-side encryption with a client-side master key.

### Explanation

Client-side encryption is the act of encrypting data before sending it to Amazon S3. To enable client-side encryption, you have the following options:

- Use an AWS KMS key.

- Use a client-side master key.

When using an AWS KMS key to enable client-side data encryption, you provide an AWS KMS key identifier (KeyId) to AWS. On the other hand, when you use client-side master key for client-side data encryption, your client-side master keys and your unencrypted data are never sent to AWS. It's important that you safely manage your encryption keys because if you lose them, you can't decrypt your data.

This is how client-side encryption using a client-side master key works:

When uploading an object - You provide a client-side master key to the Amazon S3 encryption client. The client uses the master key only to encrypt the data encryption key that it generates randomly. The process works like this:

1. The Amazon S3 encryption client generates a one-time-use symmetric key (also known as a data encryption key or data key) locally. It uses the data key to encrypt the data of a single Amazon S3 object. The client generates a separate data key for each object.

2. The client encrypts the data encryption key using the master key that you provide. The client uploads the encrypted data key and its material description as part of the object metadata. The client uses the material description to determine which client-side master key to use for decryption.

3. The client uploads the encrypted data to Amazon S3 and saves the encrypted data key as object metadata (x-amz-meta-x-amz-key) in Amazon S3.

When downloading an object - The client downloads the encrypted object from Amazon S3. Using the material description from the object's metadata, the client determines which master key to use to decrypt the data key. The client uses that master key to decrypt the data key and then uses the data key to decrypt the object.

Hence, the correct answer is: Use S3 client-side encryption with a client-side master key.

The option that says: Use S3 client-side encryption with an AWS KMS key is incorrect because, in client-side encryption with a KMS key, you provide an AWS KMS key identifier (KeyId) to AWS. The scenario clearly indicates that both the master keys and the unencrypted data should never be sent to AWS.

The option that says: Use S3 server-side encryption with an AWS KMS key is incorrect because the scenario mentioned that the unencrypted data should never be sent to AWS, which means that you have to use client-side encryption in order to encrypt the data first before sending to AWS. In this way, you can only ensure that there is no unencrypted data being uploaded to AWS. In addition, the master key used by Server-Side Encryption with AWS KMS Key (SSE-KMS) is uploaded and managed by AWS, which directly violates the requirement of not uploading the master key.

The option that says: Use S3 server-side encryption with customer provided key is incorrect because, just as mentioned above, you have to use client-side encryption in this scenario instead of server-side encryption. For the S3 server-side encryption with a customer-provided key (SSE-C), you actually provide the encryption key as part of your request to upload the object to S3. Using this key, Amazon S3 manages both the encryption (as it writes to disks) and decryption (when you access your objects).

---

## Question 53

A company plans to migrate its on-premises workload to AWS. The current architecture is composed of a Microsoft SharePoint server that uses a Windows shared file storage. The Solutions Architect needs to use a cloud storage solution that is highly available and can be integrated with Active Directory for access control and authentication.

Which of the following options can satisfy the given requirement?

### Options

- __Create a file system using Amazon FSx for Windows File Server and join it to an Active Directory domain in AWS.__
- Launch an Amazon EC2 Windows Server to mount a new Amazon S3 bucket as a file volume.
- Create a Network File System (NFS) file share using AWS Storage Gateway.
- Create a file system using Amazon EFS and join it to an Active Directory domain.

### Correct Answer

Create a file system using Amazon FSx for Windows File Server and join it to an Active Directory domain in AWS.

### Explanation

Amazon FSx for Windows File Server provides fully managed, highly reliable, and scalable file storage that is accessible over the industry-standard Service Message Block (SMB) protocol. It is built on Windows Server, delivering a wide range of administrative features such as user quotas, end-user file restore, and Microsoft Active Directory (AD) integration. Amazon FSx is accessible from Windows, Linux, and MacOS compute instances and devices. Thousands of compute instances and devices can access a file system concurrently.

Amazon FSx works with Microsoft Active Directory to integrate with your existing Microsoft Windows environments. You have two options to provide user authentication and access control for your file system: AWS Managed Microsoft Active Directory and Self-managed Microsoft Active Directory.

Take note that after you create an Active Directory configuration for a file system, you can't change that configuration. However, you can create a new file system from a backup and change the Active Directory integration configuration for that file system. These configurations allow the users in your domain to use their existing identity to access the Amazon FSx file system and to control access to individual files and folders.

Hence, the correct answer is: Create a file system using Amazon FSx for Windows File Server and join it to an Active Directory domain in AWS.

The option that says: Create a file system using Amazon EFS and join it to an Active Directory domain is incorrect because Amazon EFS does not support Windows systems, only Linux OS. You should use Amazon FSx for Windows File Server instead to satisfy the requirement in the scenario.

The option that says: Launch an Amazon EC2 Windows Server to mount a new Amazon S3 bucket as a file volume is incorrect because you can't integrate Amazon S3 with your existing Active Directory to provide authentication and access control.

The option that says: Create a Network File System (NFS) file share using AWS Storage Gateway is incorrect because NFS file share is primarily used for Linux systems. Remember that the requirement in the scenario is to use a Windows shared file storage. Therefore, you must use an SMB file share instead, which supports Windows OS and Active Directory configuration. Alternatively, you can also use the Amazon FSx for Windows File Server file system.

---

## Question 54

A car dealership website hosted in Amazon EC2 stores car listings in an Amazon Aurora database managed by Amazon RDS. Once a vehicle has been sold, its data must be removed from the current listings and forwarded to a distributed processing system.

Which of the following options can satisfy the given requirement?

### Options

- Create an RDS event subscription and send the notifications to AWS Lambda. Configure the Lambda function to fan out the event notifications to multiple Amazon SQS queues to update the processing system.
- __Use an Aurora MySQL native function to invoke an AWS Lambda function whenever a vehicle listing is deleted. Configure the Lambda function to send the data to an Amazon SQS queue for the distributed processing system to consume.__
- Create an RDS event subscription and send the notifications to Amazon SQS. Configure the SQS queues to fan out the event notifications to multiple Amazon SNS topics. Process the data using AWS Lambda functions.
- Create an RDS event subscription and send the notifications to Amazon SNS. Configure the SNS topic to fan out the event notifications to multiple Amazon SQS queues. Process the data using AWS Lambda functions.

### Correct Answer

Use an Aurora MySQL native function to invoke an AWS Lambda function whenever a vehicle listing is deleted. Configure the Lambda function to send the data to an Amazon SQS queue for the distributed processing system to consume.

### Explanation

You can invoke an AWS Lambda function from an Amazon Aurora MySQL-Compatible Edition DB cluster using a native function (lambda_sync or lambda_async). This approach can be useful when you want to integrate your database running on Aurora MySQL with other AWS services. For example, you might want to capture data changes whenever a row in a table is modified in your database.

Aurora Native Function

In the scenario, you can trigger a Lambda function using a native function whenever a listing is deleted from the database. You can then write the logic of the function to send the listing data to an SQS queue and have different processes consume it.

Hence, the correct answer is: Use an Aurora MySQL native function to invoke an AWS Lambda function whenever a vehicle listing is deleted. Configure the Lambda function to send the data to an Amazon SQS queue for the distributed processing system to consume.

The option that says: Create an RDS event subscription and send the notifications to Amazon SQS. Configure the SQS queues to fan out the event notifications to multiple Amazon SNS topics. Process the data using AWS Lambda functions is incorrect because RDS event subscriptions typically notify about operational changes rather than data modifications. This method does not capture database modifications like INSERT, DELETE, or UPDATE.

The option that says: Create an RDS event subscription and send the notifications to AWS Lambda. Configure the Lambda function to fan out the event notifications to multiple Amazon SQS queues to update the processing system is incorrect because RDS event subscriptions primarily focus on operational-level changes rather than capturing direct data modifications.

The option that says: Create an RDS event subscription and send the notifications to Amazon SNS. Configure the SNS topic to fan out the event notifications to multiple Amazon SQS queues. Process the data using AWS Lambda functions is incorrect because RDS event subscriptions only track infrastructure-related events and not actual database changes.

---

## Question 55

A travel photo-sharing website is using Amazon S3 to serve high-quality photos to visitors. After a few days, it was discovered that other travel websites are linking to and using these photos. This has resulted in financial losses for the business.

What is the MOST effective method to mitigate this issue?

### Options

- Block the IP addresses of the offending websites using NACL.
- Use Amazon CloudFront distributions for your photos.
- Store and privately serve the high-quality photos on Amazon WorkDocs instead.
- __Configure your S3 bucket to remove public read access and use pre-signed URLs with expiry dates.__

### Correct Answer

Configure your S3 bucket to remove public read access and use pre-signed URLs with expiry dates.

### Explanation

In Amazon S3, all objects are private by default. Only the object owner has permission to access these objects. However, the object owner can optionally share objects with others by creating a pre-signed URL, using their own security credentials, to grant time-limited permission to download the objects.

When you create a pre-signed URL for your object, you must provide your security credentials, specify a bucket name, an object key, specify the HTTP method (GET to download the object), and the expiration date and time. The pre-signed URLs are valid only for the specified duration.

Anyone who receives the pre-signed URL can then access the object. For example, if you have a video in your bucket and both the bucket and the object are private, you can share the video with others by generating a pre-signed URL.

Hence, the correct answer is: Configure your S3 bucket to remove public read access and use pre-signed URLs with expiry dates.

The option that says: Using Amazon CloudFront distributions for your photos is incorrect. CloudFront is primarily a content delivery network service that speeds up the delivery of content to your customers.

The option that says: Blocking the IP addresses of the offending websites using NACL is also incorrect. Blocking IP addresses using NACLs is not a very efficient method because a quick change in IP address would easily bypass this configuration.

The option that says: Storing and privately serving the high-quality photos on Amazon WorkDocs instead is incorrect as WorkDocs is simply a fully managed, secure content creation, storage, and collaboration service. It is not a suitable service for storing static content. Amazon WorkDocs is more often used to easily create, edit, and share documents for collaboration and not for serving object data like Amazon S3.

---

## Question 56

A company has a web application that uses Amazon CloudFront to distribute its images, videos, and other static content stored in its Amazon S3 bucket to users around the world. The company has recently introduced a new member-only access feature for some of its high-quality media files. There is a requirement to provide access to multiple private media files only to paying subscribers without having to change the current URLs.

Which of the following is the most suitable solution to implement to satisfy this requirement?

### Options

- Create a Signed URL with a custom policy which only allows the members to see the private files.
- __Use Signed Cookies to control who can access the private files in your CloudFront distribution by modifying your application to determine whether a user should have access to your content. For members, send the required Set-Cookie headers to the viewer which will unlock the content only to them.__
- Configure your CloudFront distribution to use Match Viewer as its Origin Protocol Policy which will automatically match the user request. This will allow access to the private content if the request is a paying member and deny it if it is not a member.
- Configure your CloudFront distribution to use Field-Level Encryption to protect your private data and only allow access to members.

### Correct Answer

Use Signed Cookies to control who can access the private files in your CloudFront distribution by modifying your application to determine whether a user should have access to your content. For members, send the required Set-Cookie headers to the viewer which will unlock the content only to them.

### Explanation

Many companies that distribute content over the internet want to restrict access to documents, business data, media streams, or content that is intended for selected users, for example, users who have paid a fee. To securely serve this private content by using CloudFront, you can do the following:

- Require that your users access your private content by using special CloudFront signed URLs or signed cookies.

- Require that your users access your content by using CloudFront URLs, not URLs that access content directly on the origin server (for example, Amazon S3 or a private HTTP server). Requiring CloudFront URLs isn't necessary, but we recommend it to prevent users from bypassing the restrictions that you specify in signed URLs or signed cookies.

CloudFront signed URLs and signed cookies provide the same basic functionality: they allow you to control who can access your content.

If you want to serve private content through CloudFront and you're trying to decide whether to use signed URLs or signed cookies, consider the following:

Use signed URLs for the following cases:

- You want to use an RTMP distribution. Signed cookies aren't supported for RTMP distributions.

- You want to restrict access to individual files, for example, an installation download for your application.

- Your users are using a client (for example, a custom HTTP client) that doesn't support cookies.

Use signed cookies for the following cases:

- You want to provide access to multiple restricted files, for example, all of the files for a video in HLS format or all of the files in the subscribers' area of a website.

- You don't want to change your current URLs.

Hence, the correct answer is: Use Signed Cookies to control who can access the private files in your CloudFront distribution by modifying your application to determine whether a user should have access to your content. For members, send the required Set-Cookie headers to the viewer which will unlock the content only to them.

The option that says: Configure your CloudFront distribution to use Match Viewer as its Origin Protocol Policy which will automatically match the user request. This will allow access to the private content if the request is a paying member and deny it if it is not a member is incorrect because a Match Viewer is an Origin Protocol Policy that configures CloudFront to communicate with your origin using HTTP or HTTPS, depending on the protocol of the viewer request. CloudFront caches the object only once even if viewers make requests using both HTTP and HTTPS protocols.

The option that says: Create a Signed URL with a custom policy which only allows the members to see the private files is incorrect because Signed URLs are primarily used for providing access to individual files, as shown in the above explanation. In addition, the scenario explicitly says that they don't want to change their current URLs which is why implementing Signed Cookies is more suitable than Signed URLs.

The option that says: Configure your CloudFront distribution to use Field-Level Encryption to protect your private data and only allow access to members is incorrect because Field-Level Encryption only allows you to securely upload user-submitted sensitive information to your web servers. It does not provide access to download multiple private files.

---

## Question 57

A company is experiencing repeated outages in the Availability Zone where its Amazon RDS database instance is deployed, resulting in a complete loss of access to the database during each incident.

Which solution should be implemented to prevent losing database access if this occurs again?

### Options

- Make a snapshot of the database
- Create a read replica
- __Enabled Multi-AZ failover__
- Increase the database instance size

### Correct Answer

Enabled Multi-AZ failover

### Explanation

Amazon RDS Multi-AZ deployments are designed to enhance the availability and durability of database instances, making them well-suited for production workloads. When you enable Multi-AZ failover, Amazon RDS automatically creates a standby replica in a different Availability Zone (AZ) and synchronously replicates data from the primary instance. This ensures high data consistency and protection against infrastructure-related disruptions. Each AZ operates on physically distinct infrastructure, which adds fault isolation and resilience.

Multi-AZ deployment and failover

In the event of planned maintenance or an unexpected failure such as an Availability Zone outage or hardware issue, Amazon RDS automatically performs a failover to the standby instance. This process is fully managed by Amazon RDS and does not require manual intervention, helping to minimize downtime and maintain business continuity. For Amazon Aurora, the failover involves promoting a replica to become the new writer instance.

Hence, the correct answer is: Enable Multi-AZ failover.

The option that says: Make a snapshot of the database is incorrect because snapshots are typically used for backup and disaster recovery, not for maintaining high availability. A snapshot allows you to restore a database to a specific point in time, but it does not prevent downtime or provide continuous access during an Availability Zone outage.

The option that says: Increase the database instance size is incorrect because this action just improves the instance's compute and memory capacity, which may help performance but does not address Availability Zone-level failures. The database would still be a single point of failure within the same zone, leaving it vulnerable to the same type of outage described in the question.

The option that says: Create a read replica is incorrect because read replicas are primarily intended to handle read-heavy workloads and do not automatically take over in the event of a failure. Promoting a read replica to a standalone instance requires manual intervention, which simply does not meet the goal of preventing loss of access during unplanned outages.

---

## Question 58

A Solutions Architect is hosting a website in an Amazon S3 bucket named tutorialsdojo. The users load the website using the following URL: http://tutorialsdojo.s3-website-us-east-1.amazonaws.com. A new requirement has been introduced to add JavaScript on the webpages to make authenticated HTTP GET requests against the same bucket using the S3 API endpoint (tutorialsdojo.s3.amazonaws.com). However, upon testing, the web browser blocks JavaScript from allowing those requests.

Which of the following options is the MOST suitable solution to implement for this scenario?

### Options

- Enable Cross-Zone Load Balancing.
- Enable cross-account access.
- Enable Cross-Region Replication (CRR).
- __Enable Cross-origin resource sharing (CORS) configuration in the bucket.__

### Correct Answer

Enable Cross-origin resource sharing (CORS) configuration in the bucket.

### Explanation

Cross-origin resource sharing (CORS) defines a way for client web applications that are loaded in one domain to interact with resources in a different domain. With CORS support, you can build rich client-side web applications with Amazon S3 and selectively allow cross-origin access to your Amazon S3 resources.

Suppose that you are hosting a website in an Amazon S3 bucket named your-website and your users load the website endpoint http://your-website.s3-website-us-east-1.amazonaws.com. Now you want to use JavaScript on the webpages that are stored in this bucket to be able to make authenticated GET and PUT requests against the same bucket by using the Amazon S3 API endpoint for the bucket, your-website.s3.amazonaws.com. A browser would normally block JavaScript from allowing those requests, but with CORS you can configure your bucket to explicitly enable cross-origin requests from your-website.s3-website-us-east-1.amazonaws.com.

Hence, the correct answer is: Enable Cross-origin resource sharing (CORS) configuration in the bucket.

The option that says: Enable cross-account access is incorrect because cross-account access is just a feature in IAM and not in Amazon S3.

The option that says: Enable Cross-Zone Load Balancing is incorrect because Cross-Zone Load Balancing is only used in ELB and not in S3.

The option that says: Enable Cross-Region Replication (CRR) is incorrect because CRR is a bucket-level configuration that enables automatic, asynchronous copying of objects across buckets in different AWS Regions.

---

## Question 59

A company is in the process of migrating their applications to AWS. One of their systems requires a database that can scale globally and handle frequent schema changes. The application should not have any downtime or performance issues whenever there is a schema change in the database. It should also provide a low latency response to high-traffic queries.

Which is the most suitable database solution to use to achieve this requirement?

### Options

- __Amazon DynamoDB__
- An Amazon Aurora database with Read Replicas
- Redshift
- An Amazon RDS instance in Multi-AZ Deployments configuration

### Correct Answer

Amazon DynamoDB

### Explanation

Before we proceed in answering this question, we must first be clear with the actual definition of a "schema". Basically, the english definition of a schema is: a representation of a plan or theory in the form of an outline or model.

Just think of a schema as the "structure" or a "model" of your data in your database. Since the scenario requires that the schema, or the structure of your data, changes frequently, then you have to pick a database which provides a non-rigid and flexible way of adding or removing new types of data. This is a classic example of choosing between a relational database and non-relational (NoSQL) database.

A relational database is known for having a rigid schema, with a lot of constraints and limits as to which (and what type of ) data can be inserted or not. It is primarily used for scenarios where you have to support complex queries which fetch data across a number of tables. It is best for scenarios where you have complex table relationships but for use cases where you need to have a flexible schema, this is not a suitable database to use.

For NoSQL, it is not as rigid as a relational database because you can easily add or remove rows or elements in your table/collection entry. It also has a more flexible schema because it can store complex hierarchical data within a single item which, unlike a relational database, does not entail changing multiple related tables. Hence, the best answer to be used here is a NoSQL database, like DynamoDB. When your business requires a low-latency response to high-traffic queries, taking advantage of a NoSQL system generally makes technical and economic sense.

Amazon DynamoDB helps solve the problems that limit the relational system scalability by avoiding them. In DynamoDB, you design your schema specifically to make the most common and important queries as fast and as inexpensive as possible. Your data structures are tailored to the specific requirements of your business use cases.

Remember that a relational database system does not scale well for the following reasons:

- It normalizes data and stores it on multiple tables that require multiple queries to write to disk.

- It generally incurs the performance costs of an ACID-compliant transaction system.

- It uses expensive joins to reassemble required views of query results.

For DynamoDB, it scales well due to these reasons:

- Its schema flexibility lets DynamoDB store complex hierarchical data within a single item. DynamoDB is not a totally schemaless database since the very definition of a schema is just the model or structure of your data.

- Composite key design lets it store related items close together on the same table.

An Amazon RDS instance in Multi-AZ Deployments configuration and an Amazon Aurora database with Read Replicas are incorrect because both of them are a type of relational database.

Redshift is incorrect because it is primarily used for OLAP systems.

---

## Question 60

A Forex trading platform, which frequently processes and stores global financial data every minute, is hosted in an on-premises data center and uses an Oracle database. Due to a recent cooling problem in its data center, the company urgently needs to migrate its infrastructure to AWS to improve the performance of its applications. As the Solutions Architect, the responsibility is to ensure that the database is properly migrated and remains available in case of database server failure in the future, following AWS Prescriptive Guidance for database migration and high availability.

Which combination of actions would meet the requirement? (Select TWO.)

### Options

- __Create an Oracle database in Amazon RDS with Multi-AZ deployments.__
- __Migrate the Oracle database to AWS using the AWS Database Migration Service__
- Convert the database schema using the AWS Schema Conversion Tool.
- Migrate the Oracle database to a non-cluster Amazon Aurora with a single instance.
- Launch an Oracle database instance in Amazon RDS with Recovery Manager (RMAN) enabled.

### Correct Answer

- Create an Oracle database in Amazon RDS with Multi-AZ deployments.
- Migrate the Oracle database to AWS using the AWS Database Migration Service

### Explanation

Amazon RDS Multi-AZ deployments provide enhanced availability and durability for Database (DB) Instances, making them a natural fit for production database workloads. When you provision a Multi-AZ DB Instance, Amazon RDS automatically creates a primary DB Instance and synchronously replicates the data to a standby instance in a different Availability Zone (AZ). Each AZ runs on its own physically distinct, independent infrastructure, and is engineered to be highly reliable.

Amazon RDS Multi-AZ deployments

In case of an infrastructure failure, Amazon RDS performs an automatic failover to the standby (or to a read replica in the case of Amazon Aurora) so that you can resume database operations as soon as the failover is complete. Since the endpoint for your DB Instance remains the same after a failover, your application can resume database operation without the need for manual administrative intervention.

In this scenario, the best RDS configuration to use is an Oracle database in RDS with Multi-AZ deployments to ensure high availability even if the primary database instance goes down. You can use AWS DMS to move the on-premises database to AWS with minimal downtime and zero data loss. It supports over 20 engines, including Oracle to Aurora MySQL, MySQL to RDS for MySQL, SQL Server to Aurora PostgreSQL, MongoDB to DocumentDB, Oracle to Redshift, and S3.

Hence, the correct answers are:

- Create an Oracle database in Amazon RDS with Multi-AZ deployments.

- Migrate the Oracle database to AWS using the AWS Database Migration Service.

The option that says: Launch an Oracle database instance in Amazon RDS with Recovery Manager (RMAN) enabled is incorrect because Oracle RMAN is not supported in RDS.

The option that says: Convert the database schema using the AWS Schema Conversion Tool is incorrect. AWS Schema Conversion Tool is typically used for heterogeneous migrations where you're moving from one type of database to another (e.g., Oracle to PostgreSQL). In the scenario, the migration is homogenous, meaning it's an Oracle-to-Oracle migration. As a result, there's no need to convert the schema since you're staying within the same database type.

The option that says: Migrate the Oracle database to a non-cluster Amazon Aurora with a single instance is incorrect. While a single-instance Aurora can be a feasible solution for non-critical applications or environments like development or testing, it is typically not suitable for applications that demand high availability.

## Question 61

An AI-powered Forex trading application consumes thousands of data sets to train its machine learning model. The application’s workload requires a high-performance, parallel hot storage to process the training datasets concurrently. It also needs cost-effective cold storage to archive those datasets that yield low profit.

Which of the following Amazon storage services should the developer use?

### Options

- Use Amazon FSx For Windows File Server and Amazon S3 for hot and cold storage respectively.
- Use Amazon Elastic File System and Amazon S3 for hot and cold storage respectively.
- Use Amazon FSx For Lustre and the Provisioned IOPS SSD (io1) volumes of Amazon EBS for hot and cold storage respectively.
- __Use Amazon FSx For Lustre and Amazon S3 for hot and cold storage respectively.__

### Correct Answer

Use Amazon FSx For Lustre and Amazon S3 for hot and cold storage respectively.

### Explanation

Hot storage refers to the storage that keeps frequently accessed data (hot data). Warm storage refers to the storage that keeps less frequently accessed data (warm data). Cold storage refers to the storage that keeps rarely accessed data (cold data). In terms of pricing, the colder the data, the cheaper it is to store, and the costlier it is to access when needed.

Amazon FSx For Lustre is a high-performance file system for fast processing of workloads. Lustre is a popular open-source parallel file system which stores data across multiple network file servers to maximize performance and reduce bottlenecks.

Amazon FSx for Windows File Server is a fully managed Microsoft Windows file system with full support for the SMB protocol, Windows NTFS, and Microsoft Active Directory (AD) Integration.

Amazon Elastic File System is a fully-managed file storage service that makes it easy to set up and scale file storage in the Amazon Cloud.

Amazon S3 is an object storage service that offers industry-leading scalability, data availability, security, and performance. S3 offers different storage tiers for different use cases (frequently accessed data, infrequently accessed data, and rarely accessed data).

The question has two requirements:

High-performance, parallel hot storage to process the training datasets concurrently.

Cost-effective cold storage to keep the archived datasets that are accessed infrequently.

In this case, we can use Amazon FSx For Lustre for the first requirement, as it provides a high-performance, parallel file system for hot data. On the second requirement, we can use Amazon S3 for storing cold data. Amazon S3 supports a cold storage system via Amazon S3 Glacier / Glacier Deep Archive.

Hence, the correct answer is: Use Amazon FSx For Lustre and Amazon S3 for hot and cold storage respectively.

---

## Question 62

A government entity is conducting a population and housing census in the city. Each household information uploaded on their online portal is stored in encrypted files in Amazon S3. The government assigned its Solutions Architect to set compliance policies that verify data containing personally identifiable information (PII) in a manner that meets their compliance standards. They should also be alerted if there are potential policy violations with the privacy of their S3 buckets.

Which of the following should the Architect implement to satisfy this requirement?

### Options

- Set up and configure Amazon Fraud Detector to send out alert notifications whenever a security violation is detected on their Amazon S3 data.
- __Set up and configure Amazon Macie to monitor their Amazon S3 data.__
- Set up and configure Amazon Kendra to monitor malicious activity on their Amazon S3 data
- Set up and configure Amazon Polly to scan for usage patterns on Amazon S3 data

### Correct Answer

Set up and configure Amazon Macie to monitor their Amazon S3 data.

### Explanation

Amazon Macie is an ML-powered security service that helps you prevent data loss by automatically discovering, classifying, and protecting sensitive data stored in Amazon S3. Amazon Macie uses machine learning to recognize sensitive data such as personally identifiable information (PII) or intellectual property, assigns a business value, and provides visibility into where this data is stored and how it is being used in your organization.

Amazon Macie generates two categories of findings: policy findings and sensitive data findings. A policy finding is a detailed report of a potential policy violation or issue with the security or privacy of an Amazon S3 bucket. Macie generates these findings as part of its ongoing monitoring activities for your Amazon S3 data. A sensitive data finding is a detailed report of sensitive data in an S3 object. Macie generates these findings when it discovers sensitive data in S3 objects that you configure a sensitive data discovery job to analyze.

Hence, the correct answer is: Set up and configure Amazon Macie to monitor their Amazon S3 data.

---

## Question 63

A global IT company with offices around the world has multiple AWS accounts. To improve efficiency and drive costs down, the Chief Information Officer (CIO) wants to set up a solution that centrally manages their AWS resources. This will allow them to procure AWS resources centrally and share resources such as AWS Transit Gateways, AWS License Manager configurations, or Amazon Route 53 Resolver rules across their various accounts.

As the Solutions Architect, which combination of options should you implement in this scenario? (Select TWO.)

### Options

- Consolidate all of the company's accounts using AWS ParallelCluster.
- __Use the AWS Resource Access Manager (RAM) service to easily and securely share your resources with your AWS accounts.__
- __Consolidate all of the company's accounts using AWS Organizations.__
- Use AWS Control Tower to easily and securely share your resources with your AWS accounts.
- Use the AWS Identity and Access Management service to set up cross-account access that will easily and securely share your resources with your AWS accounts.

### Correct Answer

- Use the AWS Resource Access Manager (RAM) service to easily and securely share your resources with your AWS accounts.
- Consolidate all of the company's accounts using AWS Organizations.

### Explanation

AWS Resource Access Manager (RAM) is a service that enables you to easily and securely share AWS resources with any AWS account or within your AWS Organization. You can share AWS Transit Gateways, Subnets, AWS License Manager configurations, and Amazon Route 53 Resolver rules resources with RAM.

Many organizations use multiple accounts to create administrative or billing isolation, and limit the impact of errors. RAM eliminates the need to create duplicate resources in multiple accounts, reducing the operational overhead of managing those resources in every single account you own. You can create resources centrally in a multi-account environment, and use RAM to share those resources across accounts in three simple steps: create a Resource Share, specify resources, and specify accounts.

AWS Organizations is an account management service that lets you consolidate multiple AWS accounts into an organization that you create and centrally manage.

Hence, the correct combination of options in this scenario is:

- Consolidate all of the company's accounts using AWS Organizations.
- Use the AWS Resource Access Manager (RAM) service to easily and securely share your resources with your AWS accounts.

---

## Question 64

A financial application consists of an Auto Scaling group of Amazon EC2 instances, an Application Load Balancer, and a MySQL RDS instance set up in a Multi-AZ Deployment configuration. To protect customers' confidential data, it must be ensured that the Amazon RDS database is only accessible using an authentication token specific to the profile credentials of EC2 instances.

Which of the following actions should be taken to meet this requirement?

### Options

- Configure SSL in your application to encrypt the database connection to RDS.
- Create an IAM Role and assign it to your EC2 instances which will grant exclusive access to your RDS instance.
- Use a combination of IAM and STS to enforce restricted access to your RDS instance using a temporary authentication token.
- __Enable the IAM DB Authentication.__

### Correct Answer

Enable the IAM DB Authentication.

### Explanation

You can authenticate to your DB instance using AWS Identity and Access Management (IAM) database authentication. IAM database authentication works with MySQL and PostgreSQL. With this authentication method, you don't need to use a password when you connect to a DB instance. Instead, you use an authentication token.

An authentication token is a unique string of characters that Amazon RDS generates on request. Authentication tokens are generated using AWS Signature Version 4. Each token has a lifetime of 15 minutes. You don't need to store user credentials in the database, because authentication is managed externally using IAM.

Hence, the correct answer is: Enable the IAM DB Authentication.

---

## Question 65

A company needs to deploy at least two Amazon EC2 instances to support the normal workloads of its application and automatically scale up to six EC2 instances to handle the peak load. The architecture must be highly available and fault-tolerant as it is processing mission-critical workloads.

As a Solutions Architect, what should be done to meet this requirement?

### Options

- Create an Auto Scaling group of EC2 instances and set the minimum capacity to 2 and the maximum capacity to 6. Deploy 4 instances in Availability Zone A.
- Create an Auto Scaling group of EC2 instances and set the minimum capacity to 2 and the maximum capacity to 6. Use 2 Availability Zones and deploy 1 instance for each AZ.
- __Create an Auto Scaling group of EC2 instances and set the minimum capacity to 4 and the maximum capacity to 6. Deploy 2 instances in Availability Zone A and another 2 instances in Availability Zone B.__
- Create an Auto Scaling group of EC2 instances and set the minimum capacity to 2 and the maximum capacity to 4. Deploy 2 instances in Availability Zone A and 2 instances in Availability Zone B.

### Correct Answer

Create an Auto Scaling group of EC2 instances and set the minimum capacity to 4 and the maximum capacity to 6. Deploy 2 instances in Availability Zone A and another 2 instances in Availability Zone B.

### Explanation

Amazon EC2 Auto Scaling helps ensure that you have the correct number of Amazon EC2 instances available to handle the load for your application.

To achieve highly available and fault-tolerant architecture for your applications, you must deploy all your instances in different Availability Zones. This will help isolate your resources if an outage occurs.

Since the scenario requires at least 2 instances to handle regular traffic, you should have 2 instances running all the time even if an AZ outage occurred. By configuring the Auto Scaling group with a minimum capacity of 4 across two Availability Zones, the application will still have 2 running instances even if one Availability Zone fails.

Hence, the correct answer is: Create an Auto Scaling group of EC2 instances and set the minimum capacity to 4 and the maximum capacity to 6. Deploy 2 instances in Availability Zone A and another 2 instances in Availability Zone B.

