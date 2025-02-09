# AWS-Terraform
erraform:
------------

In order to launch your first EC2 instance using Terraform, you need to make sure you are ready with few things mentioned below: -

AWS Free Tier Account, use existing or create a programmatic user
AWS Access Key ID & AWS Secret Access Key for programmatic access
Programmatic user should have Administrator Access to manage Infra

Commands:
Execute terraform validate, to validate all terraform files in present working directory

Execute terraform init, to download and configure plugin for provider “aws”

Execute terraform plan, to generate and show execution plan

Execute terraform apply followed by a confirmation(Yes), to build the infrastructure

Execute terraform destroy to terminate the instance, remember terraform destroy will delete all your existing infrastructure


--------------------------------------------------------------------------------------------------------------------------------------------------------

Create EC2 instance
--------------------
provider "aws" {
    access_key="<YOUR-AWS-ACCESS-KEY"
    secret_key="<YOUR-AWS-SECRET-ACCESS-KEY>"
    region="ap-south-1"
}
resource "aws_instance" "Demo1" {
    ami="ami-03b8a287edc0c1253"
    instance_type="t2.micro"
}

we have explicitly mentioned the AWS access key in the instance.tf file. This is not recommended, hard coding credentials into terraform configuration risks secret leakage should the files ever be committed to public version control system. Providing credentials for authentication in terraform as below:

Static Credentials
Environment Variables
Shared Credentials File
EC2 Role
