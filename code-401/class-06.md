# Authentication

![Authentication](https://www.cisco.com/c/en/us/products/security/identity-services-engine/what-is-user-authentication-policy/jcr:content/Grid/subcategory_atl_d1dc/layout-subcategory-atl/anchor_info_6e7e.img.png/1612244099055.png)

## Review, Research, and Discussion

**“Singleton” is (in Computer Science terms)**:

- It is a design pattern that ensures that a class has only one instance.
- It provides global access to that single instance.
- Because it globally accessed, many programmers recommends not to use it.

**How the Singleton pattern can be used with Node modules, specifically with classes**:

- Singleton is used by creating a ES6 class.
- a private constructor of the class
- static method would have access to the private constructor.
- the static method would create an instance of the class if not exists (getInstance()) or call the instance in created before.

**If I was tasked with building a middleware system like Express uses, the approach I might  take to construct/operate it**:

- Define what layers I want to middle in (eg. request and response).
- Allow the middleware to have access to both layers.
- Allow the middleware to end the process (eg. the request) or move to the next middleware or callback function.

## Vocabulary Terms

**Router Middleware**: Are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle and responsible of handlding the process in certial route envoked by the client,

**Dynamic Module Loading**: It is loading the module at run time into memory, getting needed data and executing needed functionality, then unloading it.

**Singleton Pattern**: A design pattern used to create one instance of a class with global access.

**Mock Testing**: Its an approach to unit testing that lets you make assertions about how the code under test is interacting with other system modules.

**CRUD -> REST Method Matches**:

![crud rest method](https://camo.githubusercontent.com/b5f7bde8ed7b416534f7acc28628548547256df3c2e53136be7f37f2571c043f/68747470733a2f2f7777772e65647572656b612e636f2f626c6f672f77702d636f6e74656e742f75706c6f6164732f323031392f30362f435255442d4f7065726174696f6e732d576861742d69732d524553542d4150492d45647572656b612d312e706e67)

## Securing Passwords

- Passwords are the first defense line. For that, they must be crypt before saved in the database.
- Hash algorithms help with securing the data. although it is not reversible it can be hacked.
- **Brute Force attack**: While the hacker can only get hashed data. he can get the data by trying many passwords until he found one that generate the same hash pattern as the hacked password.
- **Hash Collision attack**: Collision is when two different input generate the same output. That is the result of having unlimited input length and predefined output length. The hacker can have the first input and try to guess the second one using the brute force attack.
- Adding salt can help more in protection.

## Basic Auth

**Authentication** is the process of verifying that an individual, entity or website is whom it claims to be. Authentication in the context of web applications is commonly performed by submitting a username or ID and one or more items of private information that only a given user should know.

**Basic access authentication** is a method for an HTTP user agent (e.g. a web browser) to provide a user name and password when making a request.

In basic HTTP authentication, a request contains a header field in the form of `Authorization: Basic <credentials>`, where credentials is the *Base64* encoding of ID and password joined by a single colon `:`.

The **basic HTTP authentication (BA)** mechanism does not provide confidentiality protection for the transmitted credentials. They are merely encoded with Base64 in transit and not encrypted or hashed in any way. Therefore, basic authentication is typically used in conjunction with HTTPS to provide confidentiality.
