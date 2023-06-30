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
Configure AWS setup 			\
Download the code into local system	
```
terraform init         			
terraform workspace new test  		
terraform workspace list   		
```

### Deploy in default workspace
```
terraform workspace select default
terraform apply --auto-approve 
```

### Deploy in test workspace
```
terraform workspace select test 
terraform apply --auto-approve
```
### Cleanup
```
terraform workspace select test
tearraform destory --auto-approve 

terraform workspace select default
tearraform destory --auto-approve 

terraform workspace delete test  
```
