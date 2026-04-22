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

Amazon CloudFront is a content delivery network (CDN) that can be used to deliver content to users around the world with low latency and high availability. CloudFront works by caching content on edge servers that are located close to the users who request the content. This can reduce latency and improve performance for users who are located far away from the origin of the content. To use CloudFront to deliver the static HTML pages, the solutions architect would need to create a CloudFront distribution and associate it with the S3 bucket that contains the files. Once the distribution is created, the solutions architect can update the links to the files on the event website to point to the CloudFront distribution domain name.

## Question 2

A security team wants to limit access to specific services or actions in all of the team’s AWS accounts. All accounts belong to a large organization in AWS Organizations. The solution must be scalable and there must be a single point where permissions can be maintained. What should a solutions architect do to accomplish this?

### Options

- __Create a service control policy in the root organizational unit to deny access to the services or actions.__
- Create an ACL to provide access to the services or actions.
- Create a security group to allow accounts and attach it to user groups.
- Create cross-account roles in each account to deny access to the services or actions.

### Correct Answer

Create a service control policy in the root organizational unit to deny access to the services or actions.

### Explanation

Service control policies (SCPs) are a type of organization policy that can be used to manage permissions in AWS Organizations. SCPs offer central control over the maximum available permissions for all accounts in an organization. SCPs can be used to deny access to specific services or actions, and they can be applied to all accounts in an organization or to specific organizational units.

## Question 3

A company is concerned about the security of its public web application due to recent web attacks. The application uses an Application Load Balancer (ALB). A solutions architect must reduce the risk of DDoS attacks against the application. Which of the following options is correct?

### Options

- Configure Amazon Guard Duty to monitor the ALB.
- __Enable AWS Shield Advanced to prevent attacks.__
- Configure Amazon Macie to prevent attacks.
- Add an Amazon Inspector agent to the ALB.

### Correct Answer

Enable AWS Shield Advanced to prevent attacks.

### Explanation

AWS Shield Advanced is a managed DDoS protection service that helps you protect your applications from DDoS attacks. It provides comprehensive protection against a wide range of attacks, including volumetric attacks, application layer attacks, and protocol attacks. To enable AWS Shield Advanced, you need to create a Shield Advanced subscription and associate it with the ALB. Once you have enabled Shield Advanced, AWS will automatically monitor and mitigate DDoS attacks against your application.

## Question 4

One of your instances is reporting an unhealthy system status check. However, this is not something you should have to monitor and repair on your own. How might you automate the repair of the system status check failure in an AWS environment?

### Options

- Write a script that queries the EC2 API for each instance status check
- Implement a third party monitoring tool such as Nagios
- __Create CloudWatch metrics that stop and then start the instance based off of status check alarms__
- Write a script that periodically shuts down and starts instances

### Correct Answer

Create CloudWatch metrics that stop and then start the instance based off of status check alarms

### Explanation

This  approach is the most efficient and scalable way to automate the repair process. CloudWatch metrics can be used to monitor the status of your instances and to trigger alarms when the status of an instance changes. When an alarm is triggered, CloudWatch can automatically take actions, such as stopping and starting the instance.

## Question 5

A news company web application is running on Amazon EC2 instances behind an Application Load Balancer. The news company recently changed its policy, which now requires the application to be accessed from one specific country only. Which configuration will meet this requirement?

### Options

- Configure the network ACL for the subnet that contains the EC2 instances.
- Configure the security group for the EC2 instances.
- Configure the security group on the Application Load Balancer.
- __Configure AWS WAF on the Application Load Balancer in a VPC.__

### Correct Answer

Configure AWS WAF on the Application Load Balancer in a VPC.

### Explanation



## Question 6

A company provides an API to its users that automates inquiries for tax computations based on item prices. The company experiences a larger number of inquiries during the holiday season only that cause slower response times. A solutions architect needs to design a solution that is scalable and elastic. What should the solutions architect do to accomplish this?

### Options

- Design a REST API using Amazon API Gateway that connects with an API hosted on an Amazon EC2 instance. API Gateway accepts and passes the item names to the EC2 instance for tax computations.
- Create an Application Load Balancer that has two Amazon EC2 instances behind it. The EC2 instances will compute the tax on the received item names.
- Provide an API hosted on an Amazon EC2 instance. The EC2 instance performs the required computations when the API request is made.
- __Design a REST API using Amazon API Gateway that accepts the item names. API Gateway passes item names to AWS Lambda for tax computations.__

### Correct Answer

Design a REST API using Amazon API Gateway that accepts the item names. API Gateway passes item names to AWS Lambda for tax computations.

### Explanation

AWS Lambda is a serverless compute service that allows you to run code without provisioning or managing servers. This makes it a good choice for applications that need to be scalable and elastic. API Gateway is a fully managed service that makes it easy to create, publish, maintain, monitor, and secure APIs at any scale. It provides a variety of features, such as authentication, authorization, and rate limiting, which can be used to build secure and scalable APIs.

## Question 7

A gaming company hosts a browser-based application on AWS. The users of the application consume a large number of videos and images that are stored in Amazon S3. This content is the same for all users. The application has increased in popularity, and millions of users worldwide accessing these media files. The company wants to provide the files to the users while reducing the load on the origin. Which solution meets these requirements MOST cost-effectively?

### Options

- Deploy an Amazon ElastiCache for Memcached instance in front of the web servers.
- __Deploy an Amazon CloudFront web distribution in front of the S3 bucket.__
- Deploy an Amazon ElastiCache for Redis instance in front of the web servers.
- Deploy an AWS Global Accelerator accelerator in front of the web servers.

### Correct Answer

Deploy an Amazon CloudFront web distribution in front of the S3 bucket.

### Explanation

Amazon CloudFront is a content delivery network (CDN) that can be used to deliver content to users around the world with low latency and high availability. CloudFront works by caching content on edge servers that are located close to the users who request the content. This can reduce latency and improve performance for users who are located far away from the origin of the content. In this case, the company can create a CloudFront web distribution and associate it with the S3 bucket that contains the video and image files. CloudFront will then cache the files on edge servers around the world. When a user requests a video or image file, CloudFront will deliver the file from the edge server that is closest to the user. This will reduce the load on the origin S3 bucket and improve performance for users around the world.

## Question 8

A company is designing a cloud communications platform that is driven by APIs. The application is hosted on Amazon EC2 instances behind a Network Load Balancer (NLB). The company uses Amazon API Gateway to provide external users with access to the application through APIs. The company wants to protect the platform against web exploits like SQL injection and also wants to detect and mitigate large, sophisticated DDoS attacks. Which combination of solutions provides the MOST protection? (Choose two.)

### Options

- Use AWS Shield Standard with Amazon API Gateway.
- Use Amazon GuardDuty with AWS Shield Standard
- Use AWS WAF to protect the NLB.
- __Use AWS WAF to protect Amazon API Gateway.__
- __Use AWS Shield Advanced with the NLB.__

### Correct Answer

