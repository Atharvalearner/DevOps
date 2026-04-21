\- Process of **creating a virtual version of a physical computing environment** using a layer of 

software called a **hypervisor.**



\- Instead of running directly on physical hardware, **multiple virtual machines (VMs) can share the same physical resources** (CPU, memory, storage, network). Each VM behaves like an independent computer with its own operating system and applications.



\# Hypervisor (Virtual Machine Monitor – VMM) :

&#x09;▪ The software layer that enables virtualization.

&#x09;▪ Types:

&#x09;	1. **Type-I (Bare-metal): Runs directly on host machine's physical hardware**

&#x09;		**-** It doesn't have to load an underlying OS

&#x09;		**-** more efficient and provides better performance

&#x09;		- It is best suited for enterprise computing or data centers

&#x20;			**-** e.g., VMware ESXi, Microsoft Hyper-V, Xen



&#x09;	2. **Type-II (Hosted): Runs on top of a host OS** 

&#x09;		**-** It is installed on top of an existing OS, and it's called a hosted hypervisor.

&#x09;		-  It relies on the host machine's pre-existing OS to manage calls to CPU, memory, storage and network resources.

&#x09;		- E.g. VMware Fusion, Oracle VM VirtualBox, Parallels and VMware Workstation



\# Virtual Machine (VM) :

&#x09;▪ A software-based emulation of a physical computer

&#x09;▪ Each VM has its own virtual CPU, memory, disk, and network interface



