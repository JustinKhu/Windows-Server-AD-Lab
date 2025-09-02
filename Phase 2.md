**Overall Objective: Configure and create GPOs** 

**Objective 1:** Create and map shared and personal drives for a user. 

**Steps undertaken:** 

1. Opened Server Manager and created two shares named 'HR' and 'Personal' in the Shares tab.

2. Opened ADUC and created a 'HR' and 'Personal' security group in Users. Added the network path and a very short description (\Server2022\hr (shared folder)).

3. Added user account 'Patty' to both groups in the members tab. Verified by navigating to the user accounts properties in the 'Member of' tab to ensure that they were properly added to both groups.

4. Opening up properties from the 'HR' and 'Personal' folder shares and opening advanced security settings. Added 'helpdesk' user in the permission entry for both shares. Added the security group in permission entries for their respective settings (HR security group in Advanced Security Settings for HR).

5. Configured share options to allow read/write permissions for 'HR' security group.

6. Verified configuration success by logging onto the 'Patty' user on a second VM. Added the shared folder by opening the Map Network Drive menu and inputting the network path '\\Server2022\hr'. Ensure 'reconnect at sign-in' is checked to ensure the user connects to the shared folder every time they login.

7. Found 'Patty' user in ADUC and opened properties. Selected the option to connect a path and entered '\\SERVER2022\Personal\%username%' to create a folder for the desired user.

8. Verified this by signing out of the 'Patty' user account and checking that they indeed have access to a drive named 'Patty'. 


**Objective 2:** Configure GPO to enforce a standard wallpaper for users in a specific OU. 

**Steps Undertaken:** 

1. Create folder 'Wallpapers' and configured settings to share the folder on the network and allow everyone to have read permissions. Allowed Authenticated Users to have Read & execute permissions.

2. Added the share path on client VM '\\Server2022\Wallpapers'.

3. Open Group Policy management console in Server Manager. Navigated to Group Policy Object container and created new GPO named 'HR - Default Wallpaper'.

4. Opened Group Policy Management editor for the new GPO and configured wallpaper settings by adding the UNC path \\Server2022\Wallpapers\Capture.png.

5. Verified by logging onto the client user 'Patty' (which is in the HR OU). Opened cmd and entered 'gpupdate /force' followed by 'logoff' to enable the changes to be applied. 