Use AWS WAF to protect Amazon API Gateway.  
Use AWS Shield Advanced with the NLB.

### Explanation

Use AWS WAF to protect the NLB. AWS WAF is a web application firewall that can help to protect your applications against common web attacks, such as SQL injection and cross-site scripting. Use AWS Shield Advanced with the NLB. AWS Shield Advanced is a managed DDoS protection service that can help to protect your applications against large, sophisticated DDoS attacks.

## Question 9

A company wants to migrate its MySQL database from on premises to AWS. The company recently experienced a database outage that significantly impacted the business. To ensure this does not happen again, the company wants a reliable database solution on AWS that minimizes data loss and stores every transaction on at least two nodes. Which of the following options is correct?

### Options

- Create an Amazon EC2 instance with a MySQL engine installed that triggers an AWS Lambda function to synchronously replicate the data to an Amazon RDS MySQL DB instance.
- Create an Amazon RDS MySQL DB instance and then create a read replica in a separate AWS Region that synchronously replicates the data.
- __Create an Amazon RDS MySQL DB instance with Multi-AZ functionality enabled to synchronously replicate the data.__
- Create an Amazon RDS DB instance with synchronous replication to three nodes in three Availability Zones.

### Correct Answer

Create an Amazon RDS MySQL DB instance with Multi-AZ functionality enabled to synchronously replicate the data.

### Explanation

This solution will provide a highly available and reliable database that minimizes data loss and stores every transaction on at least two nodes. Multi-AZ is a feature of Amazon RDS that automatically provisions and maintains a synchronous standby replica in a different Availability Zone. If the primary database instance fails, Multi-AZ will automatically failover to the standby replica.

## Question 10

An IT Company is building a new dynamic ordering website. The company wants to minimize server maintenance and patching. The website must be highly available and must scale read and write capacity as quickly as possible to meet changes in user demand. Which of the following options is correct?

### Options

- Host all the website content on Amazon EC2 instances. Create an Auto Scaling group to scale the EC2 instances. Use an Application Load Balancer to distribute traffic. Use Amazon Aurora with Aurora Auto Scaling for the database.
- Host all the website content on Amazon EC2 instances. Create an Auto Scaling group to scale the EC2 instances. Use an Application Load Balancer to distribute traffic. Use Amazon DynamoDB with provisioned write capacity for the database.
- Host static content in Amazon S3. Host dynamic content by using Amazon API Gateway and AWS Lambda. Use Amazon Aurora with Aurora Auto Scaling for the database. Configure Amazon CloudFront to deliver the website content.
- __Host static content in Amazon S3. Host dynamic content by using Amazon API Gateway and AWS Lambda. Use Amazon DynamoDB with on-demand capacity for the database. Configure Amazon CloudFront to deliver the website content.__

### Correct Answer

Host static content in Amazon S3. Host dynamic content by using Amazon API Gateway and AWS Lambda. Use Amazon DynamoDB with on-demand capacity for the database. Configure Amazon CloudFront to deliver the website content.

### Explanation

The company wants to minimize server maintenance and patching, so hosting static content in Amazon S3 and dynamic content using Amazon API Gateway and AWS Lambda will help them achieve this goal. Amazon S3 is a highly available and scalable object storage service that can store static content, such as images, CSS, and JavaScript files, without the need for any server maintenance or patching. Amazon API Gateway is a fully managed service that allows you to create, publish, maintain, monitor, and secure APIs at any scale. AWS Lambda is a serverless compute service that lets you run code without provisioning or managing servers. By using these services, the company can offload the responsibility of managing and patching servers to AWS. The website must be highly available, so using Amazon DynamoDB with on-demand capacity for the database will help them achieve this goal. Amazon DynamoDB is a fully managed NoSQL database service that provides high availability and scalability. On-demand capacity is a pricing model that allows you to pay only for the resources you use. This will help the company minimize costs during periods of low traffic.

## Question 11

A company runs an application using Amazon ECS. The application creates resized versions of an original image and then makes Amazon S3 API calls to store the resized images in Amazon S3. How can a solutions architect ensure that the application has permission to access Amazon S3?

### Options

- __Create an  IAM  role with S3 permissions, and then specify that role as the taskRoleArn in the task definition.__
- Create an IAM user with S3 permissions, and then relaunch the Amazon EC2 instances for the ECS cluster while logged in as this account.
- Create a security group that allows access from Amazon ECS to Amazon S3, and update the launch configuration used by the ECS cluster.
- Update the S3 role in AWS IAM to allow read/write access from Amazon ECS, and then relaunch the container.

### Correct Answer

Create an  IAM  role with S3 permissions, and then specify that role as the taskRoleArn in the task definition.

### Explanation

This solution will grant the application the necessary permissions to access Amazon S3 without requiring any changes to the application code. The IAM role will be attached to the task when it is launched, and the task will be able to use the permissions of the IAM role to make Amazon S3 API calls.

## Question 12

A company has a Windows-based application that must be migrated to AWS. The application requires the use of a shared Windows file system attached to multiple Amazon EC2 Windows instances that are deployed across multiple Availability Zone: Which of the following options should does the solutions architect recommend to meet this requirement?

### Options

- Configure an Amazon Elastic Block Store (Amazon EBS) volume with the required size. Attach each EC2 instance to the volume. Mount the file system within the volume to each Windows instance.
- Configure a file system by using Amazon Elastic File System (Amazon EFS). Mount the EFS file system to each Windows instance.
- __Configure Amazon FSx for Windows File Server. Mount the Amazon FSx file system to each Windows instance.__
- Configure AWS Storage Gateway in volume gateway mode. Mount the volume to each Windows instance.

### Correct Answer

Configure Amazon FSx for Windows File Server. Mount the Amazon FSx file system to each Windows instance.

### Explanation

Amazon FSx for Windows File Server is a fully managed file system that provides native Windows compatibility, enterprise performance, and enterprise features. It is a good choice for applications that require a highly available, scalable, and secure shared Windows file system. By using Amazon FSx for Windows File Server, the company can avoid the need to manage the underlying storage infrastructure. This will reduce the company's operational overhead and allow them to focus on their application.

## Question 13

A company is developing an ecommerce application that will consist of a load-balanced front end, a container-based application, and a relational database. A solutions architect needs to create a highly available solution that operates with as little manual intervention as possible. Which solutions meet these requirements? (Choose two.)

### Options

- __Create an Amazon RDS DB instance in Multi-AZ mode.__
- __Create an Amazon Elastic Container Service (Amazon ECS) cluster with a Fargate launch type to handle the dynamic application load.__
- Create an Amazon Elastic Container Service (Amazon ECS) cluster with an Amazon EC2 launch type to handle the dynamic application load.
- Create an Amazon EC2 instance-based Docker cluster to handle the dynamic application load.
- Create an Amazon RDS DB instance and one or more replicas in another Availability Zone.

### Correct Answer

Create an Amazon RDS DB instance in Multi-AZ mode.  
Create an Amazon Elastic Container Service (Amazon ECS) cluster with a Fargate launch type to handle the dynamic application load.

