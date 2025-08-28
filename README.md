# Windows-Server-AD-Lab
A homelab project utilising Windows Server, Virtual Machines and Active Directory built to gain foundational knowledge on Active Directory to prepare for an entry-level Help Desk or similar role. This project will mainly focus on domain controllers, managing users/groups, and simulating common helpdesk tickets.  

**Lab Goals and Objectives:**

* Install and confingure a Windows User account and set up Windows Server as Domain Controller.
* Create user accounts, groups, and Organizational Units as well as manage their permissions.
* Set up and apply Group Policy Objects.
* Simulate and solve common helpdesk tickets such as password resetting, permission changes, and creating/deleteing user accounts.

**Lab Environment**

* Hypervisor: Oracle Virtualbox
* Server OS: Windows Server 2022
* Client OS: Windows 10
* Services Used: Active Directory Domain Services

**Phase 1: Setup and User Creation/Management** 

Created two Virtual Machine's, running Windows 10 and Windows Server. Setup Windows Server as Domain Controller and added Windows 10 VM to the domain. 


Created OUs for Users based off of department e.g. HR, IT. Created User accounts and added them to their respective OU. 


**Phase 2: Group Policy**

Configured account lockout policy to set maximum password age and account lockout threshold and duration.
