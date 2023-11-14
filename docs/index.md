# ElusiveBot

## Overview

### Goal

ElusiveBot is AI agent framework:

- Agonistic of communication service; i.e. supports direct HTTP or TCP messages and richer Discord channels.
- Supports any number of behaviors
  - Triggered by events, whether internally generated (i.e. timers) or external (text message received)
  - Return zero or more possible actions for the agent to perform
- Selects one or no actions to perform

It is intended to support both simple behaviors, such as regex
matching, and a platform for developing more complex ML models.

As this is a modern web backend application, it will be decomposed
into smaller services written in any programming language.

## Architecture

<figure markdown>
  [![Architecture diagram](imgs/diagrams/architecture.png)](design.md)
  <figcaption>Architecture</figcaption>
</figure>

## Components

- [Direct service](direct/index.md)
- [HTTP service](http/index.md)
