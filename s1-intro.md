layout: true
class: compact
background-image: url(./assets/images/backgrounds/HashiCorp-Content-bkg.png)
background-size: cover
name: s1-intro

## Introduction and What is Covered

Throughout the next few slides we are going to setup a test environment and a Vault cluster inside of AWS. Following that we will configure Vault to use dynamic secrets in the form of creating short-lived users in AWS that have permissions for working with EC2 instances.
--

- Start off using Terraform code to spin up a environment and the Vault cluster prior to going over the use of dynamic secrets.
--

- Vault will be initialized and then setup to use the AWS secrets engine. A role will be defined in Vault for the secrets to use, and these secrets will create users in AWS.
--

- The users are created with dynamically generated access key pairs to be able to interact with EC2 instances in the AWS Account they are created in.
--

- Each time a call is made to Vault to read the established role, a new IAM user and access key pair will be generated.
--

- These users will automatically be removed after their lease expires, however we will cover revoking the credentials with Vault in the event this needs to be done earlier.

???

---
