# tf-azure-lab

### AZURE CLI FOR cygwin
https://gist.github.com/avoidik/2ae9257240065a2b6733cc4f0c0e993f
### LAB URL
https://docs.microsoft.com/en-us/azure/terraform/terraform-create-vm-cluster-with-infrastructure

read -sp "Azure password: " AZ_PASS && echo && az.cmd login -u kononenkomi@gmail.com -p $AZ_PASS
az account show --query "{subscriptionId:id, tenantId:tenantId}"
Next, create separate credentials for Terraform.
az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/${SUBSCRIPTION_ID}"
az vm show --resource-group myResourceGroup --name myVM -d --query [publicIps] --o tsv

*Create "terraform.tfvars" and put your credentials here like:*
```
client_id       = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
client_secret   = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
tenant_id       = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
subscription_id = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
```