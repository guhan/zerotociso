# Continuous Integration (CI)/ Continous Delivery (CD)

## What are the steps for a CI/CD pipeline? 
- **Code Repository**:
  - Host your application code in a version control system like Git (e.g., GitHub, GitLab, Bitbucket)
  - Setup appropriate permissions for the repository using RBAC
  - Require a code review for each PR
    
- **CI/CD Pipeline Setup**:
  - Choose a CI/CD platform (e.g., Github Actions, Jenkins, GitLab CI/CD, Travis CI, CircleCI).

- **Define your CI/CD Workflow**:
  - Build: Build your application code into deployable artifacts (e.g., Docker images, JAR files).
    - Store the artifacts in a container registry (e.g., Amazon ECR, Docker Hub).
    - Make sure to tag the artifact with a version, and use a clear versioning strategy (SemVer) 

  - Test: Execute automated tests to validate the application
    - unit tests
    - integration tests
    - check for leaked credentials
    - perform static analysis (SAST)
    - scan for vulnerabilities in the container image

  - Deployment:
    - Deploy the artifact to a test environment (pre-prod) first
    - Define the Kubernetes manifests (YAML files) that describe your application's deployment, services, and other resources.
    - Use Kubernetes configuration files to specify the desired state of your application.

- **EKS Configuration**:
  - Configure authentication and permissions to allow your CI/CD pipeline to interact with your EKS cluster.
  - Ensure that your CI/CD system can interact with the Kubernetes cluster running in EKS.
  - Set up a Kubernetes context to access your EKS cluster using the kubectl command-line tool or other Kubernetes client libraries.
  - Use Kubernetes ConfigMaps or Secrets to store configuration settings required for your application.
  - Customize environment-specific configurations for your deployments.
  - Setup appropriate network policies for Kubernetes

- **Deployment Strategy**:
  - Define your deployment strategy:
    - Rolling updates with zero downtime
    - blue-green deployments
    - canary releases

- **Continuous Deployment**:
  - Set up a trigger mechanism in your CI/CD pipeline to automatically deploy to EKS whenever changes are pushed to the main branch or feature branches.

- **Monitoring and Alerting**:
  - Implement monitoring and logging solutions (e.g., Prometheus, Grafana, AWS CloudWatch) to collect and visualize metrics from your applications running on EKS.
  - Configure notifications to alert your team of successful deployments or any issues during the CI/CD process.
  - Continuously monitor and optimize your EKS cluster for performance, scalability, and cost-efficiency.

- **Rollback and Recovery**:
  - Implement rollback procedures in case a deployment goes wrong.
  - MTTR: Make sure you can quickly revert to a previous stable state if necessary

- **Documentation**:
  - Document your CI/CD pipeline setup, including deployment procedures, access controls, and environment configurations.

- **Production Deployment**:
  - Deploy to the production environment using your CI/CD pipeline _only_ after successful testing and validation in the staging environment.


 



