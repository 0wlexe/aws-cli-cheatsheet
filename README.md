# AWS CLI Cheatsheet
Documentation for AWS studies. 

## Summary
- [Overview](README.md#overview)
  - [JQ Utilization](README.md#jq-utilization)
- [Config](README.md#config)
- [API Gateway](README.md#api-gateway)
- [AWS IAM](README.md#aws-iam)
- [CloudFront](README.md#cloudfront)
- [CloudWatch](README.md#cloudwatch)
- [Elastic Block Store (EBS)](README.md#elastic-block-store-ebs)
- [Elastic Compute Cloud (EC2)](README.md#elastic-compute-cloud-ec2)
- [EC2 container service (ECS)](README.md#ec2-container-service-ecs)
- [Elastic Kubernetes Service (EKS)](README.md#elastic-kubernetes-service-eks)

## Overview
The purpose of this page is to separate a list of commands and descriptions for study purposes. 

AWS CLI stands for Amazon Web Services Command Line Interface. When managing your AWS services there are a few options as far as tools go. Two of the most common options are the AWS Console, or AWS CLI. 

- **AWS Console -** A web interface that you log into to manage your AWS services. 
- **AWS CLI -** A tool to manage AWS resources across different accounts, regions, and environments from the command line. It allows you to control services manually or create automation with scripts.

### JQ Utilization
This cheatsheet utilizes jq, a lightweight and flexible command-line JSON processor - you can use it to slice and filter and map and transform structured data with the same ease that sed, awk, grep and friends let you play with text.

**More information on it can be found in the JQ Github repository:** https://jqlang.github.io/jq/

Installation on Linux - Debian/Ubuntu
```shell
sudo apt-get install jq
```

Installation on Linux - Fedora
```shell
sudo dnf install jq
```

#

AWS CLI Reference: 
- https://docs.aws.amazon.com/cli/latest/#
- https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-completion.html






