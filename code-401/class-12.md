# Socket.io

![socket.io](https://miro.medium.com/max/1624/0*xAADmPJN52Yy6XJV.jpg)

## Review, Research, and Discussion

1. What is the benefit of transforming data into packets?

It allows data to be transferred fast and efficiently over the network and to minimizes the transmission latency
2. UDP is often refereed to as a connectionless protocol. Why is this?

Because it's helps to make the connection between to parts before the data transmission
3. Can a socket server application have multiple socket connections?

Yes a socket server may have multiple socket connection.
4. Can a socket connection application be connected to multiple socket servers?

No, a single client-side server should only connect to one socket server.
5. Can an application be both a socket server and a socket connection?

Yes an application can be both a socket server and a socket connection

## Terms

- **Observer Pattern**: Is a software design pattern in which an object, named the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods.
- **Listener**: It is a function that listens for an event to occur.
- **Event Handler**: Is a function that runs when a specific event fires.
- **Event-Driven Programming**: Pogramming paradigm in which the flow of the program is determined by events such as user actions, message passing.
- **Event Loop**: Responsible for executing the code, collecting and processing events, and executing queued sub-tasks
- **Event Queue**: A queue where events from an application are held prior to being processed by a receiving program or system
- **Call Stack**: A Stack for an interpreter to store and track of its place in a script that calls multiple functions - what function is currently being run and what functions are called from within that function.
- **Emit/Raise/Trigger**: In event-driven programming, emit sends a message to trigger a response and raise an event
- **Subscribe**: Listening to an event to take place.
- **Database**: An organized collection of data, generally stored and accessed electronically from a computer system.

## WebSocket

**The WebSocket API**: is an advanced technology that makes it possible to open a two-way interactive communication session between the user's browser and a server. With this API, you can send messages to a server and receive event-driven responses without having to poll the server for a reply.

WebSocket handshake uses the HTTP Upgrade header to change from the HTTP protocol to the WebSocket protocol and enables interaction between a web browser (or other client application) and a web server with lower overhead than half-duplex alternatives such as HTTP polling, facilitating real-time data transfer from and to the server.

WebSocket can be done by providing a standardized way for the server to send content to the client without being first requested by the client, and allowing messages to be passed back and forth while keeping the connection open.

## Socket io

**Socket.IO** is a JavaScript library for realtime web applications. It enables realtime, bi-directional communication between web clients and servers. It has two parts: a client-side library that runs in the browser, and a server-side library for Node.js. Both components have a nearly identical API.

## Socket.io vs. Web Sockets

- **WebSocket** is the communication protocol that provides bidirectional communication between the client and the server over a TCP connection.
- WebSocket remains open all the time so they allow the real-time data transfer
- When clients trigger the request to the server it does not close the connection, it persists and waits for the client or server to terminate the request
- **Socket.io** is a library that enables real-time and full-duplex communication between the client and the web servers
- Uses the WebSocket protocol to provide the interface
- Divided into two parts, both WebSocket vs Socket.io are event-driven libraries:
  - client-side: a library that runs inside the browser
  - server-side: library for Node.js
