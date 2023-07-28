A. Review the article at the link showing how GitHub is integrated into a CICD pipeline.
https://aws.amazon.com/blogs/devops/integrating-with-github-actions-ci-cd-pipeline-to-deploy-a-web-app-to-amazon-ec2/
* Go to the associated repository and study it - https://github.com/aws-samples/aws-codedeploy-github-actions-deployment
* Review the GitHub Actions workflow code
* Investigate how the deployment onto the EC3 instances is implemented.

1. The code below is taken from the repository in the questions above (A)  - it is used to bootstrap an EC2 server and install some applications.
Describe in details what it does.
```
#!/bin/bash

yum  install -y java-1.8.0-openjdk-devel wget
java -version
cd /usr/local
wget https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.43/bin/apache-tomcat-9.0.43.zip
wget https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.43/bin/apache-tomcat-9.0.43.zip.asc
wget https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.43/bin/apache-tomcat-9.0.43.zip.sha512

# verify hash / are these two outputs the same
cat apache-tomcat-9.0.43.zip.sha512
sha512sum apache-tomcat-9.0.43.zip

gpg --keyserver pgpkeys.mit.edu --recv-key A9C5DF4D22E99998D9875A5110C01C5A2F6059E7
gpg --verify apache-tomcat-9.0.43.zip.asc apache-tomcat-9.0.43.zip

# if hash and signature are ok:
unzip apache-tomcat-9.0.43.zip
mv apache-tomcat-9.0.43 tomcat9
echo 'JAVA_OPTS="$JAVA_OPTS -Djava.net.preferIPv4Stack=true -Djava.net.preferIPv4Addresses=true "' > /usr/local/tomcat9/bin/setenv.sh
ls -la tomcat9/
useradd -r tomcat
chown -R tomcat:tomcat /usr/local/tomcat9
ls -l /usr/local/tomcat9

echo "[Unit]
Description=Apache Tomcat Server
After=syslog.target network.target

[Service]
Type=forking
User=tomcat
Group=tomcat

Environment=CATALINA_PID=/usr/local/tomcat9/temp/tomcat.pid
Environment=CATALINA_HOME=/usr/local/tomcat9
Environment=CATALINA_BASE=/usr/local/tomcat9

ExecStart=/usr/local/tomcat9/bin/catalina.sh start
ExecStop=/usr/local/tomcat9/bin/catalina.sh stop

RestartSec=10
Restart=always
[Install]
WantedBy=multi-user.target" > /etc/systemd/system/tomcat.service

# firewall-cmd --zone=public --permanent --add-port=8080/tcp
# firewall-cmd --zone=public --permanent --add-port=8443/tcp
# firewall-cmd --reload
cd /usr/local/tomcat9/bin && chmod +x catalina.sh
systemctl daemon-reload
systemctl start tomcat.service
systemctl enable tomcat.service
systemctl status tomcat.service
yum install ruby -y
wget https://aws-codedeploy-${AWS::Region}.s3.${AWS::Region}.amazonaws.com/latest/install
chmod +x ./install
./install auto
cd /tmp
yum install -y https://s3.amazonaws.com/ec2-downloads-windows/SSMAgent/latest/linux_amd64/amazon-ssm-agent.rpm
systemctl enable amazon-ssm-agent
systemctl start amazon-ssm-agent
```

2. apt is a package manager on the ubuntu linux system. Desscribe what these commands do;
```
apt install
apt update
apt upgrade
apt list
apt remove
apt purge
```
###
- apt install: installs a package or software on the system.
- apt update: updates the package lists and information about available packages from the repositories.
- apt upgrade: upgrades all installed packages to their latest versions.
- apt list: displays a list of all available packages from the repositories.
- apt remove: removes a package or software from the system, but keeps its configuration files.
- apt purge: removes a package or software along with its configuration files.

3. These are some commonly used Linux commands. Describe what they do.
```
df 
du
lsblk
mount
umount
ln -s 
tar
rsync
```
###
- df: displays the disk space usage of the file system.
- du: estimates file space usage of a directory or files.
- lsblk: lists information about all available block devices, such as hard drives and USB drives.
- mount: mounts a file system to a specific directory in the file system hierarchy.
- umount: unmounts a mounted file system from its mount point.
- ln -s: creates a symbolic link between files or directories.
- tar: creates or extracts archived files in tar format.
- rsync: synchronizes files and directories between two locations, either locally or remotely.

4) What variable type does this satisfy: zones = ["us-central1-a", "us-central1-b", "us-central1-f"] ?
a) list(string)
b) list(list)
c) map(string)
d) list(map)
e) string
###
a) list(string)


