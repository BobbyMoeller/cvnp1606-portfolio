Bobby Moeller

Matt M

CVNP1606

11/16/2026

In this scenario, ACME is shifting to a cloud-first device management model. All new endpoints will be Entra joined and Intune-enrolled rather than joined to the on-premises domain. I have been assigned to prepare the pilot enrollment process: set up the required device groups, enroll one test endpoint, verify its join and management state, and design the pilot group structure for a phased rollout to the rest of ACME.

The first thing I did was to login into the Intune admin center and to make sure my tenant was ready. Then for the second step, I created two new groups, ACME-Pilot-Devices which was assigned and ACME-All-Devices, which was dynamic to have all new windows devices added to it. Then for step 3, I enrolled the Windows 11 VM in Entra and Intune, then I verified it by using the dsregcmd /status command. Then for step 4, I verified the Intune enrollment from the portal side by making sure the device was available in the admin portal. 

Evidence:
Screenshots Folder: Screenshots for each step.
join-state-evidence.md: Explanations for some fields from the dsregcmd /status output from Step 3.   
tenant-setup-notes.md: Tenant Name, Expiry Date, and info on the two device groups created.
enrollment-diagnosis.md: Diagnosed a failed enrollment.
pilot-group-design.md: A phased rollout plan for enrolling all 50 ACME endpoints over 4 weeks.

Portfolio Card: I was able to enroll a Windows machine into Entra ID and Intune, verified the state of enrollment with PowerShell commands, and designed a four-wave pilot rollout plan to help ACME migrate 50 endpoints to cloud-first management.
