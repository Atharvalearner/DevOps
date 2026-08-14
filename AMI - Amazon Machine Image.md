AMI stands for Amazon Machine Image. It is a pre-configured template used to launch EC2 instances. It can contain an operating system, applications, and configuration required for the instance. An AMI includes information such as the root volume template, launch permissions, and block device mappings that specify the volumes to attach when the instance is launched. We must select an AMI when launching an EC2 instance. We can also create custom AMIs from configured EC2 instances, which is useful when we need to launch multiple identical servers quickly and consistently. AMIs can be EBS-backed or instance-store-backed.





**# AMI (Amazon Machine Image):**

* Operating System **used to create virtual machine** (EC2 instance)
* **a pre-configured template** used to launch virtual servers/machine, known as EC2 instances.
* It's **built for a specific region**.
* You can also create a custom AMI with required applications/configuration
* You must specify an AMI to launch an EC2 instance.
* AMI contains :

&#x09;- Template for root volume

&#x09;- Launch permissions

&#x09;- EBS (Block Device Mapping) mapping that specifies the volume(s) to attach the instance when its launched

* AMI comes into two types :

&#x09;- Instance store backed AMI

&#x09;- EBS backed AMI





**# You have configured one EC2 server and now you need five identical servers. What would you do?**

I would create a custom AMI from the configured EC2 instance. Then I would use that AMI to launch the other EC2 instances. This avoids manually installing and configuring the same software on every server and ensures consistency.

