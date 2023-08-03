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

## Single Tenant 
System is designed to serve only one customer or tenant at a time.

- Isolation: Each customer or tenant has their own dedicated environment, including separate databases, configurations, and resources. This isolation ensures data privacy, security, and minimizes the risk of interference between tenants.
- Customization: Single-tenant architecture allows for a high degree of customization for individual customers or tenants. They can have specific configurations, branding, and even custom code tailored to their unique needs.
- Performance and Scalability: Resources such as computing power, storage, and memory can be allocated based on the specific requirements of each tenant, ensuring optimal performance and scalability.
- Data Privacy and Security: Since each tenant has a separate instance, data is kept separate, reducing the risk of data leaks or unauthorized access to sensitive information.
- Upgrades and Maintenance: Upgrades and maintenance can be performed independently for each tenant without affecting others. This allows for more control over downtime and versioning.
- Billing and Subscriptions: Single-tenant architectures often align well with subscription-based billing models, where each customer pays for their dedicated instance of the application.

**Downsides:** 
- Resource Utilization: Single-tenant architectures may lead to lower resource utilization compared to multi-tenant architectures, where resources are shared among multiple tenants.
- Cost: Setting up and maintaining separate instances for each tenant can be costlier compared to shared resources in multi-tenant architectures.
- Complexity: Managing and maintaining separate instances can introduce complexity in the deployment and management of the application.

## Multi Tenant 
Supports multiple customers or tenants using a shared instance of the application. In multi-tenancy, tenants share the same resources and database, while data isolation is managed through logical or physical separation.

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


## Event Based Architecture
Communication between different software components is based on events. In this architecture, components (also known as services) produce and consume events, which are notifications of significant occurrences or changes in the system. Events are typically small, self-contained messages that carry information about the event that occurred.

### Key Concepts and Components of Event-Based Architecture:
- Event Producer: The component or service that generates and publishes events to the event bus. It announces that something has happened.
- Event Consumer: The component or service that listens for specific events on the event bus and reacts to them. It processes the events it is interested in.
- Event Bus (Message Broker): The central communication channel that facilitates the exchange of events between producers and consumers. The event bus ensures that events are delivered to the appropriate consumers.
- Event: A small, self-contained message that carries information about a specific occurrence or change in the system. Events are typically represented in a structured format (e.g., JSON) and contain relevant data about the event.
- Event Handler: The logic within a service that processes incoming events and triggers actions or updates based on the event's information.

### Key Benefits of Event-Based Architecture:

- Loose Coupling: Components are decoupled, allowing them to evolve independently without affecting each other.
- Scalability: Services can scale independently, as they are not directly dependent on each other.
- Resilience: Services can temporarily go offline or become unavailable without affecting other services since events can be queued and processed later.
- Flexibility: New services can be added or existing ones modified without disrupting the system's overall behavior.
- Asynchronicity: Processing events asynchronously allows for better responsiveness and performance.
- Event Sourcing and CQRS: Event-based architectures often support event sourcing and the Command Query Responsibility Segregation (CQRS) pattern, enabling better data consistency and separation of read and write operations.

## Immutable Architecture

A software design approach where once an application or system is deployed, it cannot be modified. Instead of updating the software in place, any **changes are made by creating a new version of the application or system and deploying it alongside** the existing one.

The main benefits of immutable architecture include improved scalability, reliability, and security. By treating infrastructure as disposable, it is easier to automate and scale deployments, reduce downtime, and ensure that systems are always up-to-date and secure.
