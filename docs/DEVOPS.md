# DevOps
DevOps is a set a processes that enable an organization to produce reliable, scalable, and robust products. 

## Useful Metrics to track
The following metrics are good to track to assess the maturity of the DevOps practices at an organization. Ideally, there should be a 
dashboard tracking these metrics over time visible by all members of the organization. 

### Lead Time for changes
How long does it take from idea to production for a change? 

### MTTR
When a system is not performing as desired how long does it take for the organization to push changes to recover. 

### Frequency of releases
How often is the production environment updated? 


### Change failure Rate
What percentage of the changes pushed cause further issues? 

### Reliability 
This metric is broken down into:
- uptime: percentage of time over a given period that the services are available
- error rate: percentage of requests that result in an error (caught or uncaught) 
- latency: the time difference between the request and the response
- scalability: can the system gracefully handle (dramatic) changes in usage 


## Continuous Integration (CI)
A development process that automatically builds an artifact and runs a series of automated tests for every code commit in an effort to assess whether code
is ready to be deployed. This process provides quick, automated feedback to the developer, allowing them to operate with higher levels of confidence. 

## Continuous Delivery/Deployment (CD)
A development process where: 
1. Enables the team to deploy software to production or end users at any time
2. Ensures the software is in a deployable state throughout its lifecycle, including when working on new features
3. Establishes a fast feedback loop that enables the team to check the quality and deployability of the system, and prioritizes fixing issues blocking deployment.