### Explanation

Amazon RDS DB instance in Multi-AZ mode ensures high availability by automatically replicating the database across multiple Availability Zones. This configuration ensures data redundancy and minimizes downtime in case of an Availability Zone outage. Amazon ECS cluster with a Fargate launch type provides a serverless container management service that eliminates the need to manage and provision underlying infrastructure. It automatically scales containers based on demand, ensuring optimal resource utilization and cost-efficiency.

## Question 14

A company uses Amazon S3 as its data lake. The company has a new partner that must use SFTP to upload data files. A solutions architect needs to implement a highly available SFTP solution that minimizes operational overhead. Which of the following options is correct?

### Options

- Launch Amazon EC2 instances in a private subnet in a VPC. Place a Network Load Balancer (NLB) in front of the EC2 instances. Create an SFTP listener port for the NLB. Share the NLB hostname with the new partner. Run a cron job script on the EC2 instances to upload files to the S3 data lake.
- __Use AWS Transfer Family to configure an SFTP-enabled server with a publicly accessible endpoint. Choose the S3 data lake as the destination.__
- Launch an Amazon EC2 instance in a private subnet in a VPInstruct the new partner to upload files to the EC2 instance by using a VPN. Run a cron job script, on the EC2 instance to upload files to the S3 data lake.
- Use Amazon S3 File Gateway as an SFTP server. Expose the S3 File Gateway endpoint URL to the new partner. Share the S3 File Gateway endpoint with the new partner.

### Correct Answer

Use AWS Transfer Family to configure an SFTP-enabled server with a publicly accessible endpoint. Choose the S3 data lake as the destination.

### Explanation

This solution will provide a highly available and scalable SFTP server that is easy to manage and secure. AWS Transfer Family is a fully managed service that makes it easy to create, configure, and manage SFTP servers. It also provides a secure endpoint that can be accessed by the new partner.

## Question 15

A financial company has a web application that is based on Java and PHP. The company plans to move the application from on premises to AWS. The company needs the ability to test new site features frequently. The company also needs a highly available and managed solution that requires minimum operational overhead. Which of the following options is correct?

### Options

- Containerize the web application. Deploy the web application to Amazon EC2 instances. Use the AWS Load Balancer Controller to dynamically route traffic between containers that contain the new site features for testing.
- Deploy the web application to Amazon EC2 instances that are configured with Java and PHP. Use Auto Scaling groups and an Application Load Balancer to manage the website’s availability.
- __Deploy the web application to an AWS Elastic Beanstalk environment. Use URL swapping to switch between multiple Elastic Beanstalk environments for feature testing.__
- Create an Amazon S3 bucket. Enable static web hosting on the S3 bucket. Upload the static content to the S3 bucket. Use AWS Lambda to process all dynamic content.

### Correct Answer

Deploy the web application to an AWS Elastic Beanstalk environment. Use URL swapping to switch between multiple Elastic Beanstalk environments for feature testing.

### Explanation

AWS Elastic Beanstalk is a fully managed service that makes it easy to deploy and manage web applications. It supports a variety of programming languages, including Java and PHP. It also provides a number of features that are useful for feature testing, such as URL swapping and environment rollback. Using URL swapping, the company can create a separate Elastic Beanstalk environment for each new feature. This will allow them to test the new feature without affecting the production environment. Once they are finished testing, they can use URL swapping to switch the traffic from the production environment to the new feature environment.

## Question 16

A company has an ordering application that stores customer information in Amazon RDS for MySQL. During regular business hours, employees run one-time queries for reporting purposes. Timeouts are occurring during order processing because the reporting queries are taking a long time to run. The company needs to eliminate the timeouts without preventing employees from performing queries. Which of the following options should does the solutions architect recommend to meet this requirement?

### Options

- Schedule the reporting queries for non-peak hours.
- Create a read replica. Distribute the ordering application to the primary DB instance and the read replica.
- Migrate the ordering application to Amazon DynamoDB with on-demand capacity.
- __Create a read replica. Move reporting queries to the read replica.__

### Correct Answer

Create a read replica. Move reporting queries to the read replica.

### Explanation

The most effective solution to meet the company's requirements is to create a read replica and move the reporting queries to the read replica. This approach will offload the reporting queries from the primary database instance, which is currently being overloaded by these queries. By moving the reporting queries to the read replica, the company can ensure that the ordering application remains responsive during regular business hours.

## Question 17

A new hospital wants to create digital copies for its large collection of historical written records. The hospital will continue to add hundreds of new documents each day. The hospital’s data team will scan the documents and will upload the documents to the AWS Cloud. A solutions architect must implement a solution to analyze the documents, extract the medical information, and store the documents so that an application can run SQL queries on the data. The solution must maximize scalability and operational efficiency. Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)

### Options

- __Create an AWS Lambda function that runs when new documents are uploaded. Use Amazon Textract to convert the documents to raw text. Use Amazon Comprehend Medical to detect and extract relevant medical information from the text.__
- __Write the document information to an Amazon S3 bucket. Use Amazon Athena to query the data.__
- Create an AWS Lambda function that runs when new documents are uploaded. Use Amazon Rekognition to convert the documents to raw text. Use Amazon Transcribe Medical to detect and extract relevant medical information from the text.
- Write the document information to an Amazon EC2 instance that runs a MySQL database.
- Create an Auto Scaling group of Amazon EC2 instances to run a custom application that processes the scanned files and extracts the medical information.

### Correct Answer

Create an AWS Lambda function that runs when new documents are uploaded. Use Amazon Textract to convert the documents to raw text. Use Amazon Comprehend Medical to detect and extract relevant medical information from the text.  
Write the document information to an Amazon S3 bucket. Use Amazon Athena to query the data.

### Explanation



## Question 18

A company’s order system sends requests from clients to Amazon EC2 instances. The EC2 instances process the orders and then store the orders in a database on Amazon RDS. Users report that they must reprocess orders when the system fails. The company wants a resilient solution that can process orders automatically if a system outage occurs. Which of the following options should does the solutions architect recommend to meet this requirement?

### Options

- Create an Amazon Simple Notification Service (Amazon SNS) topic. Create an AWS Lambda function, and subscribe the function to the SNS topic. Configure the order system to send messages to the SNS topic. Send a command to the EC2 instances to process the messages by using AWS Systems Manager Run Command.
- Move the EC2 instances into an Auto Scaling group. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to target an Amazon Elastic Container Service (Amazon ECS) task.
- __Move the EC2 instances into an Auto Scaling group. Configure the order system to send messages to an Amazon Simple Queue Service (Amazon SQS) queue. Configure the EC2 instances to consume messages from the queue.__
- Move the EC2 instances into an Auto Scaling group behind an Application Load Balancer (ALB). Update the order system to send messages to the ALB endpoint.

### Correct Answer

Move the EC2 instances into an Auto Scaling group. Configure the order system to send messages to an Amazon Simple Queue Service (Amazon SQS) queue. Configure the EC2 instances to consume messages from the queue.

