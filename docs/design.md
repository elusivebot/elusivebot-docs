# Design

## Overview

**So it's all quite simple you see....**

* Events come the web to their corresponding endpoint/handler service.
* Messages are passed to message processing function, which preprocesses
  and applies any comprehension (tbd).
* User state and message logs are updated by the handler.
* A channel update event is queued.
* Behavior fanout receives channel update, creates snapshot of channel
  and sends to behavior services.
* Behavior services send a list of possible actions to decision service.
* Decision service evalutes and picks one (or no) to execute.
* Chosen action is forwarded to the executor fanout, which forwards to
  the corresponding executor services.
* Executor service modifies Redis tables, enqueues responses for
  endpoint/handler.

## Architecture

<figure markdown>
  ![Architecture diagram](imgs/diagrams/architecture.png)
  <figcaption>Architecture</figcaption>
</figure>

## Requirements

### Functional

### Non-Functional

## Appendix
