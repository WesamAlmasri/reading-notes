# Message Queues

![Message Queues](https://www.cloudamqp.com/img/blog/thumb-mq.jpg)

## Review, Research, and Discussion

1. What does it mean that web sockets are bidirectional? Why is this useful?

It means that the data flows in both ways (full-duplex), a web socket can both send and receive which is useful because it allows data to be sent and received on the same channel.
2. Does socket.io use HTTP? Why?

Yes, it use HTTP. Socket.io will try to establish a WebSocket if possible but if it cannot it will fall back on HTTP.
3. What happens when a client emits an event?

The event will be sent to the server, which will be listening for the event if already connected and run a handler for the event received.
4. What happens when a server emits an event?

Wheneer server is emitting an event it will be send to all client's socket connected and litene to it.
5. What happens if a client “misses” an event?

The socket that miss an event won't recognise it later and it will be ignored.
6. How can we mitigate this?

To avoid missing an event by caching the events on the server and when the client recive the event it will emit an event to the server, so that the server will awknowladge the client got the message and the server will remove the event from the chach. And every time the client start a connection with the server he will emit an event to get the events that he missed.

## Terms

- **Socket**: One endpoint of a two-way communication link between two programs running on the network, a socket is bound to a port number so that the TCP layer can identify the application that data is destined to be sent to.
- **Web Socket**: Communication protocol that provides a full-duplex and low-latency channel between the server and the browser.
- **Socket.io**: It is a library that enables real-time, bidirectional, and event-based communication between the browser and the server, consists of a Node.js server and a javascript client library for the browser.
- **Client**: It is a program separate from the server that initiates requests for services or info from the server
- **Server**: The part which provide function, info, or service back to the client, acts as the main hub for communication
- **OSI Model**: Open systems interconnection model is a model that characterizes and standardizes the communication functions of a telecommunication or computing system without regard to its underlying internal structure and technology
- **TCP Model**: Transmission control protocol, essentially a concise version of the OSI model
- **TCP**: Transmission control protocol, one of the main protocols of the internet protocol suite
- **UDP**: User datagram protocol, connectionless protocol so there is no need to establish a connection prior to data transfer
- **Packets**: It is a formatted unit of data carried by a packet-switched network, packet consists of control information and user data/payload

## Socket.io Rooms and Namespaces

A room is an arbitrary channel that sockets can `join` and `leave`. It can be used to broadcast events to a subset of clients:

![socket.io rooms](https://socket.io/images/rooms.png)

Rooms are a **server-only** concept (i.e. the client does not have access to the list of rooms it has joined).

### Joining and leaving

You can call `join` to subscribe the socket to a given channel:

```js
io.on('connection', socket => {
  socket.join('some room');
});
```

And then simply use `to` or `in` (they are the same) when broadcasting or emitting:

```js
io.to('some room').emit('some event');
```

### Default room

Each `Socket` in Socket.IO is identified by a random, unguessable, unique identifier Socket#id. For your convenience, each socket automatically joins a room identified by its own id.

## Namespaces

A Namespace is a communication channel that allows you to split the logic of your application over a single shared connection (also called “multiplexing”).

![Namespace diagram](https://socket.io/images/namespaces.png)

Each namespace has its own:

1. event handlers
2. rooms
3. middlewares
