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
####
variable "servers" {
  type = list(object({
    name  = string,
    size = string,
    image = string,
    region = string
    tags = list(string)
  }))
  default = [
    {
      name = "server1"
      size = "small"
      image = "ubuntu"
      region = "us-west-1"
      tags = ["web", "dev"]
    },
    {
      name = "server2"
      size = "medium"
      image = "centos"
      region = "us-east-2"
      tags = ["db", "prod"]
    }
  ]
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
###
variable "my_servers" {
  type = list(object({
    name  = string,
    size = string,
    image = string,
    region = string
    tags = list(string)
  }))
  default = [
    {
      name = "web-server"
      size = "small"
      image = "ubuntu"
      region = "us-west-1"
      tags = ["web", "dev"]
    },
    {
      name = "db-server"
      size = "medium"
      image = "centos"
      region = "us-east-2"
      tags = ["db", "prod"]
    }
  ]
}

4. A variable is defined as follows:
```
variable "mapmap" {
  type        = map(map(string))
}
```
Redefine the variable to include a default with values that satisfy the type definition.
###
variable "mapmap" {
  type        = map(map(string))
  default     = {
    west-coast = {
      us-west-1 = "California"
      us-west-2 = "Oregon"
    }
    east-coast = {
      us-east-1 = "Virginia"
      us-east-2 = "Ohio"
    }
  }
}

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
###


6. Discuss how these features could be used to create multiple resources in Terraform
*  count
*  for_each
###
The "count" and "for_each" features can be used to create multiple resources in Terraform by iterating over a list or map and creating a resource for each item. For example, if you had a list of server configurations, you could use the "count" feature to create a resource for each server:
resource "aws_instance" "server" {
  count = length(var.server_configs)
  ami = var.server_configs[count.index].ami
  instance_type = var.server_configs[count.index].instance_type
  # ...
}

Alternatively, you could use the "for_each" feature to create a resource for each key-value pair in a map:
resource "aws_instance" "server" {
  for_each = var.server_configs
  ami = each.value.ami
  instance_type = each.value.instance_type
  # ...
}

7.  What is a Terraform provisioner typically used for? Provide some sample code of its use.
###
A Terraform provisioner is typically a resource used to perform actions on a resource after it has been created or updated. For example, you might use a provisioner to install software on a virtual machine after it has been launched. Here is an example of using the "remote-exec" provisioner to run a shell command on an EC2 instance:
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  provisioner "remote-exec" {
    inline = [
      "sudo apt-get update",
      "sudo apt-get install -y nginx",
      "sudo service nginx start"
    ]
  }
}


8.  Which Terraform resource would you use to retrieve information from an existing infrastructure?
###
The Terraform data resource can be used to retrieve information from an existing infrastructure. For example, you might use the "aws_instance" data resource to retrieve information about an EC2 instance:
data "aws_instance" "example" {
  instance_id = "i-0123456789abcdef0"
}

9.  Describe how you could use Terraform to manage resources created outside of Terraform.
###
 To manage resources created outside of Terraform, you can use the Terraform "import" command to import the existing resource into your Terraform state file. Once the resource is imported, you can manage it like any other Terraform resource. For example, if you had an existing EC2 instance that you wanted to manage with Terraform, you could run the following command:
terraform import aws_instance.example i-0123456789abcdef0

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
###
- The "try" function attempts to evaluate an expression and returns a default value if the evaluation fails.
- The "coalesce" function returns the first non-null value in a list of expressions.
- The "merge" function merges two or more maps into a single map.
- The "join" function concatenates a list of strings into a single string, with a separator between each element.
- The "lookup" function retrieves the value of a specified key from a map, or returns a default value if the key is not found.
- The "distinct" function returns a list with duplicates removed.
- The "concat" function concatenates two or more lists into a single list.
- The "jsonencode" function converts a value to a JSON string.
- The "compact" function removes null and empty values from a list.
- The "contains" function returns true if a specified element is in a list, or false if it is not.
- The "flatten" function flattens a nested list into a single list.
- The "toset" function converts a list to a set, removing duplicates.

