# AWS: S3 and Lambda

![AWS: S3 and Lambda](https://i.morioh.com/210329/907c47ba.webp)

## Review, Research, and Discussion

1. Describe “The Cloud”

**The Cloud** refers to servers that are accessed over the Internet, and the software and databases that run on those servers. Cloud servers are located in data centers all over the world. By using cloud computing, users and companies don't have to manage physical servers themselves or run software applications on their own machines.
2. What is a container (as it relates to computers and servers)?

A **Container** is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. ... Available for both Linux and Windows-based applications, containerized software will always run the same, regardless of the infrastructure.
3. What is auto-scaling?

**Auto-scaling**: is a method used in cloud computing that dynamically adjusts the amount of computational resources in a server farm - typically measured by the number of active servers - automatically based on the load on the farm.
4. What is bandwidth?

**Bandwidth** describes the maximum data transfer rate of a network or Internet connection. It measures how much data can be sent over a specific connection in a given amount of time. 
5. How do cloud providers compute service costs?

They start by calculating costs for network hardware, network infrastructure maintenance, and labor. These expenses are added together and then divided by the number of rack units a business will need for its IaaS cloud.

## Terms

**Server Instances**: An instance is a single copy of the software running on a single physical or virtual server.

**Containers**: Is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another.

**Cloud Services**: A wide range of services delivered on demand to companies and customers over the internet, these services are designed to provide easy, affordable access to applications and resources without the need for internal infrastructure or hardware.

**Cloud Architecture**: The way technology components combine to build a cloud, in which resources are pooled through virtualization technology and shared across a network

**AWS**: Amazon Web Services, a subsidiary of Amazon providing on-demand cloud computing platforms and APIs to individuals, companies, and governments on a metered pay-as-you-go basis

**EC2/Beanstalk vs Heroku**: Heroku and AWS Elastic Beanstalk, solutions (production configurations) is that they have comparable features and pricing. One big difference is that Heroku’s pricing takes exponential price jumps as one adds common additional features, e.g., auto-scaling, where-as AWS pricing is fairly linear. On the other hand, Heroku is generally simpler to get up and running as AWS has a fairly steep initial learning curve.

## AWS S3

Amazon S3 or Amazon Simple Storage Service is a service offered by Amazon Web Services that provides object storage through a web service interface. Amazon S3 uses the same scalable storage infrastructure that Amazon.com uses to run its global e-commerce network.

- Cloud object storage service that offers scalability, data availability, security and performance
- Capability to scale your storage resources up and down to meet fluctuating demands
- Stores data across the S3 storage classes which support different data access levels at corresponding rates
- Store your data in Amazon S3 and secure it from unauthorized access with encryption features and access management tools
- S3 is the only object storage service that allows you to block public access to all of your objects at the bucket or the account level
- S3 Access Points make it easy to manage data access with specific permissions for your applications using a shared data set
- Use cases: backup and restore, disaster recovery, archive, data lakes and big data analytics, hybrid cloud storage, cloud-native applications

## AWS Lambda

AWS Lambda is an event-driven, serverless computing platform provided by Amazon as a part of Amazon Web Services. It is a computing service that runs code in response to events and automatically manages the computing resources required by that code.

- WS Lambda is a serverless computing service provided by Amazon Web Services (AWS)
- The Lambda functions can perform any kind of computing task, from serving web pages and processing streams of data to calling APIs and integrating with other AWS services
- Each Lambda function runs in its own container
- When a function is created, Lambda packages it into a new container and then executes that container on a multi-tenant cluster of machines managed by AWS
- Before the functions start running, each function’s container is allocated its necessary RAM and CPU capacity
- Once the functions finish running, the RAM allocated at the beginning is multiplied by the amount of time the function spent running
- The customers then get charged based on the allocated memory and the amount of run time the function took to complete
- One of the distinctive architectural properties of AWS Lambda is that many instances of the same function, or of different functions from the same AWS account, can be executed concurrently
- Common use cases for Lambda: scalable APIs, data processing, task automation

## CDN

A **content delivery network**, or content distribution network, is a geographically distributed network of proxy servers and their data centers. The goal is to provide high availability and performance by distributing the service spatially relative to end users.

At its core, a CDN is a network of servers linked together with the goal of delivering content as quickly, cheaply, reliably, and securely as possible. In order to improve speed and connectivity, a CDN will place servers at the exchange points between different networks.

These Internet exchange points (IXPs) are the primary locations where different Internet providers connect in order to provide each other access to traffic originating on their different networks. By having a connection to these high speed and highly interconnected locations, a CDN provider is able to reduce costs and transit times in high speed data delivery.

Beyond placement of servers in IXPs, a CDN makes a number of optimizations on standard client/server data transfers. CDNs place Data Centers at strategic locations across the globe, enhance security, and are designed to survive various types of failures and Internet congestion.