### Explanation

This solution will provide a resilient and scalable order processing system that can automatically recover from system outages. By using an Auto Scaling group, the company can ensure that there are always enough EC2 instances available to process orders, even if some instances fail. By using an Amazon SQS queue, the company can decouple the order system from the EC2 instances, which will allow the order system to continue to send orders even if the EC2 instances are unavailable.

## Question 19

A company runs an application on a large fleet of Amazon EC2 instances. The application reads and writes entries into an Amazon DynamoDB table. The size of the DynamoDB table continuously grows, but the application needs only data from the last 30 days. The company needs a solution that minimizes cost and development effort. Which of the following options should does the solutions architect recommend to meet this requirement?

### Options

- __Extend the application to add an attribute that has a value of the current timestamp plus 30 days to each new item that is created in the table. Configure DynamoDB to use the attribute as the TTL attribute.__
- Use an AWS CloudFormation template to deploy the complete solution. Redeploy the CloudFormation stack every 30 days, and delete the original stack.
- Configure Amazon DynamoDB Streams to invoke an AWS Lambda function when a new item is created in the table. Configure the Lambda function to delete items in the table that are older than 30 days.
- Use an EC2 instance that runs a monitoring application from AWS Marketplace. Configure the monitoring application to use Amazon DynamoDB Streams to store the timestamp when a new item is created in the table. Use a script that runs on the EC2 instance to delete items that have a timestamp that is older than 30 days.

### Correct Answer

Extend the application to add an attribute that has a value of the current timestamp plus 30 days to each new item that is created in the table. Configure DynamoDB to use the attribute as the TTL attribute.

### Explanation



## Question 20

A financial company runs a containerized application on a Kubernetes cluster in an on-premises data center. The company is using a MongoDB database for data storage. The company wants to migrate some of these environments to AWS, but no code changes or deployment method changes are possible at this time. The company needs a solution that minimizes operational overhead. Which of the following options should does the solutions architect recommend to meet this requirement?

### Options

- Use Amazon Elastic Container Service (Amazon ECS) with Amazon EC2 worker nodes for compute and MongoDB on EC2 for data storage.
- __Use Amazon Elastic Kubernetes Service (Amazon EKS) with AWS Fargate for compute and Amazon DocumentDB (with MongoDB compatibility) for data storage.__
- Use Amazon Elastic Container Service (Amazon ECS) with AWS Fargate for compute and Amazon DynamoDB for data storage
- Use Amazon Elastic Kubernetes Service (Amazon EKS) with Amazon EC2 worker nodes for compute and Amazon DynamoDB for data storage.

### Correct Answer

Use Amazon Elastic Kubernetes Service (Amazon EKS) with AWS Fargate for compute and Amazon DocumentDB (with MongoDB compatibility) for data storage.

### Explanation

This solution will provide the company with a highly available and scalable Kubernetes cluster that is fully managed by AWS. Fargate will eliminate the need for the company to manage EC2 instances, which will reduce operational overhead. Amazon DocumentDB is a NoSQL document database that is compatible with MongoDB, so the company will not need to make any changes to their application code.

## Question 21

A telemarketing company is designing its customer call center functionality on AWS. The company needs a solution that provides multiple speaker recognition and generates transcript files. The company wants to query the transcript files to analyze the business patterns. The transcript files must be stored for 7 years for auditing purposes. Which of the following options should does the solutions architect recommend to meet this requirement?

### Options

- Use Amazon Rekognition for multiple speaker recognition. Store the transcript files in Amazon S3. Use machine learning models for transcript file analysis.
- __Use Amazon Transcribe for multiple speaker recognition. Use Amazon Athena for transcript file analysis.__
- Use Amazon Rekognition for multiple speaker recognition. Store the transcript files in Amazon S3. Use Amazon Textract for transcript file analysis
- Use Amazon Translate for multiple speaker recognition. Store the transcript files in Amazon Redshift. Use SQL queries for transcript file analysis.

### Correct Answer

Use Amazon Transcribe for multiple speaker recognition. Use Amazon Athena for transcript file analysis.

### Explanation

mazon Transcribe is specifically designed for transcribing audio and video recordings, including conversations with multiple speakers. It can accurately identify and separate different speakers in a conversation and provide transcripts for each speaker.

## Question 22

A company hosts its application on AWS. The company uses Amazon Cognito to manage users. When users log in to the application, the application fetches required data from Amazon DynamoDB by using a REST API that is hosted in Amazon API Gateway. The company wants an AWS managed solution that will control access to the REST API to reduce development efforts. Which of the following options is correct?

### Options

- Configure an AWS Lambda function to be an authorizer in API Gateway to validate which user made the request.
- Send the user’s email address in the header with every request. Invoke an AWS Lambda function to validate that the user with that email address has proper access.
- __Configure an Amazon Cognito user pool authorizer in API Gateway to allow Amazon Cognito to validate each request.__
- For each user, create and assign an API key that must be sent with each request. Validate the key by using an AWS Lambda function.

### Correct Answer

Configure an Amazon Cognito user pool authorizer in API Gateway to allow Amazon Cognito to validate each request.

### Explanation

This solution will provide the company with a secure and scalable way to control access to their REST API. Amazon Cognito is a fully managed service that makes it easy to manage user authentication, authorization, and access control. By using an Amazon Cognito user pool authorizer, the company can offload the responsibility of validating user requests to Amazon Cognito, which will reduce their operational overhead. Related link-https://aws.amazon.com/premiumsupport/knowledge-center/api-gateway-cognito-user-pool-authorizer/

## Question 23

The customers of a finance company request appointments with financial advisors by sending text messages. A web application that runs on Amazon EC2 instances accepts the appointment requests. The text messages are published to an Amazon Simple Queue Service (Amazon SQS) queue through the web application. Another application that runs on EC2 instances then sends meeting invitations and meeting confirmation email messages to the customers. After successful scheduling, this application stores the meeting information in an Amazon DynamoDB database. As the company expands, customers report that their meeting invitations are taking longer to arrive. Which of the following options should does the solutions architect recommend to meet this requirement?

### Options

- Add a DynamoDB Accelerator (DAX) cluster in front of the DynamoDB database.
- __Add an Auto Scaling group for the application that sends meeting invitations. Configure the Auto Scaling group to scale based on the depth of the SQS queue.__
- Add an Amazon API Gateway API in front of the web application that accepts the appointment requests.
- Add an Amazon CloudFront distribution. Set the origin as the web application that accepts the appointment requests.

### Correct Answer

Add an Auto Scaling group for the application that sends meeting invitations. Configure the Auto Scaling group to scale based on the depth of the SQS queue.

### Explanation

The best solution to resolve the issue of meeting invitations taking longer to arrive is to add an Auto Scaling group for the application that sends meeting invitations. Configure the Auto Scaling group to scale based on the depth of the Amazon Simple Queue Service (Amazon SQS) queue.

## Question 24

