## Kubernetes, Docker, Containerisation and Virtualisation

My name is abiodunolajide

## Linux administration and shell scripting



## CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible


1. You want to use the following code to created an AWS EKS resource from the 
public repository pointed to by the source clause. Would could you ensure
that any changes made to the public repository you are pointing to does not
adversely affect your infrastructure?

```
module "myeks" {
source = "terraform-aws-modules/terraform-aws-eks"
cluster_name = "mycluster"
}
```


2. When you run the terraform init command in the directory containing terraform files, what 
changes does it make to directory in which you run the command?


3. What is the purpose of a Terraform provider?


4. What is the purpose of Terraform state?


5. How would you ensure that the Terraform state is secure and can be used in a collaborative
environment with the rest of your team without it being corrupted?


6. You have created a resource using Terraform. A colleague of your accidentally changed the resource
on the AWS console. What would happen if you run the Terraform apply command again?


7. You have a Terraform file in which you have defined 10 resources. You realise that one of the resources 
is no longer required. How would you go about deleting the unwanted resource without deleting the other resources?

8. What is a Terraform backend and how might you configure one?


9. Describe the various method by which Terraform might obtain credentials it needs for authenticating to an endpoint?


10. Your terraform code uses public external modules. What do you need to do to ensure that these external modules dependencies 
are resolved before you provision your resources?

11. You have provisioned some infrastructure in the AWS cloud using Terraform. How could you check by querying the state what 
resources you have created using Terraform?

12. What is the recommended approach for editing the Terraform state?

13. Describe as best as possible what the following code does.
```
terraform {
  backend "s3" {
    bucket   = "techoutcomes-terraforms.tfstate"
    key      = "simplegithubactions"
    region   = "eu-west-1"
  }
}
```

14. Describe as best as possible what the following code does.
```
provider "aws" {
  region = local.region
}
```



## System Architecture and Application Design, Cloud Computing (AWS)




## Site Reliability Engineering (SRE), Troubleshooting, Observability




## DevOps and Agile Transformation principles and methodology
