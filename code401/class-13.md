# Class 13 - Message Queues

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- What does it mean that web sockets are bidirectional? This allows communication in a duplex manner.

- Why is this useful?

- Does socket.io use HTTP? For the initial connection.

- What happens when a client emits an event?

- What happens when a server emits an event?

- What happens if a client “misses” an event? They miss them.

- How can we mitigate this? Set up a database and have them stored to wait until the client logs on to show up for the client when the log on.

## Additional Resources

- [Get started](https://socket.io/get-started/chat/)

- [Rooms](https://socket.io/docs/v4/rooms/)

- [Namespaces](https://socket.io/docs/v4/namespaces/)

- [Emit Cheatsheet](https://socket.io/docs/v4/emit-cheatsheet/)

## Videos

## Vocab

- Socket is the connection between the server and the client.
- Web Socket is the protocol that provides full-duplex channel between the server and browser.
- Socket.io is the library and does bidirectional event based communication between server and browser.
- Client
- Server
- OSI Model has 7 layers, Physical, Data Link, Network, Transport, Session, Presentation and Application. Devs normally live in App layer.
- TCP Model has 4 layers, Network Interface (1st two of OSI), Network, Transport and Application (5th-7th of OSI). 
- TCP transmission control protocol uses syn and ack messages to form 3 way handshake to ensure all data is received, in order.  
- UDP user datagram protocol promises speed over loss tolerance. Sends packets of data without acknowledging connection, which could result in data loss, but gets data sent more quickly.
- Packets have the header (destination and origin information) and payload of data that is sent of the internet. 

## Bookmark/Skim

- Which 3 things had you heard about previously and now have better clarity on?
- Which 3 things are you hoping to learn more about in the upcoming lecture/demo?
- What are you most excited about trying to implement or see how it works?

## Things I Want To Know More About

- Class notes

- Need to do the LAB!!
- And the previous one so I can catch up with these lectures!!

- Message Queues

- Event Driven

- Bi-directional connects through the hub

- Benefits of Micro Architechture 
  - Triggers other code systems in other languages
  - Simplifies code base

- Socket.io rooms
- How does information get passed to rooms?
- Broadcasting to rooms