A globle online retail company has more than 50 million active customers and receives more than 25,000 orders each day. The company collects purchase data for customers and stores this data in Amazon S3. Additional customer data is stored in Amazon RDS. The company wants to make all the data available to various teams so that the teams can perform analytics. The solution must provide the ability to manage fine-grained permissions for the data and must minimize operational overhead. Which of the following options is correct?

### Options

- Create an Amazon Redshift cluster. Schedule an AWS Lambda function to periodically copy data from Amazon S3 and Amazon RDS to Amazon Redshift. Use Amazon Redshift access controls to limit access.
- __Create a data lake by using AWS Lake Formation. Create an AWS Glue JDBC connection to Amazon RDS. Register the S3 bucket in Lake Formation. Use Lake Formation access controls to limit access.__
- Migrate the purchase data to write directly to Amazon RDS. Use RDS access controls to limit access.
- Schedule an AWS Lambda function to periodically copy data from Amazon RDS to Amazon S3. Create an AWS Glue crawler. Use Amazon Athena to query the data. Use S3 policies to limit access.

### Correct Answer

Create a data lake by using AWS Lake Formation. Create an AWS Glue JDBC connection to Amazon RDS. Register the S3 bucket in Lake Formation. Use Lake Formation access controls to limit access.

### Explanation

AWS Lake Formation provides a comprehensive solution for building and managing a data lake. It simplifies data ingestion, organization, and access control. By creating a data lake using AWS Lake Formation, you can centralize and govern access to your data across multiple sources.

## Question 25

A solutions architect is designing the architecture of a new application being deployed to the AWS Cloud. The application will run on Amazon EC2 On-Demand Instances and will automatically scale across multiple Availability Zones. The EC2 instances will scale up and down frequently throughout the day. An Application Load Balancer (ALB) will handle the load distribution. The architecture needs to support distributed session data management. The company is willing to make changes to code if needed. What should the solutions architect do to ensure that the architecture supports distributed session data management?

### Options

- Use the GetSessionToken API operation in AWS Security Token Service (AWS STS) to manage the session.
- Use session affinity (sticky sessions) of the ALB to manage session data.
- Use Session Manager from AWS Systems Manager to manage the session.
- __Use Amazon ElastiCache to manage and store session data.__

### Correct Answer

Use Amazon ElastiCache to manage and store session data.

### Explanation

Amazon ElastiCache is a fully managed in-memory data store that is designed to handle high-throughput workloads. It is a good choice for managing session data, as it can provide low latency and high availability. Additionally, Amazon ElastiCache is easy to use and can be integrated with the ALB to automatically scale with the application.

## Question 26

You receive a bill from AWS but are confused as the exact same storage size you have in different regions on Amazon S3 are incurring different costs. You enquire to AWS as to why this is so. What response would you expect to receive from AWS ?

### Options

- It must be a mistake.
- __We charge less where our costs are less .__
- This will balance out next bill .
- We charge less in different time zones.

### Correct Answer

We charge less where our costs are less .

### Explanation



## Question 27

You created a Windows EC2 instance with a public IP address and installed SQL Server. When attempting to connect to SQL Server from SQL Server Enterprise Manager on your local computer, the Windows EC2 instance is unable to establish a connection to the server. What is the first thing you should check?

### Options

- Check the routing tables for the VPC
- Check the policies within Windows Firewall.
- __Verify that the assigned security groups allow TCP port 1433 traffic from your current IP address.__
- Verify that you are connecting to the instance using a user that is not same.

### Correct Answer

Verify that the assigned security groups allow TCP port 1433 traffic from your current IP address.

### Explanation



## Question 28

Choose the correct statements. (Choose 3 correct answers)

### Options

- An S3 object can be of unlimited size
- You can use Reduced Redundancy storage for lower cost option
- __You can serve your static website from S3__
- Data stored in S3 is encrypted
- __You can have unlimited number of objects in S3 bucket__

### Correct Answer

You can serve your static website from S3  
You can have unlimited number of objects in S3 bucket

### Explanation



## Question 29

How do you achieve single sign on with AWS (choose 1 correct answers)

### Options

- It is currently not possible in AWS
- By Using Multi-factor authentication
- By Using active directory and LDAP integration
- __By Configuring SAML 2.0__
- It is configurable in the IAM policies for the user

### Correct Answer

By Configuring SAML 2.0

### Explanation



## Question 30

In CloudFront what happens when content is NOT present at an Edge location and a request is made to it? (Choose 1 correct answer)

### Options

- The request is kept on hold till content is delivered to the edge location
- An Error 404 not found is returned
- The request is routed to the next closest edge location
- __CloudFront delivers the content directly from the origin server and stores it in the cache of the edge location__

### Correct Answer

CloudFront delivers the content directly from the origin server and stores it in the cache of the edge location

### Explanation

## Question 31

DDoS attacks that happen at the application layer commonly target web applications with lower volumes of traffic compared to infrastructure attacks. To mitigate these types of attacks, you should probably want to include a WAF (Web Application Firewall) as part of your infrastructure. To inspect all HTTP requests, WAFs sit in-line with your application traffic. Unfortunately, this creates a scenario where WAFs can become a point of failure or bottleneck. To mitigate this problem, you need the ability to run multiple WAFs on demand during traffic spikes. This type of scaling for WAF is done via a “WAF sandwich.” Which of the following statements best describes what a “WAF sandwich” is?

### Options

- The EC2 instance running your WAF software is placed between your private subnets and any NATed connections to the Internet.
- The EC2 instance running your WAF software is placed between your public subnets and your private subnets.
- The EC2 instance running your WAF software is placed between your public subnets and your Internet Gateway
- __The EC2 instance running your WAF software is included in an Auto Scaling group and placed in between two Elastic load balancers__

### Correct Answer

The EC2 instance running your WAF software is included in an Auto Scaling group and placed in between two Elastic load balancers

### Explanation



## Question 32

You have two Elastic Compute Cloud (EC2) instances inside a Virtual Private Cloud (VPC) in the same Availability Zone (AZ) but in different subnets. One instance is running a database and the other instance an application that will interface with the database. You want to confirm that they can talk to each other for your application to work properly. Which two things do we need to confirm in the VPC settings so that these EC2 instances can communicate inside the VPC? Choose 2 answers

### Options

- Both instances are the same instance class and using the same Key-pair.
- __A network ACL that allows communication between the two subnets.__
- That the default route is set to a NAT instance or Internet Gateway (IGW) for them to communicate.
- __Security groups are set to allow the application host to talk to the database on the right port/protocol__

### Correct Answer

A network ACL that allows communication between the two subnets.  
Security groups are set to allow the application host to talk to the database on the right port/protocol

### Explanation



## Question 33

A user has created a VPC with CIDR 20.0.0.0/24. The user has created a public subnet with CIDR 20.0.0.0/25. The user is trying to create the private subnet with CIDR 20.0.0.128/25. Which of the below mentioned statements is true in this scenario?

### Options

