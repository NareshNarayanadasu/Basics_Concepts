Terraform Architecture:


Terraform :
        
        Terraform is a popular infrastructure-as-code tool that allows you to automate the provisioning and management of infrastructure resources. It uses configuration files written in the HashiCorp Configuration Language (HCL) to define the desired state of your infrastructure
             Can create infra in almost all the virtual environments
            
                                Or
                                
        Terraform is a powerful and flexible tool that enables users to define and manage infrastructure resources in a reusable and automated way. 
        
         
        
        
 Infrastructure as a Code (IAC): 

        Infrastructure as Code (IaC) is a method of managing and provisioning IT infrastructure using code, rather than manual configuration. It allows teams to automate the setup and management of their infrastructure, making it more efficient and consistent.
        
Use Cases Of Terraform

        1. Provisioning Cloud Resources: Different types of cloud resources can be provisioned by using terraform like AWS,GCP, and others. The resources can be managed are compute, storage, networking, and application services.
        
        2. Multi-Cloud Management: You can manage the infrastructure of different cloud platform at a time which will helps you to maintain the multi-cloud or hybrid cloud environments.
        
        3. Infrastructure Versioning and Collaboration: You can store the scripts which have been written to provision the infrastructure in the version control system like git form where other teams can collaborate on infrastructure changes, track revisions, and roll back to previous states if needed.
        
        4. Automation and Continuous Integration/Continuous Deployment (CI/CD): You can also integrate the terraform into you CI/CD Pipelines. where ever the build is triggered if there is any changes the infrastructure will upgrades automatically.
        
Terraform Provider

        A software element known as a Terraform provider enables Terraform to communicate with a particular infrastructure platform. 
        
        
Work Of Terraform

        With Terraform, users can define infrastructure resources using a simple, declarative configuration language. These resources can include virtual machines, networking components, storage resources, and more. Once the configuration is defined, Terraform can be used to create, modify, and destroy these resources in a repeatable and predictable way.
        
        
         
        
Components of Terraform Architecture
        
        Configuration Files
            These files contain the definition of the infrastructure resources that Terraform will manage, as well as any input and output variables and modules. 
        State File
            The state file is used to track the resources that have been created, modified, or destroyed, and it is used to ensure that the infrastructure resources match the desired state defined in the configuration files.
            
        Providers
            Terraform integrates with a wide range of cloud and infrastructure providers, including AWS, Azure, GCP, and more. These providers allow Terraform to create and manage resources on those platforms.
            
            A provider is a Terraform plugin that allows users to manage an external API.
            
                
                
                terraform {
 required_providers {
   aws = {                      # provider local name
     source  = "hashicorp/aws"  # global and unique source address
     version = "~> 3.0"         # version constraint
     } 
    }
   }
                
                # Configure the AWS Provider
