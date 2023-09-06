# AWS 

## What are the important cloud security aspects in AWS?

- Identity and Access Management (IAM): Implement robust IAM practices to control and manage user access to AWS resources. This involves using strong authentication mechanisms, defining granular permissions, and regularly reviewing and auditing access privileges.
- Data Protection: Ensure the confidentiality, integrity, and availability of your data. Implement encryption mechanisms for data at rest and in transit using services like AWS Key Management Service (KMS) and SSL/TLS certificates. Use secure storage services like Amazon S3 with access control mechanisms.

- Network Security: Utilize Virtual Private Cloud (VPC) to create isolated network environments and control inbound and outbound traffic with security groups and network ACLs. Use AWS Firewall Manager, AWS WAF (Web Application Firewall), and AWS Shield to protect against network-based attacks.


- Secure Configuration: Follow AWS security best practices and ensure that your AWS services and resources are configured securely. Implement multi-factor authentication (MFA), enforce strong password policies, regularly patch and update software, and apply security configurations to prevent vulnerabilities.


- Monitoring and Logging: Enable AWS CloudTrail to monitor and log all API activity in your AWS account. Utilize AWS Config to assess and audit resource configurations for compliance. Implement centralized logging using services like AWS CloudWatch Logs and AWS CloudTrail to gain visibility into security events and potential threats.


- Incident Response: Develop an incident response plan to quickly respond to and mitigate security incidents. Define roles and responsibilities, establish communication channels, and conduct periodic security incident simulations to test and improve your incident response capabilities.
Compliance and Governance: Understand and adhere to relevant compliance standards and regulations, such as GDPR, HIPAA, PCI DSS, etc. Leverage AWS services and features that help meet compliance requirements, such as AWS Artifact, AWS Config Rules, and AWS CloudTrail.


- Disaster Recovery and Business Continuity: Implement backup and recovery strategies to ensure the resilience and availability of your AWS infrastructure. Utilize services like AWS Backup and Amazon S3 versioning to protect against data loss. Use AWS services like AWS Elastic Beanstalk, AWS Auto Scaling, and AWS Route 53 to achieve high availability and fault tolerance.


- Third-Party Integration: If using third-party services or applications in conjunction with AWS, ensure they are properly vetted for security and adhere to your organization's security standards. Maintain oversight and control over access and data sharing with external parties.

## How to setup an AWS account? 

- Use organizations to segment various accounts. 
- **SCP stands for Service Control Policies**. SCPs are a feature of AWS Organizations that allow you to define fine-grained permissions and access controls for AWS accounts within your organization.
You can define fine-grained permissions by allowing or denying access to specific AWS services, APIs, actions, or resources.
  - Enforcement: SCPs are enforced at the AWS Organizations level and are independent of any individual account's IAM (Identity and Access Management) policies. This means that even if an IAM policy allows certain actions, an SCP can override and deny those actions at the organizational level.


## AWS Well Architected Framework
### Operational Excellence Pillar
The operational excellence pillar focuses on running and monitoring systems, and continually improving processes and procedures. Key topics include automating changes, responding to events, and defining standards to manage daily operations.

### Security Pillar
The security pillar focuses on protecting information and systems. Key topics include confidentiality and integrity of data, managing user permissions, and establishing controls to detect security events.
### Reliability Pillar
The reliability pillar focuses on workloads performing their intended functions and how to recover quickly from failure to meet demands. Key topics include distributed system design, recovery planning, and adapting to changing requirements.
### Performance Efficiency Pillar
The performance efficiency pillar focuses on structured and streamlined allocation of IT and computing resources. Key topics include selecting resource types and sizes optimized for workload requirements, monitoring performance, and maintaining efficiency as business needs evolve.
### Cost Optimization Pillar
The cost optimization pillar focuses on avoiding unnecessary costs. Key topics include understanding spending over time and controlling fund allocation, selecting resources of the right type and quantity, and scaling to meet business needs without overspending.

