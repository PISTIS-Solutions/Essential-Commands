# Terraform Command Lines
Terraform CLI Tricks
```sh

terraform -install-autocomplete
```
Setup tab auto-completion, requires logging back in

## Format and Validate Terraform Code
```sh

terraform fmt
```
## Format code per HCL canonical standard

```sh

terraform validate
```
## Validate code for syntax

```sh

terraform validate -backend=false
```
Validate code, skip backend validation

### Initialize Your Terraform Working Directory
```sh
terraform init
```
## Initialize directory, pull down providers

```sh

terraform init -get-plugins=false
```
Initialize directory, do not download plugins

```sh

terraform init -verify-plugins=false
```
Initialize directory, do not verify plugins for HashiCorp signature

## Plan, Deploy, and Cleanup Infrastructure
```sh
terraform apply --auto-approve
```


## Apply changes without being prompted to enter "yes"

```sh

terraform destroy --auto-approve
```

## Destroy/cleanup deployment without being prompted for "yes"

```sh
terraform plan -out plan.out
```
Output the deployment plan to plan.out

```sh

terraform apply plan.out

```
Use the plan.out plan file to deploy infrastructure

```sh
terraform plan -destroy
```
Outputs a destroy plan

```sh

terraform apply -target=aws_instance.my_ec2
```
Only apply/deploy changes to the targeted resource

```sh

terraform apply -var my_region_variable=us-east-1
```
Pass a variable via command-line while applying a configuration

```sh

terraform apply -lock=true
```
Lock the state file so it can't be modified by any other Terraform apply or modification action (possible only where backend allows locking)

```sh

terraform apply refresh=false
```
Do not reconcile state file with real-world resources (helpful with large complex deployments for saving deployment time)

```sh
terraform apply --parallelism=5
```
## Number of simultaneous resource operations

```sh
terraform refresh
```
## Reconcile the state in Terraform state file with real-world resources

```sh
terraform providers
```
Get information about providers used in current configuration

## Terraform Workspaces

```sh

terraform workspace new mynewworkspace
```
Create a new workspace

``` sh
terraform workspace select default
``` 

Change to the selected workspace

```sh
terraform workspace list
```
List out all workspaces

### Terraform State Manipulation
```sh

terraform state show aws_instance.my_ec2
```
Show details stored in Terraform state for the resource

```sh
terraform state pull > terraform.tfstate
``` 

### Download and output terraform state to a file

```sh
terraform state mv aws_iam_role.my_ssm_role module.custom_module
```
Move a resource tracked via state to a different module

```sh

terraform state replace-provider hashicorp/aws registry.custom.com/aws
```
Replace an existing provider with another

```sh

terraform state list
```
List out all the resources tracked via the current state file

```sh

terraform state rm aws_instance.myinstace
```
Unmanage a resource, delete it from Terraform state file

## Terraform Import and Outputs
```sh

terraform import aws_instance.new_ec2_instance i-abcd1234
```
Import EC2 instance with id i-abcd1234 into the Terraform resource named "new_ec2_instance" of type "aws_instance"

```sh

terraform import 'aws_instance.new_ec2_instance[0]' i-abcd1234
```
Same as above, imports a real-world resource into an instance of Terraform resource

```sh

terraform output
```
List all outputs as stated in code

```sh
terraform output instance_public_ip
```
List out a specific declared output

```sh

terraform output -json
```
List all outputs in JSON format

### Terraform Miscellaneous Commands
```sh

terraform version
```
Display Terraform binary version, also warns if version is old

```sh

terraform get -update=true
```
Download and update modules in the "root" module

### Terraform Console (Test Out Terraform Interpolations)
```sh

echo 'join(",",["foo","bar"])' | terraform console
```
Echo an expression into terraform console and see its expected result as output

```sh
echo '1 + 5' | terraform console
```
Terraform console also has an interactive CLI; just enter "terraform console"

```sh

echo "aws_instance.my_ec2.public_ip" | terraform console
```
Display the Public IP against the "my_ec2" Terraform resource as seen in the Terraform state file

### Terraform Graph (Dependency Graphing)
```sh
terraform graph | dot -Tpng > graph.png
```
Produce a PNG diagram showing relationships and dependencies between Terraform resources in your configuration/code

### Terraform Taint/Untaint (Mark/Unmark Resource for Recreation -> Delete and Then Recreate)
```sh

terraform taint aws_instance.my_ec2
```
Taints resource to be recreated on next apply

``` sh

terraform untaint aws_instance.my_ec2
```
Remove taint from a resource

```sh

terraform force-unlock LOCK_ID
```
Forcefully unlock a locked state file, LOCK_ID provided when locking the State file beforehand

## Terraform Cloud
```sh

terraform login
```
Obtain and save API token for Terraform cloud

```sh

terraform logout
```
Log out of Terraform Cloud, defaults to hostname app.terraform.io