5) Describe qualitatively the difference between these two statements in terms of the results they will produce.

* ```[for s in var.list : upper(s)]```
* ```{for s in var.list : s => upper(s)}```
###
The first statement uses a list comprehension to iterate over the elements in the "var.list" list and apply the "upper" function to each element, resulting in a new list of uppercase strings. The second statement uses a map comprehension to iterate over the elements in the "var.list" list and create a new map where each key is an element from the original list and each value is the uppercase version of that element. So, the difference between the two statements is that the first one produces a list of uppercase strings, while the second one produces a map with the original strings as keys and their uppercase versions as values.

6) What Terraform variable type does the following satisfy?
```
node_pools = [
    {
      name               = "default-node-pool"
      machine_type       = "n1-standard-2"
      min_count          = 1
      max_count          = 100
      disk_size_gb       = 100
      disk_type          = "pd-standard"
      image_type         = "COS"
      auto_repair        = true
      auto_upgrade       = true
      service_account    = "project-service-account@<PROJECT ID>.iam.gserviceaccount.com"
      preemptible        = false
      initial_node_count = 80
    },
]
```


7) What Terraform variable type does the following satisfy?
```
node_pools_oauth_scopes = {
    all = []

    default-node-pool = [
      "https://www.googleapis.com/auth/cloud-platform",
    ]
}
```

8) What Terraform variable type does the following satisfy?
```
node_pools_labels = {
    all = {}

    default-node-pool = {
      default-node-pool = true
    }
}
```

9) Terraform code is defined as follows. What values would you put in the placeholders 
XXXXXX and YYYYYY to make the dynamic block valid?
```
locals {
 disk_profiles = [{
  label = "disk",
  size = 30
  },{
  label ="disk1",
  size = 100,
 }]
}

dynamic “disk” {
 for_each = local.disk_profiles
  content {
  label = XXXXXX
  size  = YYYYYY
  thin_provisioned = true
  }
}
```

10) Terraform code is defined as follows. What values would you put in the placeholders 
XXXXXX and YYYYYY to make the dynamic block valid?

```
common_tags = {
 Name = "ddt_webapp_asg-dev"
 Environment = "dev”"
 Power = "auto"
 CostCentre = "100123"
 Department = "marketing"
 Project = "new-campaign"
 Deployment = "terraform"
}

dynamic "tag" {
 for_each = local.common_tags
 content {
  key = XXXXXX
  value = YYYYYY
  propagate_at_launch = true
 }
}
```

11) The Terraform code below contains some repeated block of code. Use dynamic block to make the code DRY (Don't Repeat Yourself).
```
resource "azurerm_virtual_network" "dynamic_block" {
  name                = "vnet-dynamicblock-example-centralus"
  resource_group_name = azurerm_resource_group.dynamic_block.name
  location            = azurerm_resource_group.dynamic_block.location
  address_space       = ["10.10.0.0/16"]

  subnet {
    name           = "snet1"
    address_prefix = "10.10.1.0/24"
  }

  subnet {
    name           = "snet2"
    address_prefix = "10.10.2.0/24"
  }

  subnet {
    name           = "snet3"
    address_prefix = "10.10.3.0/24"
  }

  subnet {
    name           = "snet4"
    address_prefix = "10.10.4.0/24"
  }
}


variable "subnets" {
  description = "list of values to assign to subnets"
  type = list(object({
    name           = string
    address_prefix = string
  }))
}

subnets = [
  { name = "snet1", address_prefix = "10.10.1.0/24" },
  { name = "snet2", address_prefix = "10.10.2.0/24" },
  { name = "snet3", address_prefix = "10.10.3.0/24" },
  { name = "snet4", address_prefix = "10.10.4.0/24" }
]
```
###
resource "azurerm_virtual_network" "dynamic_block" {
  name                = "vnet-dynamicblock-example-centralus"
  resource_group_name = azurerm_resource_group.dynamic_block.name
  location            = azurerm_resource_group.dynamic_block.location
  address_space       = ["10.10.0.0/16"]

  dynamic "subnet" {
    for_each = var.subnets
    content {
      name           = subnet.value.name
      address_prefix = subnet.value.address_prefix
    }
  }
}

variable "subnets" {
  description = "list of values to assign to subnets"
  type = list(object({
    name           = string
    address_prefix = string
  }))
}

subnets = [
  { name = "snet1", address_prefix = "10.10.1.0/24" },
  { name = "snet2", address_prefix = "10.10.2.0/24" },
  { name = "snet3", address_prefix = "10.10.3.0/24" },
  { name = "snet4", address_prefix = "10.10.4.0/24" }
]