### Sustainability Pillar
The sustainability pillar focuses on minimizing the environmental impacts of running cloud workloads. Key topics include a shared responsibility model for sustainability, understanding impact, and maximizing utilization to minimize required resources and reduce downstream impacts. 


## What is AWS Directory Service?	
AWS Directory Service for Microsoft Active Directory (Enterprise Edition): Also known as AWS Managed Microsoft AD, this service provides a fully managed Microsoft Active Directory in the AWS cloud. It is compatible with Microsoft Active Directory, allowing you to migrate or extend your on-premises Active Directory to the AWS cloud. It supports common Active Directory features, such as Group Policies, trusts, and domain join.


- AD Connector: AD Connector enables you to connect your existing on-premises Microsoft Active Directory to AWS services without the need for directory synchronization or replication. It acts as a proxy, allowing your AWS resources to authenticate against your on-premises Active Directory.


- Simple AD: Simple AD is a directory service compatible with Microsoft Active Directory. It offers a subset of the features provided by AWS Managed Microsoft AD, making it a cost-effective option for applications that don't require advanced Active Directory functionality.


- AWS Directory Service for OpenLDAP: This service allows you to run your own OpenLDAP (Lightweight Directory Access Protocol) directory in the AWS cloud. It provides compatibility with applications that use LDAP for authentication and authorization.

## What is Amazon GuardDuty?
Cloud based threat detection service

## What is AWS Firewall Manager?
Firewall Manager enables you to centrally manage AWS WAF (Web Application Firewall) rules across multiple AWS accounts and resources. It allows you to create and apply security rules to protect your web applications from common web-based attacks.


## What is AWS Shield?
AWS Shield: AWS Shield is a managed Distributed Denial of Service (DDoS) protection service. It provides automatic protection against volumetric, state-exhaustion, and application layer DDoS attacks to help keep your applications and data available.

- Global threat dashboard that whows all AWS related attacks
- DDOS Response Team (DRT) can access your rules


## What is AWS Inspector?
Amazon Inspector: Inspector is an automated security assessment service that helps you identify security vulnerabilities and deviations from best practices in your EC2 instances and applications. It provides detailed findings and recommendations for remediation.
Looks for software vulnerabilities and unintended network access. Keeps an internal database and lets you assign a risk score. 

- CVE
- CIS Controls

Works on: 
- Network
- Host (requires agent)

## What is AWS KMS?
AWS Key Management Service (KMS): KMS is a managed service that allows you to create and control the encryption keys used to encrypt your data. It provides a secure and scalable solution for managing encryption keys for various AWS services and your own applications.

## What is AWS Secrets Manager?
AWS Secrets Manager: Secrets Manager enables you to securely store and manage secrets, such as database credentials, API keys, and other sensitive information. It provides central management, automatic rotation, and integration with other AWS services.

## What is AWS Security Hub? 
CSPM - send findings from Inspector, GuardDuty and Macie to it and you can use a benchmark like CIS or PCI to see what the current posture is

## What is AWS Certificate Manager?
AWS Certificate Manager (ACM): ACM makes it easy to provision, manage, and deploy Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS services. It simplifies the process of obtaining and renewing SSL/TLS certificates for your applications.

## What is AWS Trusted Advisor?
AWS Trusted Advisor is a service provided by Amazon Web Services (AWS) that helps customers optimize their AWS infrastructure, improve performance, enhance security, and reduce costs. It provides real-time guidance by analyzing the customer's AWS account and making recommendations based on best practices and AWS architectural principles.

## What is AWS Cloud Trail?
AWS Cloud Trail are audit logs for everything that happens in a AWS account

## What are VPC Flow Logs?
VPC Flow logs contain the traffic flows between various resources in an AWS Account

## What is AWS Cloud Watch?
Cloud Watch lets you visualize and alert on various AWS Events It collects and tracks metrics, logs, and events from various AWS resources

- Metric - cpu utilization
- Logs - Incorrect SQL query
- Event - state changed on EC2 instance

With CloudWatch Alarms, you can set thresholds on metrics and define actions to be triggered when those thresholds are breached. For example, you can configure an alarm to send a notification or invoke an AWS Lambda function when CPU utilization exceeds a certain threshold for a specified period.

