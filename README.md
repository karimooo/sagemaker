## Machine Learning Infrastructure with Terraform

How to set up architecture with Machine Learning using `Amazon SageMaker` and `Terraform`. 

## Terraform version

Ensure your `Terraform` version 
```sh
$ cd main
$ terraform --version
```

## Setup steps

From `terraform` folder:
1. Copy `terraform_backend.tf.template` to `terraform_backend.tf` and modify values accordingly. You need to manually create an S3 bucket or use an existing one to store the Terraform state file.
2. Copy `terraform.tfvars.template` to `terraform.tfvars` and modify input variables accordingly. You don't need to create any buckets specified in here, they're to be created by terraform apply.
3. Run the followings:
```sh
export AWS_PROFILE=<your desired profile>

terraform init
terraform validate
terraform plan -var-file=terraform.tfvars
terraform apply -var-file=terraform.tfvars
```

## Clean up

```
terraform plan -destroy -var-file=terraform.tfvars
terraform destroy -var-file=terraform.tfvars
```

## License

This library is licensed under the Apache 2.0 License.
