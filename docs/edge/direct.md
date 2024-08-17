# Direct

The **direct service** is a simple TCP service for developers to
easily send text messages to ElusiveBot and receive responses.

## Goal

As a *developer*, I want a simple service that lets me simulate
sending and receiving messages as in a chatroom.

## Architecture

This will be a simple Kotlin coroutines driven message passing
service.  Connect to the Kafka broker, listen for TCP connections,
create sending and receiving queues, pass newline messages to
ElusiveBot, and forward responses to the client.

<figure markdown>
  ![Sequence diagram](../imgs/diagrams/edge/direct/sequence.png)
  <figcaption>Sequence diagram</figcaption>
</figure>
<figure markdown>
  ![Architecture diagram](../imgs/diagrams/edge/direct/architecture.png)
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

Instead of sending and receiving raw text, delimited by newlines, the
service could receive formatted data, likely JSON.  This would allow
metadata to be transmitted, but increase the complexity of the service.

Given it's not immediately useful, revisit if the need arises down the road.

### Higher level protocols

ElusiveBot might need a websocket or a message queue equivalent.
This will be incorporated into a production service, rather than a
simple developer tool.

### UDP

TCP makes things simpler, in particular that this service does
care about ordering and reliability, which would need to be implemented
to use UDP.

## Appendix

- [Ktor raw sockets](https://ktor.io/docs/servers-raw-sockets.html)
- [GitHub](https://github.com/elusivebot/elusivebot-direct)
