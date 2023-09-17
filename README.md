# AWS CLI Cheatsheet
Documentation for AWS studies. 

## Summary
- [Overview](README.md#overview)
  - JQ Utilization
- Config
    - Create profiles
    - Output Format
    - AWS Region

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

## Config
Create profiles
```shell
aws configure --profile profilename
```

Output format
```shell
aws configure output format {json, yaml, yaml-stream, text, table}
```

AWS Region
```shell
aws configure region (region-name) 
```

## API Gateway
List API Gateway IDs and Names
```shell
aws apigateway get-rest-apis | jq -r ‘.items[ ] | .id+” “+.name’
```

List API Gateway keys
```shell
aws apigateway get-api-keys | jq -r ‘.items[ ] | .id+” “+.name’
```

List API Gateway domain names
```shell
aws apigateway get-domain-names | jq -r ‘.items[ ] | .domainName+” “+.regionalDomainName’
```

Find Lambda for API Gateway resource
```shell
aws apigateway get-integration --rest-api-id (id) --resource-id (resource id) --http-method GET | jq -r ‘.uri’
```

## CloudFront
List CloudFront distributions and origins
```shell
aws cloudfront list-distributions | jq -r ‘.DistributionList.Items[ ] | .DomainName+” “+.Origins.Items[0].DomainName
```

Create a new invalidation
```shell
aws cloudfront create-invalidation [distribution-id]
```

## CloudWatch
List information about an alarm
```shell
aws cloudwatch describe-alarms | jq -r ‘.MetricAlarms[ ] | .AlarmName+” “+.Namespace+” “+.StateValue’
```

Delete an alarm or alarms (you can delete up to 100 at a time)
```shell
aws cloudwatch delete-alarms --alarm-names (alarmnames)
```

## Elastic Block Store (EBS)
Complete a Snapshot
```shell
aws ebs complete-snapshot (snapshot-id)
```

Start a Snapshot
```shell
aws ebs start-snapshot --volume-size (value)
```

Get a Snapshot block
```shell
aws ebs get-snapshot-block
```

```shell
--snapshot-id (value)
```

```shell
--block-index (value)
```

```shell
--snapshot-id (value)
```

```shell
--block-token (value)
```


## Elastic Compute Cloud (EC2)
List Instance ID, Type and Name
```shell
aws ec2 describe-instances | jq -r '.Reservations[].Instances[]|.InstanceId+" "+.InstanceType+" "+(.Tags[] | select(.Key == "Name").Value)'
```

List Instances with public IP address and Name
```shell
aws ec2 describe-instances --query 'Reservations[*].Instances[?not_null(PublicIpAddress)]' | jq -r '.[][]|.PublicIpAddress+" "+(.Tags[]|select(.Key=="Name").Value)
```

List VPCs and CIDR IP Block
```shell
aws ec2 describe-instances --query 'Reservations[*].Instances[?not_null(PublicIpAddress)]' | jq -r '.[][]|.PublicIpAddress+" "+(.Tags[]|select(.Key=="Name").Value)
```

List Subnets for a VPC
```shell
aws ec2 describe-subnets --filter Name=vpc-id,Values=vpc-0d1c1cf4e980ac593 | jq -r '.Subnets[]|.SubnetId+" "+.CidrBlock+" "+(.Tags[]|select(.Key=="Name").Value)'
```

List Security Groups
```shell
aws ec2 describe-security-groups | jq -r '.SecurityGroups[]|.GroupId+" "+.GroupName'```
```

Print Security Groups for an Instance
```shell
aws ec2 describe-security-groups | jq -r '.SecurityGroups[]|.GroupId+" "+.GroupName'```
```

Edit Security Groups of an Instance
```shell
aws ec2 modify-instance-attribute --instance-id i-0dae5d4daa47fe4a2 --groups sg-02a63c67684d8deed sg-0dae5d4daa47fe4a2
```

Print Security Group Rules as FromAddress and ToPort
```shell
aws ec2 describe-security-groups --group-ids sg-02a63c67684d8deed | jq -r '.SecurityGroups[].IpPermissions[]|. as $parent|(.IpRanges[].CidrIp+" "+($parent.ToPort|tostring))'
```

Add Rule to Security Group
```shell
aws ec2 authorize-security-group-ingress --group-id sg-02a63c67684d8deed --protocol tcp --port 443 --cidr 35.0.0.1
```

Delete Rule from Security Group
```shell
aws ec2 revoke-security-group-ingress --group-id sg-02a63c67684d8deed --protocol tcp --port 443 --cidr 35.0.0.1
```

Edit Rules of Security Group
```shell
aws ec2 revoke-security-group-ingress --group-id sg-02a63c67684d8deed --protocol tcp --port 443 --cidr 35.0.0.1
```

Delete Security Group
```shell
aws ec2 delete-security-group --group-id sg-02a63c67684d8deed
```

## EC2 container service (ECS)
Create an ECS cluster
```shell
aws ecs create-cluster --cluster-name=NAME --generate-cli-skeleton
```

Create an ECS service
```shell
aws ecs create-service
```

## Elastic Kubernetes Service (EKS)
Create a cluster
```shell
aws eks create-cluster --name (cluster name)
```

Delete a cluster
```shell
aws eks delete-cluster --name (cluster name)
```

List descriptive information about a cluster
```shell
aws eks describe-cluster --name (cluster name)
```

List clusters in your default region
```shell
aws eks list-clusters
```



#

AWS CLI Reference: 
- https://docs.aws.amazon.com/cli/latest/#
- https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-completion.html






