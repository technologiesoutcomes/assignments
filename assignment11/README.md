# Assignment11

1.  Clone the following repository and use it as a model for some of your Terraform codebase.
```
https://github.com/terraform-in-action/manning-code.git
```

2.  A Terrafrom variable is defined as follows;
```
variable "servers" {
    type = list(object({
        name  = string,
        size = string,
        image = string,
        region = string
        tags = list(string)
    }))
}
```
Redefine the above variable, specifying a default value.

3.  A variable is defined as follows:
```
variable "servers" {
    type = list(object({
        name  = string,
        size = string,
        image = string,
        region = string
        tags = list(string)
    }))
}
```

Specify a variable that contains at least two objects in the list that satisfy this variable definition.

4. A variable is defined as follows:
```
variable "mapmap" {
  type        = map(map(string))
}
```
Redefine the variable to include a default with values that satisfy the type definition.

5. A variable is defined as follows:
```

variable "node_pools_oauth_scopes" {
  type        = map(list(string))
  description = "Map of lists containing node oauth scopes by node-pool name"

  # Default is being set in variables_defaults.tf
  default = {
    all               = ["https://www.googleapis.com/auth/cloud-platform"]
    default-node-pool = []
  }
}

```
Specify some values the satisfy this type definition.

6. Discuss how these features could be used to create multiple resources in Terraform
*  count
*  for_each

7.  What is a Terraform provisioner typically used for? Provide some sample code of its use.

8.  Which Terraform resource would you use to retrieve information from an existing infrastructure?

9.  Describe how you could use Terraform to manage resources created outside of Terraform.

10.   Below are some of the most commonly used Terraform Functions. Describe what each one does.
     
* try
* coalesce
* merge
* join
* lookup
* distinct
* concat
* jsonencode
* compact
* contains

11.  Describe why you might want to use the Terraform null_resource.

12. Install the cowsay command (sudo apt install cowsay). Put the code below in a file and run "terraform apply" and observer its reponse.
Then run "terraform destroy" and observe the output.
```
resource "null_resource" "cowsay" {
 provisioner "local-exec" {
 command = "cowsay Hello World!"
 }
 provisioner "local-exec" {
 when = destroy
 command = "cowsay -d Goodbye cruel world!"
 }
}
```

13.  Describe a use case where you might want to use a provider alias.

14.  Describe why you might use the clause "depends_on" in the definition of a Terraform resource.


15. Complex statements and logic

* for   -  https://developer.hashicorp.com/terraform/language/expressions/for
* splat -  https://developer.hashicorp.com/terraform/language/expressions/splat
* dynamic block  -  https://developer.hashicorp.com/terraform/language/expressions/dynamic-blocks

Read the associate link and describe how you might wnat to apply these Terraform concepts.


