**Objective: Simulate common IT helpdesk tickets and issues that are commonly encountered in the workplace.**

**Tickets** 

**1. Scenario:** A user requests help as they are locked out of their account. 

**Solution:** Open ADUC and find the user account for the user. In this case 'Patty'. Open the menu for the user account and navigate to the 'account' tab. Check the box to unlock their account. 

**Verification:** In a real world example ask the user to try logging in again. In this scenario, attempted to login as 'Patty' on VM. 

**2. Scenario:** A user has changed their contact information and needs it updated in the system. 

**Solution:** Open ADUC and search for the user account using the search function (searching the entire domain). Open the acccount properties and fill in the updated information in the general, address, and Organization tabs. 

**Verification:** Click Apply and OK. Close and reopen the tab to ensure the changes were saved. 

**3. Scenario:** The user has requested that their password be reset as they have forgotten it. 

**Solution:** Open ADUC and search for the user. Right-click on their account and select 'Reset password'. Set a new password and ensure the checkbox that forces the user to create a new password at next logon is selected. Tell the user their temporary password and that they can change it immediately upon logon. 

**Verification:** Open up command prompt and enter the command 'net user patty /domain'. The following output will reveal information regarding their password. 

**4. Scenario:** A consultant/contract worker has joined the company. I'm tasked with creating a user account for them and delegating permissions in order for them to perform their role. 

**Solution**: Created a new OU named 'Consultants' and created a user 'Scott' in that OU. Opened delegation control in ADUC, added user 'Scott' and delegated control to allow for resetting user passwords and forcing password changes. 

**Verification:** Logged in as 'Scott' user and opened ADUC. Opening the properties of another user account showed that certain options such as setting account expiry and unlocking accounts were unavailable. 


**5. Scenario:** Patty from HR needs access to employee data to perform her job. 

**Solution:** Created a new security group named 'Employee Data' in ADUC inside the 'HR' OU. In the actual Employee Data folder located on the server, opened properties and enabled Sharing in the advanced settings. Then added the security group as an authenticated user and checked 'Read, List folder contents, Read & execute'. Edited the security group in ADUC to add user 'Patty' as a member of the group. 


**Verification:** Logged in as user 'Patty'. Used gpupdate /force in the command prompt. Signed out and back in and entered the UNC path '\\\Server2022\Employee Data$'. 
