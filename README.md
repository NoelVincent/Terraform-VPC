# Terraform - VPC
Creating a VPC using terraform

# Creating a VPC using Terraform

Terraform is an open-source infrastructure as code software tool that provides a consistent CLI workflow to manage hundreds of cloud services. Terraform codifies cloud APIs into declarative configuration files.
https://www.terraform.io/

## Installing Terraform
- Create an IAM user on your AWS console and give access to create the required resources.
- Create a directory where you can create terraform configuration files.
- Download Terrafom, click here [Terraform](https://www.terraform.io/downloads.html).
- Install Terraform, click here [Terraform installation](https://learn.hashicorp.com/tutorials/terraform/install-cli?in=terraform/aws-get-started)

##### Command to install Terraform
```sh
# wget https://releases.hashicorp.com/terraform/1.0.8/terraform_1.0.8_linux_amd64.zip
# unzip terraform_1.0.8_linux_amd64.zip
# mv terraform /usr/local/bin/

# terraform version   =======> To check the version
Terraform v1.0.8
on linux_amd64
```

> Note : The terrafom files must be created with .tf extension as terraform can only execute .tf files
> https://www.terraform.io/docs/language/files/index.html
