## My name is Estdag Outcomer and please file below my submission
Pods are the smallest deployable units of computing that you can create and manage in Kubernetes
A container image is a ready-to-run software package containing everything needed to run an application
A Kubernetes node is a machine that runs containerized workloads as part of a Kubernetes cluster.
Control plane the sum of every action, task, and workflow that decides what path a data packet has to follow..
The Data plane in Kubernetes consists of workloads, scaled pods, and infrastructure components and will experience most computing actions

Linux administration and shell scripting
1.You have a shell script called addAccount.sh and you are trying to run the script but it is complaining that some permissions are missing. What would you do to fix that?

sudo chmod +x samplescript.sh

2.What Linux command would your use to find out what commands you have run in the past?

The history command in Linux is a built-in shell tool that displays a list of commands used in the terminal session.
3.Research the following Linux commands
chmod linux command
chmod +rwx filename to add permissions.
chmod -rwx directoryname to remove permissions.
chmod +x filename to allow executable permissions.
chmod -wx filename to take out write and executable permissions.

SCP is an acronym for Secure Copy Protocol. It is a command line utility that allows the user to securely copy files and directories between two locations usually between unix or linux systems.

ssh (SSH client) is a program for logging into a remote machine and
     for executing commands on a remote machine.  It is intended to
     provide secure encrypted communications between two untrusted hosts
     over an insecure network.

CICD, Infrastructure as as Code (IaC), Terraform, Packer and Ansible

Providers are the plugins that Terraform uses to manage those resources

2.What is the purpose of Terraform state?
Terraform state is used to effectively manage the infrastructure resources that are deployed and managed by the Terraform project.The primary purpose of Terraform state is to store bindings between objects in a remote system and resource instances declared in your configuration

3.How would you ensure that the Terraform state is secure and can be used in a collaborative environment with the rest of your team without it being corrupted?

Remote state management provides increased security for Terraform state ( . tfstate ) files. By storing the state file in a remote data store, such as Microsoft Azure Blob Storage or AWS S3, you can ensure that only authorized team members have access to the state file


7.You have a Terraform file in which you have defined 10 resources. You realise that one of the resources is no longer required. How would you go about deleting the unwanted resource without deleting the other rest.

To delete a specific resource, run the following command: Copy terraform destroy -target=resource_type

8.What is a Terraform backend and how might you configure one?

The state of the infrastructure resources managed by Terraform is stored in a backend, which can be a remote storage location such as Amazon S3

Run terraform init to configure your Terraform backend.

9.Describe the various method by which Terraform might obtain credentials it needs for authenticating to an endpoint?
Credentials can be provided by using the AWS_ACCESS_KEY_ID , AWS_SECRET_ACCESS_KEY ,  


[The `terraform graph` command](/terraform/cli/commands/graph) creates a visual
  representation of a configuration or a set of planned changes.
- [The `terraform output` command](/terraform/cli/commands/output) can get the
  values for the top-level [output values](/terraform/language/values/outputs) of
  a configuration, which are often helpful when making use of the infrastructure
  Terraform has provisioned.
- [The `terraform show` command](/terraform/cli/commands/show) can generate
  human-readable versions of a state file or plan file, or generate
  machine-readable versions that can be integrated with other tools.
- [The `terraform state list` command](/terraform/cli/commands/state/list) can list
  the resources being managed by the current working directory and workspace,
  providing a complete or filtered list.
- [The `terraform state show` command](/terraform/cli/commands/state/show) can print
  all of the attributes of a given resource being managed by the current working
  directory and workspace, including generated read-only attributes like the
  unique ID assigned by the cloud provider.
terraform state rm — Remove an item from the state file