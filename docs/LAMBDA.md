# Lambda



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


## What is the best way to handle shared code between Lambda functions?
Utilize AWS Lambda Layers for sharing common code and dependencies across functions. This can help maintain consistency and security in your serverless applications.
