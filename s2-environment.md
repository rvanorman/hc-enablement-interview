layout: true
class: compact
background-image: url(./assets/images/backgrounds/HashiCorp-Content-bkg.png)
background-size: cover
name: s2-environment

## Deploying the Infrastructure and Vault Cluster

We will start off with using Terraform to deploy a few assests like a vpc, subnets, a jump box, a tls certificate and more that will be utilized by a second Terraform module to deploy the Vault cluster itself.
--


- ![:fontsize 75%](Use the following) ![:fontsize 75%]([repo](https://github.com/rvanorman/tf-test-work-environment)) to deploy the prerequisites. Populate the terraform.tfvars file with your desired info.
--

- ![:fontsize 75%](Run the following via Terraform from your desired CLI environment that has your AWS credentials configured with AWS CLI: 'terraform init' and 'terraform apply --var-file=terraform.tfvars'.)
--

- ![:fontsize 75%](The following outputs are going to be used to populate the tfvars file in the next step: created_VPC, created_private_subnet_a, created_private_subnet_b, created_private_subnet_c, lb_certificate_arn, secrets_manager_arn)
--

- ![:fontsize 75%](Note the jumpbox_public_ip as well for future use to connect through to your Vault cluster.)
--

- ![:fontsize 75%](Now use this) ![:fontsize 75%]([repo](https://github.com/rvanorman/tf-aws-vault-starter)) to deploy the cluster. Populate the terraform.tfvars file with the necessary info.
--

- ![:fontsize 75%](Run the following via Terraform: 'terraform init' and 'terraform apply --var-file=terraform.tfvars'.)


???

---
