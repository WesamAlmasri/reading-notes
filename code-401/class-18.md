# AWS: API, Dynamo and Lambda

![AWS: API, Dynamo and Lambda](https://miro.medium.com/max/650/1*XuR8U6TOa5ar88lf2IbNNQ.png)

## Review, Research, and Discussion

1. What are serverless functions?

Serverless functions is small, discrete units of code that can be executed in the machine resources the provider allocated it on demand, taking care of the servers on behalf of their customers.
2. If you were to create a system that emulated Lambda functions, how would you do it?

I will use an event driven functions, for example in JavaScript I will use sockets to listen on some event and excutes its handler based on the event.
3. Describe how a CDN works.

CDNs store a cached version of your website content in multiple geographical locations around the world, which are known as “points of presence” (PoPs). These PoPs will contain their own caching servers and will be responsible for delivering that content in the user’s location.

## Terms

**Serverless Functions**: Programmatic function written by a software developer for a single purpose, which is then hosted and maintained on infrastructure by cloud computing companies that take care of code maintenance and execution so that developers can deploy new code faster and easier.

**Cloud Storage**: Cloud computing model that stores data on the internet through a cloud computing provider who manages and operates data storage as a service.

**CDN**: Content delivery network, a geographically distributed group of servers that work together to provide fast delivery of internet content.

## AWS API Gateway

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services. Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications. API Gateway supports containerized and serverless workloads, as well as web applications.

- Amazon API Gateway is a managed service that allows developers to define the HTTP endpoints of a REST API or a WebSocket API and connect those endpoints with the corresponding backend business logic
- Also handles authentication, access control, monitoring, and tracing of API requests
- API Gateway sits between the backend services of your API and your API’s users, handling the HTTP requests to your API endpoints and routing them to the correct backends
- It provides a set of tools that help you manage your API definitions and the mappings between endpoints and their respective backend services
- Can also generate API references from your definitions and make them available to your users as API documentation
- Integrates with many other AWS services, which allows for fully managed authentication and authorization layers as well as detailed metrics and tracing for API requests

## AWS DynamoDB

Amazon DynamoDB is a key-value and document database that delivers single-digit millisecond performance at any scale. It's a fully managed, multi-region, multi-active, durable database with built-in security, backup and restore, and in-memory caching for internet-scale applications.

- DynamoDB is a hosted NoSQL database offered by AWS
- It offers a reliable performance even as it scales, a managed experience so you don't need to be SSH-ing into servers, a small and simple API allowing for simple key-value access as well as more advanced query patterns
-Particularly good fit for:
  - Applications with large amounts of data and strict latency requirements
  - Serverless applications using AWS Lambda
  - Data sets with simple, known access patterns

## Dynamoose

Dynamoose is a modeling tool for Amazon's DynamoDB. Dynamoose is heavily inspired by Mongoose, which means if you are coming from Mongoose the syntax will be very familar.
