
## Identity & Access Management (IAM)

### Dictionary

- **IAM:** Identity that provides secure and controlled access to AWS services.
- **Role:** Type of IAM identity that can be authenticated and authorized to utilize an AWS resource.
- **Policy:**	 Defines the permissions of the IAM identity. IAM policies can either be identity-based or resource-based.
  - **Identity-based:** Are attached to an identity (a user, group, or role) and dictate the permissions of that specific identity.
  - **Resource-based:** Defines the permissions around the specific resource by specifying which identities have access to a specific resource and when.

## AWS CLI - Commands 

### User Management

Create IAM User
```shell
aws iam create-user --user-name account-name
```

Create access keys and record access keys for later use
```shell
aws iam create-access-key --user-name account-name
```

Configure CLI with profile
```shell
aws configure --profile account-name
```

#
### Policies
Create policy/save in JSON file
```shell
aws iam create-policy --policy-name account-name-ec2 --policy-document file://account-name-ec2.json
```

Attach policy
```shell
aws iam attach-user-policy --user-name account-name --policy-arn "arn:aws:iam::ACCOUNT_A_ID:policy/account-name-ec2"
```

List policies attached to (account-name)
```shell
aws iam list-attached-user-policies --user-name account-name
```

#
### Instances

Create IAM instance profile
```shell
aws iam create-instance-profile --instance-profile-name mytestinstanceprofile --profile account-name
```

Add role to instance profile (S3 Read Only)
```shell
aws iam add-role-to-instance-profile --role-name S3ReadOnly --instance-profile-name mytestinstanceprofile --profile account-name
```

Associate instance profile with EC2 instance
```shell
aws ec2 associate-iam-instance-profile --instance-id YOUR_EC2_INSTANCE_ID --iam-instance-profile Name=mytestinstanceprofile --profile account-name
```

Remove role from instance profile
```shell
aws iam remove-role-from-instance-profile --role-name S3ReadOnly --instance-profile-name mytestinstanceprofile --profile account-name
```

Delete instance profile
```shell
aws iam delete-instance-profile --instance-profile-name mytestinstanceprofile --profile account-name
```

