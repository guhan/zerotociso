# DevOps
DevOps is a set a processes that enable an organization to produce reliable, scalable, and robust products. 


## DORA
DevOps Research and Assessment (DORA) has conducted extensive research to identify key principles and practices that contribute to high-performing software delivery and operational excellence. The research conducted by DORA is aimed at helping organizations improve their DevOps practices and achieve better outcomes in terms of software delivery speed, stability, and quality.

Here are some of the key principles and practices identified by DORA:

- Continuous Delivery: Implementing practices that enable the continuous and automated delivery of software changes into production or other environments. This involves automated testing, deployment pipelines, and a focus on reducing lead times.
- Automation: Automating manual and repetitive tasks in the software development and deployment process. This includes automated testing, infrastructure provisioning, and deployment processes.
- Monitoring and Observability: Establishing comprehensive monitoring and observability practices to gain insights into the performance and behavior of applications and infrastructure. This enables proactive issue detection and resolution.
- Version Control: Using version control systems (e.g., Git) to manage and track changes to source code and other artifacts. Version control helps ensure collaboration, traceability, and repeatability.
- Lean Management: Applying principles from Lean manufacturing to software development, focusing on eliminating waste, optimizing processes, and fostering a culture of continuous improvement.
- Cultural Transformation: Promoting a culture of collaboration, trust, and shared responsibility between development and operations teams. This involves breaking down silos and fostering a "you build it, you run it" mentality.
- Feedback Loops: Establishing feedback loops at all stages of the software development lifecycle. This includes feedback from testing, monitoring, and end-users to drive continuous improvement.
- Small and Frequent Changes: Embracing the practice of making small, incremental changes to software and infrastructure, which reduces the risk of failures and enables faster recovery.
- Risk Management: Integrating risk management practices into the software development process to identify potential issues early and mitigate risks before they impact production.
- Continuous Improvement: Committing to ongoing learning, experimentation, and refinement of processes. Encouraging teams to learn from failures and successes to drive continuous improvement.


They publish a [State of DevOps report](https://dora.dev/publications/) which is useful to understand trends in DevOps


## SPACE Framework
The SPACE framework was introduced by Nicole Forsgren, Jez Humble, and Gene Kim in their book "Accelerate: The Science of Lean Software and DevOps." The framework outlines five key dimensions that organizations should focus on to achieve high-performing DevOps practices and outcomes.

Here's what each letter in the SPACE acronym stands for:

- **S**
Sharing: Encouraging collaboration, communication, and knowledge sharing among teams. This involves breaking down silos and fostering a culture of cooperation.
- **P**
Process and Practice: Establishing efficient and well-defined processes and practices for software development, testing, deployment, and operations. This includes implementing continuous integration, continuous delivery, and other DevOps practices.
- **A**
Automation: Automating manual and repetitive tasks to reduce errors, increase efficiency, and accelerate the software delivery pipeline.
- **C**
Cultural: Cultivating a culture of trust, respect, and innovation. This involves aligning teams, promoting a growth mindset, and embracing change.
- **E**
Evidence: Using data-driven decision-making and performance metrics to measure and optimize the DevOps process. Collecting and analyzing relevant data helps identify areas for improvement.


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
