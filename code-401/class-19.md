# AWS: Events

![AWS: Events](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2018/11/15/SNS-AWS-KMS.png)

## Review, Research, and Discussion

- Describe the similarities between AWS API Gateway + Lambda functions and an ExpressJS Server

The similarities is that a request from the user will be received at specefic end point and method then a handler will be excecuted depend on the end point.

- List the AWS Database offerings and talk about the pros and cons of each

Aws offering two type of database such as :

1. Amazon RDS: Managed Relational Database Service for MySQL, PostgreSQL, MariaDB, Oracle BYOL, or SQL Server and can't be integrated with lambda function in aws. 
2. Amazon DynamoDB: Fast and flexible NoSQL database with seamless scalability and can be integrated with lambda function in aws. .

- What’s the difference between a FIFO and a standard queue?

FIFO queues have essentially the same features as standard queues, but provide the added benefits of supporting ordering and exactly-once processing and ensure the order in which messages are sent and received is strictly preserved

- How can the server be assured a message was properly received?

By having the client emit a "received" event back to the server upon receipt of the message

## Terms

**Serverless API**: Using API Gateway you can create RESTful APIs that enable real-time two-way communication applications, API Gateway supports containerized and serverless workloads as well as web applications without having your own server.

**Triggers**: Some event that make other functinality run, like AWS Lambda resource or resource in another service that you configure to invoke your function in response to lifecycle events, external requests or on a schedule, a function can have multiple triggers.

**Dynamo vs Mongo**:

- Mongo can be deployed anywhere, Dynamo is only available on AWS
- Mongo is JSON based document store, Dynamo is limited key-value store with JSON support
- Mongo is rich query language, Dynamo is key-value queries

**Dynamoose vs Mongoose**: Dynamoose is a DynamoDB API structured like Mongoose, lets us provide a schema and perform CRUD operations against a DynamoDB table, installed via node and configured based on role

## SQS (Simple Queue Service)

Amazon Simple Queue Service (SQS) is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. SQS eliminates the complexity and overhead associated with managing and operating message oriented middleware, and empowers developers to focus on differentiating work. Using SQS, you can send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available. 

SQS offers two types of message queues. Standard queues offer maximum throughput, best-effort ordering, and at-least-once delivery. SQS FIFO queues are designed to guarantee that messages are processed exactly once, in the exact order that they are sent.

## SNS (Simple Notification Service)

Amazon Simple Notification Service (Amazon SNS) is a fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication.

The A2A pub/sub functionality provides topics for high-throughput, push-based, many-to-many messaging between distributed systems, microservices, and event-driven serverless applications. Using Amazon SNS topics, your publisher systems can fanout messages to a large number of subscriber systems including Amazon SQS queues, AWS Lambda functions and HTTPS endpoints, for parallel processing, and Amazon Kinesis Data Firehose. The A2P functionality enables you to send messages to users at scale via SMS, mobile push, and email.
