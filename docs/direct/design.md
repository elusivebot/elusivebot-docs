# Design Document

## Overview

As a *developer*, I want a simple service that lets me simulate
sending and receiving messages as in a chatroom.

## Architecture

This will be a simple Kotlin coroutines driven message passing
service.  Connect to the Redis server, listen for TCP connections,
create sending and receiving queues, pass newline messages to
ElusiveBot, and forward responses to the client.

<figure markdown>
  ![Sequence diagram](/imgs/diagrams/direct/sequence.png)
  <figcaption>Sequence diagram</figcaption>
</figure>
<figure markdown>
  ![Architecture diagram](/imgs/diagrams/direct/architecture.png)
  <figcaption>Architecture</figcaption>
</figure>

## Requirements

### Functional

- Opens a network socket that sends and receives text messages.
- Listen on localhost and a reasonable default port, with options
  to override.

### Non-Functional

- Interact with the rest of the ElusiveBot architecture the same
  as a real endpoint.

## Alternatives

### JSON messages

This would allow the service to pass metadata and non text events,
which might be desired in the future.  However, it would complicate
interacting with the service and is not immediately necessary to
fufill the requirements.

### Higher level protocols

ElusiveBot might need a WebSocket or a message queue equivalent.
This will be incorporated into a production service, rather than a
simple developer tool.

### UDP

TCP makes things simplier, in particular that this service does
care about ordering and reliability, which would need to be implemented
to use UDP.

## Appendix

- [Ktor raw sockets](https://ktor.io/docs/servers-raw-sockets.html)
