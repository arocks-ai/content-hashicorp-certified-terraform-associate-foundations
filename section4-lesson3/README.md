# Terraform Workspace demo on AWS deployment 

### main.tf 
AWS provider and EC2 VM resources. <br/>
NOTE -  ${terraform.workspace} variable decides what environment to deploy in <br/>
		default - prod env  <br/>
		test - test env <br/>

### network.tf 
Spins up the network resources required by EC2 VM <br/>
NOTE - ${terraform.workspace} variable to set their Names/IDs.


## Deployment
### Initial setup
Download the code into local system			 <br/>
terraform init         <br/>
terraform workspace new test  <br/>
terraform workspace list   <br/>

### Deploy in default workspace
terraform workspace select default  <br/>
terraform apply --auto-approve  <br/>
tearraform destory --auto-approve<br/>

### Deploy in test workspace
terraform workspace select test <br/>
terraform apply --auto-approve <br/>

### Cleanup
terraform workspace select test <br/>
tearraform destory --auto-approve <br/>

terraform workspace select test <br/>
tearraform destory --auto-approve  <br/>

terraform workspace delete test  <br/>
