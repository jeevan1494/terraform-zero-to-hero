# SCENARIO1:  MIGRATION TO TERRAFORM & DRIFT DETECTION

https://youtu.be/-4IMy5ihiiU

syntax to import aws configuration to terraform:

provider "aws" {
  region = "us-east-1"

}

import {  
 id = "i-9387528476" #instance id which you want to copy

 to = aws_instance.example
}

try the command
terraform plan -generate-config-out=generated_resources.tf
you will get configuration file and copy it to main.tf

remove ipv6 config and try the below command:

terraform import aws_instance.example i-90246509274 # give instance id which you want to copy the config

terraform plan # expected is it should not show any new addditions and the existed instance will be migrated to terraform which means your state file will be refreshed without creating new one

SCENARIO2: DRIFT DETECTION:

If someone changes state file manually then we need to detect it

Solution: 1. Use terraform refresh command 
          2. Use cronjob of terraform refresh 
          3. Setup audit logs and create a lambda function that triggers an alert when thers is a change from other than terraform user. 
you
