# AWS Load Balancer
An AWS Load Balancer is a managed service provided by Amazon Web Services (AWS) that distributes incoming network traffic across multiple instances (servers or resources) in a target group to ensure that no single instance is overwhelmed by excessive traffic. Load balancers are a critical component of modern application architectures, helping improve the availability, scalability, and fault tolerance of applications and services hosted on AWS.

## What are the different types of Load Balancers?
- **Application Load Balancer (ALB)**: ALB operates at the application layer (Layer 7) of the OSI model and is designed to route HTTP/HTTPS traffic to different targets based on content-based rules, such as URL paths and headers. ALB also supports features like path-based routing, host-based routing, and advanced request routing.
- **Network Load Balancer (NLB)**: NLB operates at the transport layer (Layer 4) and is designed to route TCP and UDP traffic to different targets based on IP protocol data. NLB is often used for applications that require extreme performance and low latency.
- **Classic Load Balancer**: Classic Load Balancer, also known as Elastic Load Balancer (ELB), is the original load balancer service in AWS. It balances traffic at both the application and transport layers. While AWS recommends using ALB or NLB for new deployments, Classic Load Balancer is still available for existing applications.

## What are the benefits of using a Load Balancer?
Key features and benefits of AWS Load Balancers include:

- **High Availability**: Load balancers distribute traffic across multiple healthy instances, ensuring that if one instance fails, traffic is automatically routed to the remaining healthy instances.
- **Scalability**: Load balancers can scale horizontally by adding or removing instances as needed to accommodate changes in traffic volume.
- **Auto Scaling Integration**: Load balancers work seamlessly with AWS Auto Scaling to dynamically adjust the number of instances based on application load.
- **Health Checks**: Load balancers continuously monitor the health of instances and route traffic only to healthy instances, helping to identify and isolate unhealthy instances.
- **SSL/TLS Termination**: Load balancers can offload SSL/TLS encryption and decryption, reducing the computational load on instances.
- **Content-Based Routing**: Application Load Balancers allow you to route traffic based on content within HTTP requests, enabling advanced routing scenarios.
- **Logging and Monitoring**: Load balancers provide logs and metrics to help you monitor traffic patterns, troubleshoot issues, and gain insights into application performance.
- **Security Groups**: Load balancers can be associated with security groups to control traffic access and improve security.


## What is a Load Balancer target group?
In the context of an AWS Load Balancer, a "target group" is a logical grouping of target instances or resources that the load balancer directs incoming traffic to. 

```
# Define the AWS provider and region
provider "aws" {
  region = "us-east-1"  # Replace with your desired region
}

# Create a security group for the instances
resource "aws_security_group" "instance_sg" {
  name        = "instance-sg"
  description = "Security group for instances"
  
  # Define your security group rules here, such as allowing inbound traffic on specific ports
  # For example:
  # ingress {
  #   from_port   = 80
  #   to_port     = 80
  #   protocol    = "tcp"
  #   cidr_blocks = ["0.0.0.0/0"]
  # }
}

# Create an AWS ALB
resource "aws_lb" "example_alb" {
  name               = "example-alb"
  internal           = false
  load_balancer_type = "application"
  subnets            = ["subnet-1a2b3c4d", "subnet-5e6f7g8h"]  # Replace with your subnet IDs
}

# Create an AWS target group
resource "aws_lb_target_group" "example_target_group" {
  name        = "example-target-group"
  port        = 80  # The port the instances are listening on
  protocol    = "HTTP"
  target_type = "instance"  # Specifies that we are using EC2 instances as targets

  vpc_id = "vpc-12345678"  # Replace with your VPC ID

  # Specify health check settings
  health_check {
    interval            = 30
    path                = "/"
    port                = "traffic-port"  # The health check uses the same port as the target
    protocol            = "HTTP"
    timeout             = 5
    healthy_threshold   = 2
    unhealthy_threshold = 2
  }
}

# Register instances with the target group
resource "aws_lb_target_group_attachment" "example_target_attachment_1" {
  target_group_arn = aws_lb_target_group.example_target_group.arn
  target_id        = "i-abcdefgh12345678"  # Replace with the ID of your first instance
}

resource "aws_lb_target_group_attachment" "example_target_attachment_2" {
  target_group_arn = aws_lb_target_group.example_target_group.arn
  target_id        = "i-ijklmnop90123456"  # Replace with the ID of your second instance
}
```

## Terraform

### Setup an ALB
```
resource "aws_alb" "application_load_balancer" {
  name               = "${var.app_name}-${var.app_environment}-alb"
  internal           = false
  load_balancer_type = "application"
  subnets            = aws_subnet.public.*.id
  security_groups    = [aws_security_group.load_balancer_security_group.id]

  tags = {
    Name        = "${var.app_name}-alb"
    Environment = var.app_environment
  }
}
```

### Security group for ALB
```
resource "aws_security_group" "load_balancer_security_group" {
  vpc_id = aws_vpc.aws-vpc.id

  ingress {
    from_port        = 80
    to_port          = 80
    protocol         = "tcp"
    cidr_blocks      = ["0.0.0.0/0"]
    ipv6_cidr_blocks = ["::/0"]
  }

  egress {
    from_port        = 0
    to_port          = 0
    protocol         = "-1"
    cidr_blocks      = ["0.0.0.0/0"]
    ipv6_cidr_blocks = ["::/0"]
  }
  tags = {
    Name        = "${var.app_name}-sg"
    Environment = var.app_environment
  }
}
```
### Load balancer Target Group
```
resource "aws_lb_target_group" "target_group" {
  name        = "${var.app_name}-${var.app_environment}-tg"
  port        = 80
  protocol    = "HTTP"
  target_type = "ip"
  vpc_id      = aws_vpc.aws-vpc.id

  health_check {
    healthy_threshold   = "3"
    interval            = "300"
    protocol            = "HTTP"
    matcher             = "200"
    timeout             = "3"
    path                = "/v1/status"
    unhealthy_threshold = "2"
  }

  tags = {
    Name        = "${var.app_name}-lb-tg"
    Environment = var.app_environment
  }
}
```

### Create a listener for the ALB
```
resource "aws_lb_listener" "listener" {
  load_balancer_arn = aws_alb.application_load_balancer.id
  port              = "80"
  protocol          = "HTTP"

  default_action {
    type             = "forward"
    target_group_arn = aws_lb_target_group.target_group.id
  }
}
```
