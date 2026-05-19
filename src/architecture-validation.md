# Architecture validation

## Models
* Sequence diagram
* Context diagram
* Component diagram (showing links and/or hierachy)

## Diagram link checking
 * Security
   * What data encryption is used? ie. HTTPS/TLS
   * What cyper suites are used?
   * What certificate checks are in place?  Standard TLS or mTLS?
 * Authentication/Authorization
   * How can we verify requests have come from specific sender ie. webhooks using secrets and HMAC; or Bearer tokens
 * Protocol
   * What protocol is used? ie. HTTP/RPC/REST/GraphQL
   * What is the schema/structure of the payloads?
   * Is it synchronous or asynchronous?
   * Time for a response to be sent back
 * Reliency
   * What happens if the sender fails to send the request?
   * What happens if the receiver fails when processing the request? ie. think about retries from the sender
   * What happens if the sender does not receieve the response from the reciever
 * Technology
   * Are there any frameworks/user flows that this link requires ie. browser based flow?
   * How does the receiver deal with multiple requests containing the same data or operation? ie. idempotency