11.  Describe why you might want to use the Terraform null_resource.
###
The Terraform null_resource is typically used as a placeholder resource that does not create or manage any infrastructure. Instead, it can be used to trigger provisioners or other actions that need to happen outside of the normal resource lifecycle. For example, you might use a null_resource to run a script or execute an API call after other resources have been created.

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
###
 A use case for using a provider alias is when you have multiple providers of the same type, but with different configurations, and you want to differentiate between them in your Terraform code. For example, if you have two AWS accounts that you need to manage, you can define two provider blocks with different aliases, and then use the alias in your resource blocks to specify which provider to use.

14.  Describe why you might use the clause "depends_on" in the definition of a Terraform resource.
###
The "depends_on" clause is used to specify dependencies between resources in Terraform. If a resource depends on another resource, Terraform will ensure that the dependent resource is created before the dependent resource. This can be useful when you have resources that require other resources to be created first, such as a database server that needs a network security group to be created before it can be launched.


15. Complex statements and logic

* for   -  https://developer.hashicorp.com/terraform/language/expressions/for
* splat -  https://developer.hashicorp.com/terraform/language/expressions/splat
* dynamic block  -  https://developer.hashicorp.com/terraform/language/expressions/dynamic-blocks

Read the associated link and describe how you might wnat to apply these Terraform concepts.
###
The "for" expression in Terraform can be used to iterate over a list or map and perform a specific action for each item in the list or map. This can be useful for creating multiple resources based on a single definition, such as creating multiple EC2 instances with different configurations.

The "splat" expression in Terraform can be used to extract values from lists or maps and use them in other expressions. This can be useful for passing dynamic values between resources, such as passing the IP addresses of a set of EC2 instances to a load balancer.

The "dynamic block" in Terraform allows you to create multiple instances of a block based on a list or map. This can be useful for creating multiple resources with similar configurations, such as creating multiple security groups with different rules based on a list of ports and protocols.


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
###
To correctly specify this variable, we need to define an object type that has five fields: nouns, adjectives, verbs, adverbs, and numbers. Each field should be a list of strings or numbers, depending on the field. Additionally, we need to include a validation block that checks if the length of the nouns list is at least 5. If the condition is not met, an error message will be displayed. This ensures that the variable is being used correctly and meets the requirements specified by the validation block.

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
###
To add a default definition that satisfies the type, we would need to provide values for each of the fields defined in the object type. For example:


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
  default = {
    enabled       = true
    min_cpu_cores = 1
    max_cpu_cores = 10
    min_memory_gb = 2
    max_memory_gb = 16
    gpu_resources = [{ resource_type = "nvidia-tesla-k80", minimum = 0, maximum = 4 }]
    auto_repair   = true
    auto_upgrade  = true
  }
}


This provides default values for each of the fields in the object type.

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
###
 The code defines a Terraform data resource that retrieves the most recent Amazon Machine Image (AMI) for an Ubuntu server from the AWS Marketplace. It filters the results to include only AMIs with the specified name pattern and owned by the specified AWS account.

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
###
 The code defines a Terraform resource for an AWS EC2 instance that uses the AMI ID retrieved by the "aws_ami" data resource. It specifies the instance type, security group, key pair, and tags for the instance. It also includes two provisioners: 

- The first provisioner is a "remote-exec" provisioner that runs a series of shell commands on the instance after it is launched. The commands install Ansible on the instance.
- The second provisioner is a "local-exec" provisioner that runs a command on the local machine after the instance is launched. The command runs an Ansible playbook on the newly launched instance.

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
###
The code defines a Terraform data resource that retrieves a secret from AWS Secrets Manager and decodes it as a JSON object. The decoded object is stored in a local variable called "creds". 

The code also defines a Terraform resource for an AWS RDS database instance that uses the decoded credentials to set the username and password for the database. It specifies the allocated storage, database engine, engine version, instance class, and name for the database instance.
