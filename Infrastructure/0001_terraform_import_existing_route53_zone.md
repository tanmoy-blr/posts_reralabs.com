### Introduction

During the initial provisioning of [reralabs.com](https://reralabs.com), a lot of Route-53 entries on AWS were done manually.
This was required for quick feedback loops.

As we gather user-input and standardize the infrastructure components,
we want to organize and manage infrastructure-code using Terraform.

We have to bring the existing infra into the control-plane of Terraform. 

Please refer to the example below, focusing on Route53 infra resources

#### Import existing Route-53 for [reralabs.com](https://reralabs.com) into Terraform

1. Create a module for Route53 zone in `main.tf`

    ![img_3.png](img_3.png)

2. Perform `terraform import -var-file=uat.tfvars module.<module_name>.aws_route53_zone.<zone_name> Z00XXXX00XX` on the CLI

    ![img.png](img.png)


3. Once `import` is successful, the new module will become in-scope.

   ![img_1.png](img_1.png)

4. We can now `add/modify` Route53 records using terraform

    ![img_2.png](img_2.png)




