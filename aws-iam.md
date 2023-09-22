
## AWS IAM 
Create IAM User
```shell
aws iam create-user --user-name (account-name)
```

Create access keys and record access keys for later use
```shell
aws iam create-access-key --user-name (account-name)
```

Configure CLI with profile
```shell
aws configure --profile (account-name)
```

Create policy/save if in JSON file
```shell
aws iam create-policy --policy-name (account-name)-ec2 --policy-document file://(account-name)-ec2.json
```

Attach policy
```shell
aws iam attach-user-policy --user-name (account-name) --policy-arn "arn:aws:iam::ACCOUNT_A_ID:policy/(account-name)-ec2"
```

List policies attached to (account-name)
```shell
aws iam list-attached-user-policies --user-name (account-name)
```

Create IAM instance profile
```shell
aws iam list-attached-user-policies --user-name (account-name))
```
