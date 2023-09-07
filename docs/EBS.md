# Elastic Block Storage (EBS)


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
