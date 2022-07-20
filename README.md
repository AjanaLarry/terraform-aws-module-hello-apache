This Terraform module will provision an EC2 Instance that is running Apache.

This is not intended for production use.


```HCL

terraform{

}

provider "aws" {
  region = "us-east-1"
}

module "hello_apache" {
  source = "./terraform-aws-module-hello-apache"
  vpc_id = "vpc-00DEFAULTVPC00"
  my_ip = "YOUR_IP_ADDRESS/32"
  public_key = "ssh-rsa AAAAB.../root/.ssh/terraform.pub"
  instance_type = "t2.micro"
  server_name = "Hello Apache Server"

}

output "public_ip"{
  value = module.hello_apache.public_ip
}

```