```
# Terraform
provider "aws" {
  region = "us-west-2"  # Replace with your desired region
}

resource "aws_instance" "example_instance" {
  ami           = "ami-0c94855ba95c71c99"  # Replace with your desired AMI ID
  instance_type = "t2.micro"  # Replace with your desired instance type

  # Other instance configuration...
}

resource "aws_cloudwatch_metric_alarm" "example_alarm" {
  alarm_name          = "example-alarm"
  comparison_operator = "GreaterThanOrEqualToThreshold"
  evaluation_periods  = "1"
  metric_name         = "CPUUtilization"
  namespace           = "AWS/EC2"
  period              = "60"
  statistic           = "Average"
  threshold           = "100"
  alarm_description   = "This metric alarm triggers when CPU utilization reaches 100%"
  alarm_actions       = []  # Specify any actions to be triggered when the alarm state changes

  dimensions = {
    InstanceId = aws_instance.example_instance.id
  }
}
```


## Route 53 Security Controls

- DNSSEC (Domain Name System Security Extensions): DNSSEC is a security feature that helps ensure the integrity and authenticity of DNS data. Route 53 supports DNSSEC, allowing you to sign your domain's DNS records and verify their authenticity through digital signatures.
- DNS Firewall: DNS Firewall in Route 53 allows you to set up rules to block DNS queries to known malicious domains or IP addresses. This helps in preventing access to malicious content and mitigating potential DNS-based attacks.
- Health Checks: Route 53 offers health checks to monitor the health and availability of your resources. You can configure health checks for your endpoints and define the criteria for determining their availability. This helps in detecting and responding to any issues or outages affecting your resources.
- Traffic Flow: Traffic Flow in Route 53 allows you to configure advanced traffic routing policies for your domain. It includes features such as geolocation routing, latency-based routing, and weighted round-robin routing. These features help distribute traffic efficiently and provide resilience against DDoS (Distributed Denial of Service) attacks.
- VPC Association: Route 53 supports associating your DNS records with Virtual Private Cloud (VPC) resources. By associating records with VPCs, you can control access to your resources within your private network and enhance the security of your DNS infrastructure.


## How to encrypt an EBS volume at Rest?
Modify volume 
- "AWS Managed CMK" (Customer Master Key): This option allows you to use AWS-managed keys for encryption. You can select the AWS managed key or let AWS create a new one for you.
- "Customer Managed CMK": If you want to use a key that you manage in AWS Key Management Service (KMS), select this option and choose the appropriate CMK.
- "No Encryption": Select this option if you want to remove encryption from the volume.
```
# Terraform
resource "aws_ebs_volume" "example_volume" {
  availability_zone = "us-west-2a"
  size              = 50
  encrypted         = true
}
```

# How to create a lambda function with Terraform?
Setup provider
```
provider "aws" {
  region = "us-west-2"  # Replace with your desired region
}
```
Create the function
```
resource "aws_lambda_function" "example_function" {
  function_name = "example-function"
  role          = aws_iam_role.example_role.arn  # Replace with the ARN of the IAM role for the Lambda function
  handler       = "index.handler"
  runtime       = "python3.8"  # Replace with the desired runtime for your Lambda function
  filename      = "example-function.zip"  # Replace with the filename of your Lambda function code package
  source_code_hash = filebase64sha256("example-function.zip")  # Replace with the appropriate hash for your Lambda function code package

  # Other Lambda function configuration...
}
```
Create an IAM role for the function
```
resource "aws_iam_role" "example_role" {
  name = "example-role"

  assume_role_policy = <<EOF
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "lambda.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
EOF
}

resource "aws_iam_role_policy_attachment" "example_policy_attachment" {
  role       = aws_iam_role.example_role.name
  policy_arn = "arn:aws:iam::aws:policy/AWSLambdaFullAccess"  # Replace with the appropriate policy for your Lambda function's required permissions
}
```
## What is a handler in a Lambda function?
the handler refers to the specific function within your code that AWS Lambda invokes when the function is triggered.

