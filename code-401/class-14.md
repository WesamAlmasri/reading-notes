# Event Driven Architecture

![Event Driven Architecture](https://www.daitan.com/wp-content/uploads/2017/11/Event-Driven-Architectures-825x340.png)

## Review, Research, and Discussion

1. What’s the difference between a FIFO and a standard queue?

**FIFO** queues offer first-in-first-out delivery and exactly-once processing: the order in which messages are sent and received is strictly preserved.

**Standard queues** guarantee that a message is delivered at least once and duplicates can be introduced into the queue.
2. What classic design pattern is best represented by event driven programming?

The **observer pattern** is a software design pattern in which an object, named the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods.
3. How do you test an event driven system?

By triggering an event and assert the corrosponding response or output that should be.

## Terms

**FIFO**:  It's a method for organising the manipulation of a data structure where the oldest entry, or "head" of the queue, is processed first

**Pub/Sub**: It's the process of emit or listening to spesific event.

## AWS SNS and SQS

**Amazon Simple Queue Service (SQS)** and **Amazon SNS** are both messaging services within AWS, which provide different benefits for developers. Amazon SNS allows applications to send time-critical messages to multiple subscribers through a “push” mechanism, eliminating the need to periodically check or “poll” for updates.