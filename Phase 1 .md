**Objective: Install AD DS and join a client to the domain.** 


**Steps Undertaken:** 

1. Configure static IP address:

   * Interface: Ethernet0
   * IP address: 10.1.10.2
   * Subnet mask: 255.0.0.0
   * Default gateway: 10.1.10.1
   * Preferred DNS server: 10.1.10.2
   * Alternate DNS: 10.1.10.2
  
2. Install Active Directory Domain Service and promote to Domain Controller:

   * Navigated to Server Manager > Add roles and features
   * Installed as role-based and selected Active Directory Domain Services
   * Added new forest
   * Set domain name as KEVIN.com

3. Join client VM to server:

   * On Windows 10 VM set up static IP address
   * Navigated to system properties and joined KEVIN.com domain

4. Create Organizational Units and User accounts:

   * Moved to Active Directory Users and Computers
   * Created 'IT' and 'HR' OUs
   * Created 'helpdesk' and 'Patty' sample users
   * Moved 'Patty' to HR OU and 'helpdesk' to IT OU

5. Verification:

   * Navigated to Active Directory Users and Computers
   * Select view and turned on Advanced Features
   * Moved to the HR OU and selected the 'Patty' profile
   * Clicked on Attribute Editor and verified that logging onto the domain was successful by examining lastlogon details