- __It will allow the user to create a private subnet with CIDR as 20.0.0.128/25__
- It will not allow the user to create a private subnet due to a wrong CIDR range
- This statement is wrong as AWS does not allow CIDR 20.0.0.0/25
- It will not allow the user to create the private subnet due to a CIDR overlap

### Correct Answer

It will allow the user to create a private subnet with CIDR as 20.0.0.128/25

### Explanation



## Question 34

An instance is connected to an ENI (Elastic Network Interface) in one subnet. What happens when you attach an ENI of a different subnet to this instance? (choose 1 correct answers)

### Options

- The instance follows the rules of the newer subnet
- Not possible cannot be connected to 2 ENIs
- __The instance follows the rules of both the subnets__
- The instance follows the rules of the older subne

### Correct Answer

The instance follows the rules of both the subnets

### Explanation



## Question 35

You are currently hosting multiple applications in a VPC and have logged numerous port scans coming in from a specific IP address block. Your security team has requested that all access from the offending IP address block be denied for the next 24 hours. Which of the following is the best method to quickly and temporarily deny access from the specified IP address block?

### Options

- __Modify the Network ACLs associated with all public subnets in the VPC to deny access from the IP address block__
- Modify the Windows Firewall settings on all Amazon Machine Images (AMIs) that your organization uses in that VPC to deny access from the IP address block
- Add a rule to all of the VPC 5 Security Groups to deny access from the IP address block
- Create an AD policy to modify Windows Firewall settings on all hosts in the VPC to deny access from the IP address block

### Correct Answer

Modify the Network ACLs associated with all public subnets in the VPC to deny access from the IP address block

### Explanation



## Question 36

What are the characteristics of Elastic Beanstalk ? (choose 2 correct answers)

### Options

- You can use it to replace an instance in the ELB when it fails its health check
- __Helps you quickly deploy and manage applications in the AWS cloud__
- __You don’t need to worry about the infrastructure required to run your applications__
- It creates a template for your EC2 instance

### Correct Answer

Helps you quickly deploy and manage applications in the AWS cloud  
You don’t need to worry about the infrastructure required to run your applications

### Explanation



## Question 37

