# Design

## Overview

**So it's all quite simple you see....**

## Architecture

<figure markdown>
  ![Architecture diagram](imgs/diagrams/architecture.png)
  <figcaption>Architecture</figcaption>
</figure>

### Edge

Receives messaging service specific events from the cloud.  Messaging services include Discord, but also generic HTTP and TCP endpoints.

These events are converted to generic update events and passed to the processing layer.

### Processing

Processes update events and modifies the user and message
state.  Produces a snapshot of the channel state and passes to the
behavior layer.

### Behavior

Passes channel state snapshot to behavior functions, and compiles a list
of proposed actions for the executor layer.


### Executor

Selects which actions to perform.  Pushes tangible actions to
corresponding ednpoint services in the Edge layer.

