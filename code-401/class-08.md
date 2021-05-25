# Access Control (ACL)

![acl](http://www.network-packet.com/photo/pl26448217-acl_access_control_list_functionality_in_npb_dynamic_packet_filter.jpg)

## Review, Research, and Discussion

1. When is Basic Authorization used vs. Bearer Authorization?:
   - **Basic Authorization** is used when the user first time wants to login with username and password.
   - **Bearer Authorization** is used on every request using a token in the header send by the client after the user login in first time with usernam and password.

2. What does the JSON Web Token package do?
   - Create and verify JWTs, a compact and self-contained way for securely transmitting information between parties as a JSON object.

3. What considerations should we make when creating and storing a SECRET?
   - Should be kept protected, best kept in a system enviroment variable not in plain text files.

## Terms

- **Encryption**: It is a method by which information is converted into secret code that hides the information's true meaning.
- **Token**: Is a cryptic string used to authenticate a the user who is trying to get sources from the server.
- **Bearer**: It's some type of authentication that used a token to verify a user on each request.
- **Secret**: A secret string stored on the server used to sign and encode the token to verify the token is made by the server and it's not changed by ony one else.
- **JSON Web Token**: Is a proposed Internet standard for creating data with optional signature and/or optional encryption whose payload holds JSON that asserts some number of claims.

## Role-Based Access Control (RBAC)

**RBAC** is the idea of assigning system access to users based on their role in an organization.

### Benefits of RBAC?

- The assignment of access rights becomes systematic and repeatable.
- It is much easier to audit user rights, and to correct any issues identified.

### RBAC implementation 

1. Inventory your systems
2. Analyze your workforce and create roles
3. Assign people to roles
4. Never make one-off changes
5. Audit
