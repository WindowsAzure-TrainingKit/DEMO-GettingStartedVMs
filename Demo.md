<a name="title" />
# Getting Started with Windows Azure Virtual Machines #

---

<a name="Overview" />
## Overview ##
This demonstration shows how to get started creating and configuring Windows Azure Virtual Machines.

> **Note:** In order to run through this complete demo, you must have network connectivity and a Microsoft account.

<a id="goals" />
### Goals ###
In this demo, you will see three things:

1.	VM Creation
1.	VM Configuration 
1.	VM Connectivity 

<a name="technologies" />
### Key Technologies ###

This demo uses the following technologies:

- [Windows Azure Management Portal] [1]

[1]: https://manage.windowsazure.com/

<a name="setup" />
### Setup and Configuration ###

1.	Create a new Server 2012 virtual machine.
	1.	Create Empty Disk 1023 TB.
	1.	RDP into the machine and initialize and format the disk.
	1.	Launch Windows Firewall with Advanced Security.
	1.	Under Inbound Rules Enable both File and Printer Sharing Echo Request Rules.
1.	Create a new Linux VM and “connect” to the existing Server 2012 VM.

---

<a name="Demo" />
## Demo ##

This demo is composed of the following segments:

1. [Virtual Machine Creation](#segment1)
1. [Virtual Machine Configuration](#segment2)
1. [Virtual Machine Connectivity](#segment3)

<a name="segment1" />
### Virtual Machine Creation ###

1.	Show how to create a new Server 2012 virtual machine in the Windows Azure Management portal using the gallery experience but actually do not create it (skip the last wizard step and use the VM created in the setup section).

	![VM OS Selection](Images/vm-os-selection.png?raw=true "VM OS Selection")

	_VM OS Selection_

	> **Speaking Point**: Note that we support creation from images or disks. Note that the images can be custom images created by the owner of the subscription or they can be platform.

	> Note that we now support various Linux distros.


<a name="segment2" />
### Virtual Machine Configuration ###

1.	While the previous VM is provisioned switch to the VM that was previously booted.

1. RDP into the VM, start computer manager and disk management.

	> **Speaking Point**: Note that you have 1TB of storage. How do I get more? 

1. In the portal click Attach Empty Disk.

1. Type in 1023 and switch back to disk manager.

	> **Speaking Point**: Note that you just dynamically added an additional 1TB in storage.
	> An X-Large VM can have up to 16x1TB disks attached (Small is only 2x1TB disks)

	![Attacching an Empty Disk](Images/attacching-an-empty-disk.png?raw=true)

	_Attacching an Empty Disk_

1. Show how to create a new VM based on a Linux distro but do not actually create it  (skip the last wizard step and use the VM created in the setup section).

	![Creating a Linux VM](Images/creating-a-linux-vm.png?raw=true)

	_Creating a Linux VM_

1. Change from stand-alone to connect to existing VM and select the running Server 2012 VM.

	This will put the Linux VM on the same network as the server 2012 VM.

	![VM Mode](Images/vm-mode.png?raw=true "VM Mode")

	_VM Mode_

	> **Note:** 2-3 mins for boot - talk about another slide


<a name="segment3" />
### Virtual Machine Connectivity ###

1. Use Putty or another SSH client and connect to the Linux VM.

	![SSH Details](Images/ssh-details.png?raw=true "SSH Details")

	_SSH Details_

1. Ping the Server 2012 VM to demonstrate connectivity.

	![Ping to the new VM](Images/ping-to-the-new-vm.png?raw=true "Ping to the new VM")
	
	_Ping to the new VM_

---

<a name="summary" />
## Summary ##

In this demonstration, you have seen how to provision a virtual machine and dynamically add additional storage to the VM.  You have also seen how to add additional virtual machines to the same cloud service to establish direct network connectivity and name resolution. 