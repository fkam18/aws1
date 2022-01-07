# aws1
6 Jan 2022
fkam
trying out terraform and packer on AWS
based on:
https://www.middlewareinventory.com/blog/packer-aws-terraform-example/
https://stackoverflow.com/questions/69674747/how-to-put-ami-name-in-packer-manifest
https://learn.hashicorp.com/tutorials/terraform/aws-build

Basically based on a ubuntu 20 AMI with a setup script to install apache2, then generates a customized AMI, and then pass to Terraform to provision on AWS

Key changes:
- adapted to the AMI's available on us-west-2
- Packer build source based on AMI rather than filter (AMI from ubuntu-20 from AWS us-west-2)
- Packer setup.sh simplified to just install apache2 just to prove the concept
- generated AMI id manually copied to main.tf for terraform apply
- default vpc network rule added 80 and 22 ports allow
