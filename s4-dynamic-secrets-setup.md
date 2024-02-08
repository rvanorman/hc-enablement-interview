layout: true
class: compact
background-image: url(./assets/images/backgrounds/HashiCorp-Content-bkg.png)
background-size: cover
name: s4-dynamic-secrets-setup

## Configuring AWS Secrets Engine

At this time the Vault cluster is ready for setting up secrets engines. Make sure to have an access key pair with permissions to create a user to operate on EC2 instances.

```
user@host:~$ vault secrets enable -path=aws aws
Success! Enabled the aws secrets engine at: aws/
user@host:~$ export AWS_ACCESS_KEY_ID=<aws_access_key_id>
user@host:~$ export AWS_SECRET_ACCESS_KEY=<aws_secret_key>
user@host:~$ vault write aws/config/root access_key=$AWS_ACCESS_KEY_ID secret_key=$AWS_SECRET_ACCESS_KEY region=us-east-1
Success! Data written to: aws/config/root
```

???
1) Enable the vault Secrets Engine on an instance in your vault cluster: 

vault secrets enable -path=aws aws

2) If you have not already, create an AWS access and secret access key for a user that has access to create users with permissions for EC2 Operations to your AWS account

3) Now create Environemnt Variables for the AWS access key on an instance in your vault cluster
export AWS_ACCESS_KEY_ID=<aws_access_key_id>
export AWS_SECRET_ACCESS_KEY=<aws_secret_key>

4) Write the config to vault for AWS access

vault write aws/config/root \
    access_key=$AWS_ACCESS_KEY_ID \
    secret_key=$AWS_SECRET_ACCESS_KEY \
    region=<your-region>

---
