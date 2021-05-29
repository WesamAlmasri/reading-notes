# Event Driven Applications

![Event Driven Applications](https://0701.static.prezi.com/preview/v2/dsuxmirmiupimiwt6o7joupwbl6jc3sachvcdoaizecfr3dnitcq_1_0.png)

## Review, Research, and Discussion

1. Why is access control important?

Access control is so important becuase it's a security technique that can be used to control who or what someone can view or use any given resource.
2. Describe an application that would need access control:

A blog application where and admin can read, write, update and delete any post or any typr of users, but a normal visitor can only read posts and can't comment.
3. What is a role used for?

A role is used to determine what type of capabilities a user has.
4. Why is role based access control more scalable than discretionary or mandatory access control?

The assignment of access rights in RBAC is very systematic and repeatable, easier to audit user rights (users are in only one of a few categories), and easier to correct any issues that are identified. There is no case by case assignment of roles, users fall into one of already pre-assigned roles/capabilities.

## Terms

- **Authorization**: Is the process of giving someone the ability to access a resource.
- **Role Based Access Control (RBAC)**: Is a method of restricting network access based on the roles of individual users within an enterprise.
- **Capabilities**: The functions that a user has access to. For example: (read, create, update, or delete)

## Event Driven Applications and Node js

**Event-Driven Programming** Is a logical pattern that we can choose to confine our programming within to avoid issues of complexity and collision.

### EventEmitter

Node.js natively provides us with a useful module called EventEmitter that allows us to get started incorporating Event-Driven Programming in our project right away.

We access the EventEmitter class through the events module. Once imported we’ll need to create a new object from the class to start using it.

```javascript
const EventEmitter = require('events').EventEmitter;
const myEventEmitter = new EventEmitter;
```

**Example**:

Imagine we’re creating a chat room. We want to alert everyone when a new user joins the chat room. We’ll need an event listener for a userJoined event. First, we’ll write a function that will act as our event listener, then we can use EventEmitters on method to set the listener.

```javascript
const EventEmitter = require('events').EventEmitter;
const chatRoomEvents = new EventEmitter;

function userJoined(username){
  // Assuming we already have a function to alert all users.
  alertAllUsers('User ' + username + ' has joined the chat.');
}

// Run the userJoined function when a 'userJoined' event is triggered.
chatRoomEvents.on('userJoined', userJoined);
```

The next step would be to make sure that our chat room triggers a userJoined event whenever someone logs in so that our event handler is called. EventEmitter has an emit method that we we use to trigger the event. We would want to trigger this event from within a login function inside of our chatroom module.

```javascript
function login(username){
  chatRoomEvents.emit('userJoined', username);
}
```

### Removing Listeners

To remove event listeners in EventEmitter we can use the `removeListener` or `removeAllListeners` method. It’s important to note that in the EventEmitter that comes built-in with Node you must pass a reference to the exact function you wish to remove when using the `removeListener` method.


```javascript
const EventEmitter = require('events').EventEmitter;
const chatRoomEvents = new EventEmitter;

function displayMessage(message){
  document.write(message);
}

function userJoined(username){
  chatRoomEvents.on('message', displayMessage);
}

chatRoomEvents.on('userJoined', userJoined);


// remove the listener
chatRoomEvents.removeListener('message', displayMessage);
```
