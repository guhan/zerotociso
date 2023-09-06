# Identity and Access Management (IAM)

## What are the different parts of an IAM policy?

Acronym: SEARC

- Policy Version

- Statement: Contains one or more individual statements that define the permissions and restrictions within the policy. Each statement consists of the following components:
  a. Effect: Specifies whether the statement allows or denies access. It can have two values: "Allow" or "Deny."

  b. Action: Specifies the AWS service actions or API operations that the policy allows or denies. For example, "s3:GetObject" or "ec2:DescribeInstances."

  c. Resource: Specifies the AWS resources to which the policy applies. It can be an Amazon Resource Name (ARN) or a wildcard (*) to indicate all resources.

  d. Condition: Optionally includes conditions that must be met for the statement to be evaluated. Conditions allow for additional fine-grained control based on attributes like IP address, time, or resource tags.



## Policy Level
IAM policies can be attached at different levels:
- **Identity-Based Policies**: Attached to individual IAM users, groups, or roles.
- **Resource-Based Policies**: Attached directly to AWS resources like S3 buckets, Lambda functions, or SQS queues.
- **Organizational Policies**: Attached to an AWS Organizations entity and applied to all accounts within the organization.
- **Permission Boundaries**: Used to set the maximum permissions that an IAM entity can have.

## How can you check the security of an IAM policy?
Use **IAM Access Analyzer** to identify unintended resource sharing and ensure that your IAM policies have the intended permissions.
