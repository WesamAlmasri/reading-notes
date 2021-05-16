# Class 02 Express

## What’s the difference between PUT and PATCH?

**PUT** is a method of modifying resource where the client sends data that updates the entire resource. It is used to set an entity’s information completely. PUT is similar to POST in that it can create resources, but it does so when there is a defined URI. PUT overwrites the entire entity if it already exists, and creates a new resource if it doesn’t exist.

**PATCH** applies a partial update to the resource. This means that you are only required to send the data that you want to update, and it won’t affect or change anything else. So if you want to update the first name on a database, you will only be required to send the first parameter; the first name.

## Services or tools that allow you to “mock” an API for development

1. [Nock](https://github.com/nock/nock) 
2. [MockServer](http://www.mock-server.com/)
3. [Beeceptor](https://beeceptor.com/)

## SOAP and ReST

**SOAP** is a protocol which was designed before REST and came into the picture. The main idea behind designing SOAP was to ensure that programs built on different platforms and programming languages could exchange data in an easy manner. *SOAP stands for Simple Object Access Protocol*.

**REST** was designed specifically for working with components such as media components, files, or even objects on a particular hardware device. Any web service that is defined on the principles of REST can be called a RestFul web service. A Restful service would use the normal HTTP verbs of GET, POST, PUT and DELETE for working with the required components. *REST stands for Representational State Transfer.*

## Terms

**Web Server**: Is a computer that runs websites. It’s a computer program that distributes web pages as they are requisitioned. The basic objective of the web server is to store, process and deliver web pages to the users. This intercommunication is done using Hypertext Transfer Protocol (HTTP).

**Express**: it’s a node js framework, used for deveoloping backend web app and APIs

**Routes**: Is a mechanism where HTTP requests are routed to the code that handles them. To put simply, in the Router you determine what should happen when a user visits a certain page.

**WRRC**: The request/response cycle traces how a user’s request flows through the app.
