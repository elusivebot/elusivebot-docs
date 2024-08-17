# ElusiveBot

## Overview

### Goal

ElusiveBot is AI agent framework:

- Agonistic of communication service; i.e. supports direct HTTP or TCP messages and richer Discord channels.
- Stores a persistent state of known text channels.
- Supports any number of behaviors
  - Triggered by events, whether internally generated (i.e. timers) or external (text message received)
  - Return zero or more possible actions for the agent to perform
- Selects zero or one actions to perform

It is intended to support both simple behaviors, such as regex
matching, and a platform for developing more complex ML models.

As this is a modern web backend application, it will be decomposed
into smaller services written in any programming language.

## High Level Architecture

<figure markdown>
  [Architecture diagram](imgs/diagrams/architecture.png)
  <figcaption>Architecture</figcaption>
</figure>

## Subsystems

### Edge

Services handling input and output out of ElusiveBot.  Translates service
specific data and events to generic messages for the data layer on
input. Responsible for converting generic ElusiveBot actions into the
service specific events.

- [Edge](edge/)

### State

Processes and stores the persistent state of ElusiveBot, including
message log for any channels, and the state of known external users.

- [State](state/)

### Behavior

Services woken by changes to the persistent state, such as incoming
messages, and propose zero or more actions ElusiveBot may take in
response.

- [Behavior](behavior/)

### Execution

Selects which, if any, proposed actions and performs them, involving
persistent changes to the world.

- [Execution](execution/)
