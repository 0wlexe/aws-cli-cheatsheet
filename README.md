# AWS CLI Cheatsheet
Documentation for AWS studies. 

## Summary
- [Overview](README.md#overview)
  - [JQ Utilization](README.md#jq-utilization)
- [Config](https://github.com/0wlexe/aws-cli-cheatsheet/blob/main/config.md)
- [API Gateway](https://github.com/0wlexe/aws-cli-cheatsheet/blob/main/api-gateway.md)
- [AWS IAM](https://github.com/0wlexe/aws-cli-cheatsheet/blob/main/aws-iam.md)
- [CloudFront](https://github.com/0wlexe/aws-cli-cheatsheet/blob/main/cloudfront.md)
- [CloudWatch](https://github.com/0wlexe/aws-cli-cheatsheet/blob/main/cloudwatch.md)
- [Elastic Block Store (EBS)](https://github.com/0wlexe/aws-cli-cheatsheet/blob/main/aws-ebs.md)
- [Elastic Compute Cloud (EC2)](https://github.com/0wlexe/aws-cli-cheatsheet/blob/main/aws-ec2.md)
- [EC2 container service (ECS)](https://github.com/0wlexe/aws-cli-cheatsheet/blob/main/aws-ecs.md)
- [Elastic Kubernetes Service (EKS)](https://github.com/0wlexe/aws-cli-cheatsheet/blob/main/aws-eks.md)

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






