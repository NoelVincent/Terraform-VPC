# Creating a VPC using Terraform
Here, I am creating a VPC with 6 subnets(3 public and 3 private) along with an Internet Gateway, a NAT Gateway and 2 Route Tables(1 public and 1 private). Also, a Bastion server(having only SSH access), a webserver(HTTP and HTTPS port enabled and also SSH access from the bastion server) and a database server(with 3306 port and SSH access from bastion server)

## Terraform
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

## 1. Declaring Variables
This is used to declare the variable and pass values to terraform source code.
```sh
vim variable.tf
```
##### Declare the variables for initialising terraform

```sh
variable "project" {
  default = "test"
}
variable "access_key"{
  default = " "           #==========> provide the access_key of the IAM user
}
variable "secret_key"{
  default = " "          #==========> provide the secret_key of the IAM user
}
variable "vpc_cidr" {
  default = "172.16.0.0/16"
}
variable "vpc_subnets" {
  default = "3"
}
variable "type" {
  description = "Instance type"    
  default = "t2.micro"
}
variable "ami" {
  description = "amazon linux 2 ami"
  default = "ami-041d6256ed0f2061c"
}
```
##### Creating a variable.tfvars
> Note : A terraform.tfvars file is used to set the actual values of the variables.
```sh
vim variable.tfvars
```
```sh
project     = " Your project name"
access_key  = "IAM user access_key"
secret_key  = "IAM user secret_key"
vpc_cidr    = "VPC cidr block"
vpc_subnets = "subnets"
type        = "Instance type"
ami         = "ami of the instance"
```

