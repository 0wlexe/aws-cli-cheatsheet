# AWS CLI Cheatsheet
DOcumentation for AWS studies. AWS CLI Reference: https://docs.aws.amazon.com/cli/latest/#

## Summary
- Commands
  - Config
    - Create profiles
    - Output Format
    - AWS Region

## Commands

### Config
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
