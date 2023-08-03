# Architecture


## Monolith
A "monolith" refers to a single, unified, and self-contained application or system where all components and functionalities are tightly integrated into a single codebase and deployed as a single unit

Characteristics of a Monolith:

- Single Codebase: In a monolithic architecture, all the components and features of the application are part of a single codebase. This means that all the code is written in one programming language and resides in a single version control repository.
- Tight Coupling: Since all components are part of the same codebase, they are tightly coupled to each other. Changes in one part of the application can have unintended effects on other parts, making maintenance and scaling more challenging.
- Shared Database: Monoliths often use a shared database to store data for all components. This can lead to potential issues with data consistency and performance as the application grows.
- Scalability Challenges: Scaling a monolithic application can be challenging because the entire application needs to be scaled as a single unit, even if only a specific part of the application requires more resources.
- Development and Deployment: Developers working on a monolith **need to coordinate their changes carefully** to avoid conflicts and ensure smooth deployment of updates.
- Testing: Testing a monolithic application can be complex and time-consuming since all components are integrated, and **changes in one area may affect others**.

## Service Oriented Architecture (SOA)
An architectural style and approach to building software systems based on the concept of services. In SOA, an application is composed of individual, self-contained services that communicate with each other through standardized protocols, typically over a network. Each service represents a specific business capability and can be developed, deployed, and maintained independently, promoting loose coupling and reusability.

Key Characteristics of Service-Oriented Architecture:

- Services: In SOA, services are the fundamental building blocks. Each service provides a well-defined functionality and can be invoked independently. Services are designed to be self-contained, modular, and reusable.
- Interoperability: Services communicate with each other using standard communication protocols, such as HTTP, SOAP, or RESTful APIs. This allows services to interact across different platforms, technologies, and programming languages.
- Loose Coupling: SOA promotes loose coupling between services, meaning that changes to one service do not directly affect other services. Loose coupling increases flexibility and makes it easier to modify or replace individual services without disrupting the entire system.
- Service Discovery: To enable service interaction, services must be discoverable within the architecture. Service discovery mechanisms allow services to find and communicate with each other dynamically.
- Service Composition: Applications built on SOA can be composed by combining multiple services to provide higher-level functionality. Service composition allows creating new applications by integrating existing services.
- Reusability: Services are designed to be reusable components that can be utilized in multiple applications. This reduces redundant development efforts and promotes a more efficient development process.
- Scalability: Individual services can be scaled independently based on their specific requirements, allowing for better resource utilization and performance optimization.
- Security: SOA emphasizes the importance of security in service communication and often incorporates security measures like encryption, authentication, and access control.

## Micro Services
An architectural style and approach to building software applications as a collection of small, loosely coupled, and independently deployable services

- Small and Autonomous Services: Microservices are small and focused on performing a single, well-defined function. Each service can be developed, deployed, and scaled independently of others, promoting autonomy and isolation.
- Loose Coupling: Microservices are loosely coupled, meaning **they are independent and don't rely on each other's internal details**. This reduces the impact of changes in one service on others, making it easier to modify and evolve individual services.
- Separate Data Stores: Each microservice typically has its own database or data store, which allows it to manage its data independently and avoids complex shared databases.
- Communication via APIs: Microservices communicate with each other using lightweight APIs, such as HTTP RESTful APIs or message queues. This enables easy integration and interaction between services.
- Polyglot Architecture: Different services in a microservices architecture **can be implemented using different programming languages and technologies**, allowing teams to choose the best tools for their specific needs.
- Scalability: Microservices can be scaled independently based on their individual performance and resource requirements. This provides better resource utilization and allows the system to handle varying loads effectively.
- Resilience and Fault Isolation: Since each service is independent, the failure of one service does not necessarily impact the entire system. Fault isolation is easier to achieve, and the system can continue functioning despite failures in individual services.
- Continuous Deployment: The small and isolated nature of microservices makes it easier to implement continuous integration and continuous deployment (CI/CD) practices, enabling faster and more frequent updates.

## Immutable Architecture

A software design approach where once an application or system is deployed, it cannot be modified. Instead of updating the software in place, any **changes are made by creating a new version of the application or system and deploying it alongside** the existing one.

The main benefits of immutable architecture include improved scalability, reliability, and security. By treating infrastructure as disposable, it is easier to automate and scale deployments, reduce downtime, and ensure that systems are always up-to-date and secure.