A user has created a VPC with public and private subnets. The VPC has CIDR 20.0.0.0/16. The private subnet uses CIDR 20.0.1.0/24 and the public subnet uses CIDR 20.0.0.0/24. The user is planning to host a web server in the public subnet (port 80. and a DB server in the private subnet (port 3306.. The user is configuring a security group of the NAT instance. Which of the below mentioned entries is not required for the NAT security group?

### Options

- For Outbound allow Destination: 0.0.0.0/0 on port 443
- For Outbound allow Destination: 0.0.0.0/0 on port 80
- For Inbound allow Source: 20.0.1.0/24 on port 80
- __For Inbound allow Source: 20.0.0.0/24 on port 80__

### Correct Answer

For Inbound allow Source: 20.0.0.0/24 on port 80

### Explanation



## Question 38

What are the characteristics of Subnet ? (Choose 2 correct answers)

### Options

- __Network traffic entering and exiting each subnet can be allowed or denied via network Access Control Lists (ACLs)__
- __Default subnets are assigned a /20 netblocks__
- Default subnets are assigned a /16 netblock
- A subnet can be across multiple regions
- A subnet can be across multiple availability zones

### Correct Answer

Network traffic entering and exiting each subnet can be allowed or denied via network Access Control Lists (ACLs)  
Default subnets are assigned a /20 netblocks

### Explanation



## Question 39

What kind of data should not be stored in S3 ?

### Options

- Images and videos
- __Your website database__
- Static files for your websites
- __Notifications from a computer program__

### Correct Answer

Your website database  
Notifications from a computer program

### Explanation



## Question 40

When you put objects in Amazon S3, what is the indication that an object was successfully stored?

### Options

- Each S3 account has a special bucket named_s3_logs. Success codes are written to this bucket with a timestamp and checksum.
- Amazon S3 is engineered for 99.999999999% durability. Therefore there is no need to confirm that data was inserted.
- A success code is inserted into the S3 object metadata.
- __A HTTP 200 result code and MD5 checksum, taken together, indicate that the operation was successful.__

### Correct Answer

A HTTP 200 result code and MD5 checksum, taken together, indicate that the operation was successful.

### Explanation

## Question 41

Once again your security officer is on your case and this time is asking you to make sure the AWS Key Management Service (AWS KMS) is working as it is supposed to. You are initially not too sure how KMS even works, however after some intense late night reading you think you have come up with a reasonable definition. Which of the following best describes how the AWS Key Management Service works?

### Options

- __AWS KMS supports two kinds of keys — master keys and data keys. Master keys can be used to directly encrypt and decrypt up to 4 kilobytes of data and can also be used to protect data keys. The data keys are then used to encrypt the customer data and the master keys are used to decrypt the customer data.__
- AWS KMS supports two kinds of keys — master keys and data keys. Master keys can be used to directly encrypt and decrypt up to 4 kilobytes of data and can also be used to protect data keys. The data keys are then used to encrypt and decrypt customer data.
- AWS KMS supports two kinds of keys — master keys and data keys. Master keys can be used to directly encrypt and decrypt up to 4 kilobytes of data and can also be used to protect data keys. The master keys are then used to encrypt and decrypt customer data.
- AWS KMS supports two kinds of keys — master keys and data keys. Master keys can be used to directly encrypt and decrypt up to 4 kilobytes of data and can also be used to protect data keys. The data keys are then used to decrypt the customer data, and the master keys are used to encrypt the customer data.

### Correct Answer

AWS KMS supports two kinds of keys — master keys and data keys. Master keys can be used to directly encrypt and decrypt up to 4 kilobytes of data and can also be used to protect data keys. The data keys are then used to encrypt the customer data and the master keys are used to decrypt the customer data.

### Explanation



## Question 42

You are setting up some EBS volumes for a customer who has requested a setup which includes a RAID (redundant array of inexpensive disks). AWS has certain recommendations for RAID setup. Which RAID setup is not recommended for Amazon EBS

### Options

- __RAID 5 and Raid 6__
- RAID 1 and Raid 6
- RAID 0 only
- RAID 5 only

### Correct Answer

RAID 5 and Raid 6

### Explanation



## Question 43

A web company is looking to implement an external payment service into their highly available application deployed in a VPC. Their application EC2 instances are behind a public facing ELB. Auto scaling is used to add additional instances as traffic increases. Under normal load the application runs 2 instances in the Auto Scaling group but at peak it can scale 3x in size. The application instances need to communicate with the payment service over the Internet, which requires whitelisting of all public IP addresses used to communicate with it. A maximum of 4 whitelisting IP addresses are allowed at a time and can be added through an API. How should they architect their solution?

### Options

- Whitelist the ELB IP addresses and route payment requests from the Application servers through the ELB. (ELB does not have a fixed IP address)
- __Route payment requests through two NAT instances setup for High Availability and whitelist the Elastic IP addresses attached to the NAT instances__
- Automatically assign public IP addresses to the application instances in the Auto Scaling group and run a script on boot that adds each instances public IP address to the payment validation whitelist API. (would exceed the allowed 4 IP addresses)
- Whitelist the VPC Internet Gateway Public IP and route payment requests through the Internet Gateway. (Internet gateway is only to route traffic)

### Correct Answer

Route payment requests through two NAT instances setup for High Availability and whitelist the Elastic IP addresses attached to the NAT instances

### Explanation



## Question 44

A customer is hosting their company website on a cluster of web servers that are behind a public-facing load balancer. The customer also uses Amazon Route 53 to manage their public DNS. How should the customer configure the DNS zone apex record to point to the load balancer?

### Options

- __Create an A record aliased to the load balancer DNS name__
- Create a CNAME record aliased to the load balancer DNS name.
- Create an A record pointing to the IP address of the load balancer
- Create a CNAME record pointing to the load balancer DNS name

### Correct Answer

Create an A record aliased to the load balancer DNS name

### Explanation



## Question 45

You have four front-end web servers behind a load balancer, which use NFS to access another EC2 instance that resizes and stores images for the front-end application. What security group policies should be assigned to these servers

### Options

- Create a security group that allows inbound NFS, HTTP, and HTTPS traffic from all IP addresses. Apply this group to all of the servers.
- Assign Elastic IPs to all of the instances and create a group that allows all traffic to pass between each of the five Elastic IP addresses and allow all inbound HTTPS traffic
- __Front-end web servers should allow HTTPS. Assign another group to all of the instances that allows all traffic to pass between instances using that group.__
- Create a security group that allows inbound HTTP and HTTPS traffic from all IP addresses and apply this to the web servers. Create a second security group for the NFS filestore that allows outbound NFS traffic to the private IP range of the front-end web servers.

### Correct Answer

Front-end web servers should allow HTTPS. Assign another group to all of the instances that allows all traffic to pass between instances using that group.

### Explanation



## Question 46

When an EC2 instance that is backed by an S3-based AMI Is terminated, what happens to the data on the root volume?

### Options

- Data is automatically saved as an EBS volume
- Data is unavailable until the instance is restarted
- Data is automatically saved as an EBS snapshot.
- __Data is automatically deleted__

### Correct Answer

Data is automatically deleted

### Explanation



## Question 47

An instance is launched into a VPC subnet with the network ACL configured to allow all inbound traffic and deny all outbound traffic. The instance’s security group is configured to allow SSH from any IP address and deny all outbound traffic. What changes need to be made to allow SSH access to the instance?

### Options

- The outbound security group needs to be modified to allow outbound traffic.
- __The outbound network ACL needs to be modified to allow outbound traffic.__
- Nothing, it can be accessed from any IP address using SSH.
- Both the outbound security group and outbound network ACL need to be modified to allow outbound traffic.

### Correct Answer

The outbound network ACL needs to be modified to allow outbound traffic.

### Explanation



## Question 48

Which of the following will provide the maximum IOPS for your EC2 ? (Choose 1 correct answer)

### Options

- EBS with SSD storage
- __Instance based SSD storage__
- Stripe data across Multiple EBS volumes with Raid 5
- EBS with provisioned IOPS
- Stripe data across Multiple EBS volumes with Raid 0

### Correct Answer

Instance based SSD storage

### Explanation



## Question 49

Instance A and instance B are running in two different subnets A and B of a VPC. Instance A is not able to ping instance B. What are two possible reasons for this? (Pick 2 correct answers)

### Options

- __The NACL on subnet B does not allow outbound ICMP traffic__
- The policy linked to the IAM role on instance A is not configured correctly
- __The security group attached to instance B does not allow inbound ICMP traffic__
- The routing table of subnet A has no target route to subnet B

### Correct Answer

The NACL on subnet B does not allow outbound ICMP traffic  
The security group attached to instance B does not allow inbound ICMP traffic

### Explanation



## Question 50

You manually launch a NAT AMI in a public subnet. The network is properly configured. Security groups and network access control lists are property configured. Instances in a private subnet can access the NAT. The NAT can access the Internet. However, private instances cannot access the Internet. What additional step is required to allow access from the private instances?

### Options

- Enable Source/Destination Check on the private Instances.
- __Disable Source/Destination Check on the NAT instance__
- Enable Source/Destination Check on the NAT instance.
- Disable Source/Destination Check on the private instances

### Correct Answer

Disable Source/Destination Check on the NAT instance

### Explanation

## Question 51

A user has created a VPC with CIDR 20.0.0.0/16 with only a private subnet and VPN connection using the VPC wizard. The user wants to connect to the instance in a private subnet over SSH. How should the user define the security rule for SSH?

### Options

- __Allow Inbound traffic on port 22 from the user’s network__
- The user can connect to a instance in a private subnet using the NAT instance
- The user has to create an instance in EC2 Classic with an elastic IP and configure the security group of a private subnet to allow SSH from that elastic IP
- Allow Inbound traffic on port 80 and 22 to allow the user to connect to a private subnet over the Internet

### Correct Answer

Allow Inbound traffic on port 22 from the user’s network

### Explanation



## Question 52

Your database is an RDS instance running SQL Server with Multi-AZ replication and you have several older .NET console utilities that perform database operations every 15 seconds. When the cluster has to switch the primary database server to the secondary AZ, the .NET utilities start to report connection failures to the database although other applications are able to access the database. How do you correct this problem?

### Options

- The server running the .NET utilities is caching the DNS lookup on the database cluster address. Flush the DNS cache of the server and force the C# utilities to open new connections to the database
- __The NET utilities need to change the SQL Server endpoint in the connection strings to read from the secondary database server using a try/catch__
- A.NET application will retain the IP address of a connection string until the host machine is rebooted.
- Use the RDS console to force a reboot of the database instance so that the primary server becomes the master server again.

### Correct Answer

The NET utilities need to change the SQL Server endpoint in the connection strings to read from the secondary database server using a try/catch

### Explanation



## Question 53

If you want to launch Amazon Elastic Compute Cloud (EC2) Instances and assign each Instance a predetermined private IP address you should:

### Options

- Use standard EC2 instances since each instance gets a private Domain Name Service (DNS) already
- __Launch the instances in the Amazon virtual Private Cloud (VPC)__
- Launch the instances in a Placement Group
- Launch the Instance from a private Amazon Machine image (AMI)
- Assign a group or sequential Elastic IP address to the instances

### Correct Answer

Launch the instances in the Amazon virtual Private Cloud (VPC)

### Explanation



## Question 54

After launching an instance that you intend to serve as a NAT (Network Address Translation) device in a public subnet you modify your route tables to have the NAT device be the target of internet bound traffic of your private subnet. When you try and make an outbound connection to the Internet from an instance in the private subnet, you are not successful. Which of the following steps could resolve the issue?

### Options

- Attaching a second Elastic Network interface (ENI) to the NAT instance, and placing it in the private subnet
- Attaching a second Elastic Network Interface (ENI) to the instance in the private subnet, and placing it in the public subnet
- __Disabling the Source/Destination Check attribute on the NAT instance__
- Attaching an Elastic IP address to the instance in the private subnet

### Correct Answer

Disabling the Source/Destination Check attribute on the NAT instance

### Explanation



## Question 55

Which of the following Auto scaling cannot perform ? (choose 2 correct answers)

### Options

- Start up EC2 instances when CPU utilization is above threshold
- Release EC2 instances when CPU utilization is below threshold
- __Add more Relational Database Service (RDS) read replicas when utilization is above threshold__
- __Increase the instance size when utilization is above threshold__

### Correct Answer

Add more Relational Database Service (RDS) read replicas when utilization is above threshold  
Increase the instance size when utilization is above threshold

### Explanation



## Question 56

You’re consulting for a new customer, who is attempting to create a hybrid network between AWS and their on-premise data centers. Currently, they have internal databases running on-premise that, due to licensing reasons, cannot be migrated to AWS. The front end of the application has been migrated to AWS and uses the DB hostname “”db.internalapp.local”” to communicate with the on-premise database servers. Hostnames provide an easy method for updating IP addresses in event of failover instead of having to update the IP address in the code. Given the current architecture what is the best way to configure internal DNS for this hybrid application? (Choose Two)

### Options

- Use an existing on-premise DNS server to configure hostnames for internal DNS records. Create a new Amazon VPC route table with the internal DNS server's IP addres
- Configure the database to have a public-facing IP address and use Route 53 to create a domain name
- __Use an existing on-premise DNS server to configure hostnames for internal DNS records. Create a new Amazon VPC DHCP Option Set with the internal DNS server's IP address.__
- __Create an EC2 instance DNS server to configure hostnames for internal DNS records, Create a new Amazon VPC DHCP option set with the internal DNS server's IP address.__

### Correct Answer

Use an existing on-premise DNS server to configure hostnames for internal DNS records. Create a new Amazon VPC DHCP Option Set with the internal DNS server's IP address.  
Create an EC2 instance DNS server to configure hostnames for internal DNS records, Create a new Amazon VPC DHCP option set with the internal DNS server's IP address.

### Explanation



## Question 57

A few weeks into your dream job with the large scientific institution, a group of EC2 instances that you set up in a Placement Group doesn’t seem to run as efficiently as you expected it to and seems to be suffering from low performance of packets, high latency and lots of jitter. Consequently, you have started to look at ways to fix this. Which of the following solutions would create enhanced networking capabilities on instances that would result in higher instances of packets per second, lower latency, and reduced jitter?

### Options

- Adding more instances to the Placement Group. Making sure you stop and restart all the other instances at the same time.
- Increasing the size of all the instances
- __Using Single Root I/O Virtualization (SR-IOV) on all the instances.__
- Splitting the instances across two Placement Groups in the same Availability Zone.

### Correct Answer

Using Single Root I/O Virtualization (SR-IOV) on all the instances.

### Explanation



## Question 58

Which feature can be used to respond to a sudden increase in web traffic?

### Options

- EC2 Auto Scaling groups
- AWS Shield Advanced
- __all of these answers__
- RDS Read Replicas

### Correct Answer

all of these answers

### Explanation



## Question 59

You are building infrastructure for a data warehousing solution and an extra request has come through that there will be a lot of business reporting queries running all the time and you are not sure if your current DB instance will be able to handle it. What would be the best solution for this?

### Options

- Database Snapshots
- Multi-AZ DB Instance deployment
- __Read Replicas__
- DB Parameter Groups

### Correct Answer

Read Replicas

### Explanation



## Question 60

A company has configured and peered two VPCs: VPC-1 and VPC-2. VPC-1 contains only private subnets, and VPC-2 contains only public subnets. The company uses a single AWS Direct Connect connection and private virtual interface to connect their on-premises network with VPC-1. Which two methods increase the fault tolerance of the connection to VPC-1? Choose 2 answers

### Options

- __Establish a hardware VPN over the internet between VPC-1 and the on-premises network__
- Establish a hardware VPN over the internet between VPC-2 and the on-premises network.
- Establish a new AWS Direct Connect connection and private virtual interface in a different AWS region than VPC-1
- __Establish a new AWS Direct Connect connection and private virtual interface in the same AWS region as VPC-1__
- Establish a new AWS Direct Connect connection and private virtual interface in the same region as VPC-2

### Correct Answer

Establish a hardware VPN over the internet between VPC-1 and the on-premises network  
Establish a new AWS Direct Connect connection and private virtual interface in the same AWS region as VPC-1

### Explanation

## Question 61

You created a new Linux EC2 instance and installed PostgreSQL but you are not able to establish a connection to the server from your local computer. What steps do you take to resolve this issue?

### Options

- Stop and start the instance. New security group rules will only take effect after a restart.
- __Verify that the assigned security groups allow traffic from your IP address to port 5432. Verify that PostgreSQL is configured to listen to external traffic and is bound to the public interface.__
- Make sure that you are using an Elastic IP and that it is included within the postgresql.conf configuration file.
- Create a security group rule that allows all traffic from 0.0.0.0/0. This will verify whether or not another rule is denying the traffic.

### Correct Answer

Verify that the assigned security groups allow traffic from your IP address to port 5432. Verify that PostgreSQL is configured to listen to external traffic and is bound to the public interface.

### Explanation



## Question 62

You have been given a new brief from your supervisor for a client who needs a web application set up on AWS. The most important requirement is that MySQL must be used as the database, and this database must not be hosted in the public cloud, but rather at the client’s data centre due to security risks. Which of the following solutions would be the best to assure that the client’s requirements are met?

### Options

- Build the application server on a public subnet and the database on a private subnet with a NAT instance between them
- Build the application server on a public subnet and build the database in a private subnet with a secure ssh connection to the private subnet from the client's data center.
- __Build the application server on a public subnet and the database at the client’s data centre. Connect them with a VPN connection which uses IPsec.__
- Use the public subnet for the application server and use RDS with a storage gateway to access and synchronize the data securely from the local data center

### Correct Answer

Build the application server on a public subnet and the database at the client’s data centre. Connect them with a VPN connection which uses IPsec.

### Explanation



## Question 63

You are building an automated transcription service in which Amazon EC2 worker instances process an uploaded audio file and generate a text file. You must store both of these files in the same durable storage until the text file is retrieved. You do not know what the storage capacity requirements are. Which storage option is both cost-efficient and scalable?

### Options

- A single Amazon Glacier vault
- __A single Amazon S3 bucket__
- Multiple instance stores
- Multiple Amazon EBS volume with snapshots

### Correct Answer

A single Amazon S3 bucket

### Explanation



## Question 64

What are characteristics of Amazon S3? Choose 2 answers

### Options

- S3 allows you to store objects of virtually unlimited size
- S3 should be used to host a relational database
- S3 offers Provisioned IOPS
- __S3 allows you to store virtually unlimited amounts of data__
- __Objects are directly accessible via a URL__

### Correct Answer

S3 allows you to store virtually unlimited amounts of data  
Objects are directly accessible via a URL

### Explanation