provider "aws" {
 region = "us-central-1" # provider configuration options
            
            
            Terraform resources: 
            
                Resources are the most important element in the Terraform language. It describes one or more infrastructure objects to manage.
                
                Terraform resources are components within a Terraform configuration that represent infrastructure objects or services that need to be managed.
                Resources in Terraform configurations define the desired state of various infrastructure elements, e.g. virtual machines, SQL databases, network security groups, etc.
                
                
                
                
            
            Terraform Variables :
            
                Input variables allow you customize aspects of Terraform without using hard-coded values in the source.
                
                Declaring a variable
                Variable declarations can appear anywhere in your configuration files. However, it's recommended to put them into a separate file called variables.tf.
                        # variable declaration
variable "vpc_cidr_block" {
   description = "CIDR block for VPC".
   default = "192.168.0.0/16"
   type = string
}
                Assigning values to variables
                    1. Using the default argument in the variable declaration block.
                    2. Assign a value to the variable in the variable definition file which by default is terraform.tfvars. Example: vpc_cidr_block = "172.16.0.0/16"
                    3. Using -var command-line option. Example: terraform apply -var="vpc_cidr_block=10.0.10.0/24"
                    4. Using -var-file command-line option. Example: terraform apply -auto-approve -var-file=web-prod.tfvars
                    5. Exporting the variable at the terminal. Example: export TF_VAR_vpc_cidr_block="192.168.100.0/24"
                Variable definition precedence (from highest to lowest):
                    1. Variables specified at the terminal using** -var** and -var-file options.
                    2. Variables defined in terraform.tfvars.
                    3. Variables defined as environment variables using TF_VAR prefix.
                String Interpolation
                You can interpolate other values in strings by these values in ${}, such as ${var.foo}.
                The interpolation syntax is powerful and allows you to reference variables, attributes of resources, call functions, etc.
                You can escape interpolation with double dollar signs: $${foo} will be rendered as a literal ${foo}.
                Variable Types
                    1. Simple types a. number b. string c. bool d. null
                    2. Complex types a. Collection types i. list ii. map iii. set b. Structural types i. tuple object
                type number
                        variable "web_port" {
    description = "Web Port"
    default = 80
    type = number
}
                type string
                        variable "aws_region" {
  description = "AWS Region"
  type = string
  default = "eu-central-1"
}
                type bool
                        variable "enable_dns" {
  description = "DNS Support for the VPC"
  type = bool
  default = true
}
                type list (of strings)
                        variable "azs" {
  description = "AZs in the Region"
  type = list(string)
  default = [ 
      "eu-central-1a", 
      "eu-central-1b", 
      "eu-central-1c" 
      ]
}
                type map
                        variable "amis" {
  type = map(string)
  default = {
    "eu-central-1" = "ami-0dcc0ebde7b2e00db",
    "us-west-1" = "ami-04a50faf2a2ec1901"
  }
}
                type tuple
                        variable "my_instance" {
    type = tuple([string, number, bool])  
    default = ["t2.micro", 1, true ]
}
                type object
                        variable "egress_dsg" {
    type = object({
        from_port = number
        to_port = number
        protocol = string
        cidr_blocks = list(string)
    })
    default = {
     from_port = 0,
     to_port = 65365,
     protocol = "tcp",
     cidr_blocks = ["100.0.0.0/16", "200.0.0.0/16", "0.0.0.0/0"]
    }
}
                
    
        Data sources:
            Data sources in Terraform are used to get information about resources external to Terraform. For example, the public IP address of an EC2 instance. Data sources are provided by providers.
        Use Data Sources
            A data block requests that Terraform read from a given data source ("aws_ami") and export the result under the given local name ("ubuntu").
            The data source and name together serve as an identifier for a given resource and therefore must be unique within a module.
            Within the block body (between { and }) are query constraints defined by the data source.
                data "aws_ami" "ubuntu" {
 most_recent = true
                owners = ["self"]
 tags = {
   Name   = "app-server"
   Tested = "true"
 }
}
        Output Values
            Output values print out information about your infrastructure at the terminal, and can expose information for other Terraform configurations (e.g. modules) to use.
            Declare an Output Value
            Each output value exported by a module must be declared using an output block. The label immediately after the output keyword is the name.
                output "instance_ip_addr" {
 value = aws_instance.server.private_ip 
}
            Loops
                Terraform offers the following looping constructs, each intended to be used in a slightly different scenario:
                    ® count meta-argument: loop over resources.
                    ® for_each meta-argument: loop over resources and inline blocks within a resource.
                    ® for expressions: loop over lists and maps.
            count
                The count meta-argument is defined by the Terraform language and can be used to manage similar resources.
                count is a looping technique and can be used with modules and with every resource type.
                # creating multiple EC2 instances using count
resource "aws_instance" "server" {
  ami = "ami-06ec8443c2a35b0ba"
  instance_type = "t2.micro"
  count = 3  # creating 3 resources
}
                In blocks where count is set, an additional count object is available.
            count.index represents the distinct index number (starting with 0) corresponding to the current object.
            for_each
            for_each is another meta-argument used to duplicate resources that are similar but need to be configured differently.
            for_each was introduced more recently to overcome the downsides of count.
            If your resources are almost identical, count is appropriate. If some of their arguments need distinct values that can't be directly derived from an integer, it's safer to use for_each.
                    # declaring a variable
variable "users" {
  type = list(string)
  default = ["demo-user", "admin1", "john"]
}
                    # creating IAM users
resource "aws_iam_user" "test" {
  for_each = toset(var.users) # converts a list to a set
  name = each.key
}
            For Expressions
                A for expression creates a complex type value by transforming another complex type value.
                    variable "names" {
    type = list
    default = ["daniel", "ada'", "john wick"]
}
            output "show_names" {
    # similar to Python's list comprehension
    value = [for n in var.names : upper(n)]
}
            output "short_upper_names" {
  # filter the resulting list by specifying a condition:
  value = [for name in var.names : upper(name) if length(name) > 7]
}
            If you run terraform apply -auto-approve you'll get:
            Outputs:
                short_upper_names = [
  "JOHN WICK",
]
show_names = [
  "DANIEL",
  "ADA'",
  "JOHN WICK",
]
        Splat Expressions
        A splat expression provides a more concise way to express a common operation that could otherwise be performed with a for expression.
        # Launch an EC2 instance
resource "aws_instance" "server" {
  ami = "ami-05cafdf7c9f772ad2"
  instance_type = "t2.micro"
  count = 3
}
        output "private_addresses"{
  value = aws_instance.server[*].private_ip  # splat expression
}
        Dynamic Blocks
        Dynamic blocks act much like a for expression, but produce nested blocks instead of a complex typed value. They iterate over a given complex value, and generate a nested block for each element of that complex value.
        They are supported inside resource, data, provider, and provisioner blocks.
        A dynamic block produces nested blocks instead of a complex typed value. It iterates over a given complex value, and generates a nested block for each element of that complex value.
        # Declaring a variable of type list
variable "ingress_ports" {
  description = "List Of Ingress Ports"
  type = list(number)
  default = [22, 80, 110, 143]
}
        resource "aws_default_security_group" "default_sec_group" {
  vpc_id = aws_vpc.main.id
        # Creating the ingress rules using dynamic blocks
 dynamic "ingress"{  # it produces ingress nested blocks
    for_each = var.ingress_ports # iterating over the list variable
    iterator = iport
    content {
        from_port = iport.value
        to_port = iport.value
        protocol = "tcp"
        cidr_blocks = ["0.0.0.0/0"]
     }
   }
}
        Conditional Expressions
        A conditional expression uses the value of a boolean expression to select one of two values.
        Syntax: condition ? true_val : false_val
        If condition is true then the result is true_val. If condition is false then the result is false_val.
        The condition can be any expression that resolves to a boolean value. This will usually be an expression that uses the equality, comparison, or logical operators.
        variable "istest" {
    type = bool
    default = true
}
        # Creating the test-server instance if `istest` equals true
resource "aws_instance" "test-server" {
  ami = "ami-05cafdf7c9f772ad2"
  instance_type = "t2.micro"
  count = var.istest == true ? 1:0  # conditional expression
}
        # Creating the prod-server instance if `istest` equals false
resource "aws_instance" "prod-server" {
  ami = "ami-05cafdf7c9f772ad2"
  instance_type = "t2.large"   # it's not free tier eligible
  count = var.istest == false ? 1:0  # conditional expression
}
        Terraform Locals
        Terraform local values or simply locals are named values that you can refer to in your configuration.
        Compared to variables, Terraform locals do not change values during or between Terraform runs and unlike input variables, locals are not submitted by users but calculated inside the configuration.
        Locals are available only in the current module. They are locally scoped.
        # the local values are declared in a single `locals` block
locals {
  owner = "DevOps Corp Team"
  project = "Online Store"
  cidr_blocks = ["172.16.10.0/24", "172.16.20.0/24", "172.16.30.0/24"]
  common-tags = {
      Name = "dev"
      Environment = "development"
      Version = 1.10
  }
}
        # Create a VPC.
resource "aws_vpc" "dev_vpc" {
  cidr_block = "172.16.0.0/16"
  tags = local.common-tags
} 
        # Create a subnet in the VPC
resource "aws_subnet" "dev_subnets" {
  vpc_id            = aws_vpc.dev_vpc.id
  cidr_block        = local.cidr_blocks[0]
  availability_zone = "eu-central-1a"
        tags = local.common-tags
}
        # Create an Internet Gateway Resource
resource "aws_internet_gateway" "dev_igw" {
  vpc_id = aws_vpc.dev_vpc.id  
  tags = {
    "Name" = "${local.common-tags["Name"]}-igw"
    "Version" = "${local.common-tags["Version"]}"
  }
}
        Note: Local values are created by a locals block (plural), but you reference them as attributes on an object named local (singular).
        Built-in Functions
        Terraform includes a number of built-in functions that can be called from within expressions to transform and combine values.
        Examples of functions: min, max, file, concat, element, index, lookup.
        Terraform does not support user-defined functions.
        There are functions for numbers, strings, collections, file system, date and time, IP Network, Type Conversions and more.
        You can experiment with the behavior of Terraform's built-in functions from the Terraform console, by running the terraform console command.
        Examples:
        > max(5, 12, 9)
12
        > min(12, 54, 3)
3
        > format("There are %d lights", 4)
There are 4 lights
        > join(", ", ["foo", "bar", "baz"])
foo, bar, baz
        > split(",", "foo,bar,baz")
[
 "foo",
 "bar",
 "baz",
]
        > replace("hello world", "/w.*d/", "everybody")
hello everybody
        > substr("hello world", 1, 4)
ello
        > element(["a", "b", "c"], 1)
b
        > lookup({a="ay", b="bee"}, "a", "what?")
ay
> lookup({a="ay", b="bee"}, "c", "what?")
what?
        > slice(["a", "b", "c", "d"], 1, 3)
[
 "b",
 "c",
]
        > timestamp()
"2022-04-02T05:52:48Z"
        > formatdate("DD MMM YYYY hh:mm ZZZ", "2022-01-02T23:12:01Z")
02 Jan 2022 23:12 UTC
        > cidrhost("10.1.2.240/28", 1)
10.1.2.241
        > cidrhost("10.1.2.240/28", 14)
10.1.2.254
        Backends and Remote State
        Backends
        Each Terraform configuration has an associated backend that defines how operations are executed and where the Terraform state is stored.
        The default backend is local, and it stores the state as a plain file in the current working directory.
        The backend needs to be initialized by running terraform init.
        If you switch the backend, Terraform provides a migration option which is terraform init -migrate-state.
        Terraform supports both local and remote backends:
            • local (default) backend stores state in a local JSON file on disk.
            • remote backends stores state remotely. Examples of remote backends are AzureRM, Consul, GCS, Amazon S3, and Terraform Cloud. They can support features like remote operation, state locking, encryption, and versioning.
        Configure Remote State on Amazon S3
            1. On the AWS console go to Amazon S3 and create a bucket.
            2. Configure Terraform to use the remote state from within the S3 bucket.
        terraform {
 backend "s3" {
   bucket = "bucket_name"
   key    = "s3-backend.tfstate"
   region = "eu-central-1"
   access_key = "AKIA56LJEQNM"
   secret_key = "0V9cw4CVON2w1"
 }
}
            1. Run terraform init to initialize the backend.
        Configure Remote State on Terraform Cloud
            1. The first step is to sign up for a free Terraform Cloud account.
            2. Create your organization or join a new one.
            3. Configure Terraform to use the remote state from within the S3 bucket.
        terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 3.0"
    }
  }
  cloud {
    organization = "master-terraform"  # should already exist on Terraform cloud
    workspaces {
      name = "DevOps-Production"
    }
  }
}
            1. Authenticate to Terraform Cloud to proceed with initialization.
            2. Run 'terraform login'.
            3. Run 'terraform init' to initialize the backend.
        Terraform Modules
        Terraform modules are a powerful way to reuse code and stick to the DRY principle, which stands for "Do Not Repeat Yourself". Think of modules as functions in a programming language.
        Modules will help you organize configuration, encapsulate configuration, re-use configuration and provide consistency and ensure best-practices.
        Terraform supports Local and Remote modules:
            • Local modules are stored locally, in a separate directory, outside of the root environment and have the source path prefixed with ./ or ../
            • Remote modules are stored externally in a separate repository, and support versioning. External Terraform modules are found on the Terraform Registry.
        A Terraform module is a set of Terraform configuration files in a single directory.
        When you run Terraform commands like terraform plan or terraform apply directly from such a directory, then that directory will be considered the root module.
        The modules that are imported from other directories into the root module are called child modules.
        Calling a child module from within the root module:
        module "myec2" {
  # path to the module's directory
  # the source argument is mandatory for all modules.
  source = "../modules/ec2"
        # module inputs
  ami_id = var.ami_id
  instance_type = var.instance_type
  servers = var.servers
}
        It's good practice to start building everything as a module, create a library of modules to share with your team and from the very beginning to start thinking of your entire infrastructure as a collection of reusable modules.
        After adding or removing a module, you must re-run terraform init to install the module.
        Troubleshooting and Logging
        The TF_LOG enables logging and can be set to one of the following log levels: TRACE, DEBUG, INFO, WARN or ERROR.
        Once you have configured your logging you can save the output to a file. This is useful for further inspection.
        The TF_LOG_PATH variable will create the specified file and append the logs generated by Terraform.
        Example:
        export TF_LOG_PATH=terraform.log
terraform apply
        
        From <https://zerotomastery.io/cheatsheets/terraform-cheat-sheet/> 
        
        
                
                
        
        
        
        
            
        
        
        
        


         
        
        
