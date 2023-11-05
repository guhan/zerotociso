# Webhook
A webhook is a mechanism for one system to notify another system, typically over the internet, about events or updates in real-time. It allows data to be transmitted immediately when specific events occur, instead of relying on a system to periodically check for updates. Webhooks are commonly used in web development, APIs (Application Programming Interfaces), and integrations between different software applications. Here are the key features of webhooks

![Webhook](/images/WEBHOOK.png)

## Event-Driven
Webhooks are triggered by specific events or conditions, such as a new email arriving in an inbox, a payment being processed, a user registering on a website, or a file being uploaded to a server.
## Real-Time
When an event occurs, the system generating the event (the "sender") sends an HTTP POST request to a predefined URL (endpoint) on the system that needs to receive the data (the "receiver"). This ensures that the receiver is immediately informed about the event.
## Push, Not Pull
Unlike traditional polling mechanisms where a system periodically checks for updates (pulling), webhooks "push" data to the receiving system when there's something to report.
## HTTP/HTTPS
Webhooks typically use the HTTP or HTTPS protocol for communication, making them easy to implement and secure. The receiving system must have a publicly accessible endpoint (URL) to receive the webhook payload.
## Payload
The data sent in a webhook request is known as the "payload" and usually includes information about the event, such as the event type, relevant data, and any necessary metadata.
## Two-Way Communication
While webhooks are primarily a one-way communication mechanism from sender to receiver, they can also be part of a broader two-way communication system where the receiver can acknowledge or respond to the sender based on the information received.
