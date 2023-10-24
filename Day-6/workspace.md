1. Command to create workspace:
terraform workspace new dev
terraform workspace new stage
terraform workspace new prod

2. Command to switch between the workspaces:

terraform workspace select dev
terraform workspace select stage
terraform workspace select prod

3. To print current workspace

terraform workspace show

4. Command to apply by passing var file
terraform apply -var-file=prod.tfvars

5. command to show folder structure
tree

