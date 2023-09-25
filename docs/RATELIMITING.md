# Rate Limiting
Rate limiting is a technique used to control the number of requests or actions that a user or system can perform within a specified time period. It's commonly used to prevent abuse, protect resources, and ensure fair usage of a service or system. 
## Token Bucket Algorithm
This algorithm allows a user or system to perform actions as long as there are tokens available in a "bucket." Tokens are added to the bucket at a fixed rate. When an action is performed, a token is consumed. If there are no tokens available, the action is delayed or denied. This algorithm is often used for smooth rate limiting.
## Leaky Bucket Algorithm
Similar to the token bucket, the leaky bucket algorithm limits the rate at which requests are processed. Requests are added to the "bucket," and if the bucket overflows, requests are either delayed or discarded.
## Fixed Window Rate Limiting
In this approach, the rate limit is based on a fixed window of time, such as one minute. Users or systems can perform a certain number of actions within that fixed window. Once the limit is reached, additional actions are denied until the window resets.
## Sliding Window Rate Limiting
Unlike fixed window rate limiting, sliding window rate limiting tracks usage within a rolling time window. For example, if you have a limit of 100 requests per minute, the sliding window keeps track of the requests made over the last minute. This allows for a more fine-grained control of rate limiting.
## Token-Based Rate Limiting
In this method, users or systems are issued a certain number of tokens, and each request consumes a token. When the tokens are exhausted, users must wait until tokens are replenished according to the rate limit rules.
## Distributed Rate Limiting
In distributed systems, rate limiting may be applied at various levels, such as at the edge (e.g., load balancer), within microservices, or at the database level. These distributed rate limits help protect different parts of the system from being overwhelmed.
## Adaptive Rate Limiting
This approach adjusts rate limits dynamically based on system conditions or user behavior. For example, if a service is experiencing high load, the rate limit may be temporarily lowered to ensure stability.
## User-Based Rate Limiting
Instead of limiting based on the number of requests, this approach limits actions based on individual users. Each user is assigned a rate limit, and their actions are tracked independently.
## IP Address-Based Rate Limiting
Rate limiting can also be applied based on the IP address of the requester. This is often used to protect against denial-of-service (DoS) attacks.
## Geographical Rate Limiting
Limiting access to resources based on the geographical location of the user or system can be useful in some scenarios, such as content distribution.
## Role-Based Rate Limiting
Rate limiting can be tailored to specific user roles or permissions within an application. For example, administrators may have a higher rate limit than regular users.
