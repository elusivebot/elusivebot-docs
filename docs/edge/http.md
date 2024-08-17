# HTTP

The **HTTP service** is a simple Javascript frontend and REST + websocket
backend for interacting with the service through a web browser without
any live components such as Discord.

## Goal

As a *developer*, I want a simple website that lets me interact with
ElusiveBot locally without any public access for development and testing.

## Architecture

<figure markdown>
  ![Architecture diagram](../imgs/diagrams/edge/http/architecture.png)
  <figcaption>Architecture</figcaption>
</figure>

## Requirements

- Must be written using TypeScript.  JSON schema can generate bindings in Java, Kotlin, or TypeScript as of this writing.
- Must serve static Javascript/HTML UI.  Likely in Angular.

## Alternatives

## Appendix

- [GitHub backend](https://github.com/elusivebot/elusivebot-http)
- [GitHub frontend](https://github.com/elusivebot/elusivebot-frontend)
