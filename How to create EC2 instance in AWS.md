To create an EC2 instance in AWS, I first log in to the AWS Management Console and navigate to the EC2 service. I click 'Launch Instance', provide a name for the instance, select an Amazon Machine Image (AMI) such as Amazon Linux 2 or Ubuntu, choose an appropriate instance type like t2.micro or t3.micro, create or select an existing key pair for SSH access, configure the network by selecting a VPC and subnet, assign a security group to allow required traffic such as SSH (port 22) and HTTP (port 80), configure storage, review the settings, and then launch the instance. Once the instance reaches the Running state, I connect to it using SSH with the private key.



***# Why is a Key Pair required?***

The key pair is used for secure SSH authentication. AWS stores the public key on the instance, while the user keeps the private key locally. During SSH login, the keys are used to authenticate without sending a password.



***# Why we use chmod 400 privatekey.pem?***

Because the OpenSSH client strictly requires that your private key files are completely inaccessible to other users on your system.

***400 means*** - 4: Read-only access to owner and 00: No access to Group and Others Users.



***# What is the difference between a Private IP and a Public IP?***

Private IP: Used for communication within the VPC.

Public IP: Used for communication over the internet.



***# What Happens Internally?***

When you click Launch, AWS performs these steps:



*Launch Request*

&#x20;       *↓*

*Select Physical Host*

&#x20;       *↓*

*Allocate CPU \& RAM*

&#x20;       *↓*

*Attach EBS Volume*

&#x20;       *↓*

*Attach ENI (Network Interface)*

&#x20;       *↓*

*Assign Private IP*

&#x20;       *↓*

*Assign Public IP (if enabled)*

&#x20;       *↓*

*Configure Security Group*

&#x20;       *↓*

*Boot AMI*

&#x20;       *↓*

*EC2 Running*



***# Component Summary:***

AMI → selects the operating system.

Instance type → determines CPU and memory.

Key pair → enables secure SSH authentication.

VPC/Subnet → determines the network placement.

Security Group → controls inbound and outbound traffic.

EBS → provides persistent storage.

