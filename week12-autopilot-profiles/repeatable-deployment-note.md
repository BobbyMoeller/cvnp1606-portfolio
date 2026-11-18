Repeatable Deployment Procedure: Windows Baseline Screen Saver & Camera Profile



Deployment & Verification Steps:

1. Open the Intune Configuration menu: Sign in to the Microsoft Intune admin center  and navigate to Devices → Manage devices → Configuration.
2. Initialize a new profile: Click + Create → New Policy. In the right-hand pane, select Windows 10 and later for Platform and Settings catalog for Profile type, then click Create.
3. Name the profile: On the*Basics tab, enter a clear name and a brief description noting the baseline security purpose, then click Next.
4. Add Personalization settings: On the Configuration settings tab, click + Add settings. In the Settings picker, search for screen saver and select Administrative Templates → Control Panel → Personalization. Check the boxes next to Prevent changing screen saver (User) and Screen saver timeout (User).
5.Configure Screen Saver values: In the main configuration pane on the left, set Prevent changing screen saver (User) to Enabled, set Screen saver timeout (User) to Enabled, and enter 900 in the Seconds: (User) field.
6. Add and configure Camera Privacy settings: In the Settings picker, search for Let Apps Access Camera, select the Privacy category, and check Let Apps Access Camera. Close the Settings picker, set the Let Apps Access Camera dropdown to User in control., and click Next.
7. Bypass Scope tags: On the Scope tags tab, leave the default setting unchanged and click Next.
8. Assign the profile to the Pilot group: On the Assignments tab, under Included groups, click Add groups. Search for and select ACME-Pilot-Devices, then click Select. Confirm that Filter and Filter mode remain set to None, then click Next.
9. Review and deploy: On the Review + create tab, verify that all three settings (Enabled, 900, and User in control.) and the ACME-Pilot-Devices assignment are listed correctly, then click Create.
