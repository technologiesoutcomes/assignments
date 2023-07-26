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
* flatten
* toset

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

Read the associated link and describe how you might wnat to apply these Terraform concepts.


16.    A variable is defined as follows
```
variable "words" {
 type = object({
 nouns = list(string),
 adjectives = list(string),
 verbs = list(string),
 adverbs = list(string),
 numbers = list(number),
 })
 validation {
 condition = length(var.words["nouns"]) >= 5
 error_message = "At least 5 nouns must be supplied."
 }
}
```
Describe what is takes to correctly specify this variable.

17.    A variable is defined as follows. Add a default definition that satisfies the type.
```
variable "cluster_autoscaling" {
  type = object({
    enabled       = bool
    min_cpu_cores = number
    max_cpu_cores = number
    min_memory_gb = number
    max_memory_gb = number
    gpu_resources = list(object({ resource_type = string, minimum = number, maximum = number }))
    auto_repair   = bool
    auto_upgrade  = bool
  })
}
```

18. Describe what the following code does.
```
data "aws_ami" "ubuntu" {
  most_recent = true

  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-*"]
  }

  owners = ["099720109477"]
}
```

19. Describe what the following code does.
```
resource "aws_instance" "ansible_server" {
  ami                    = data.aws_ami.ubuntu.id
  instance_type          = "t3.micro"
  vpc_security_group_ids = [aws_security_group.allow_ssh.id]
  key_name               = aws_key_pair.key_pair.key_name

  tags = {
    Name = "Ansible Server"
  }

  provisioner "remote-exec" { #A
    inline = [
      "sudo apt update -y",
      "sudo apt install -y software-properties-common",
      "sudo apt-add-repository --yes --update ppa:ansible/ansible",
      "sudo apt install -y ansible"
    ]

    connection {
      type        = "ssh"
      user        = "ubuntu"
      host        = self.public_ip
      private_key = tls_private_key.key.private_key_pem
    }
  }
  
  provisioner "local-exec" { #B
    command = "ansible-playbook -u ubuntu --key-file ansible-key.pem -T 300 -i '${self.public_ip},', app.yml" 
  }
}
```

20.    Describe what the following code does.
```
data "aws_secretsmanager_secret_version" "db" {
  secret_id = var.secret_id
}

locals {
  creds = jsondecode(data.aws_secretsmanager_secret_version.db.secret_string)
}

resource "aws_db_instance" "database" {
  allocated_storage = 20
  engine            = "postgres"
  engine_version    = "12.2"
  instance_class    = "db.t2.micro"
  name              = "ptfe"
  username          = local.creds["username"]
  password          = local.creds["password"]
}
```
