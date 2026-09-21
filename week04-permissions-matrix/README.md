Bobby Moeller

Matt M

CVNP1606

9/20/2026

AI Disclosure: No AI was used for this scenario

In this scenario, ACME HR is moving payroll files to a dedicated shared folder on the ACME file server. Three groups need different levels of access: HR-Managers require Full Control, HR-Staff need Read and Write access , and Audit-Readonly needs Read-only. No other users should be able to access the share. The current default Everyone permission on the parent share must be removed before the share goes live. My job it to build the HR payroll share with group-based NTFS and share permissions, test effective accesss, and deliver a documented permissions matrix with ACL evidence.

The first step to do on my Windows 11 baseline is to create the three local groups that are needed: HR-Managers, HR-Staff, and Audit-Readonly. Then for the second step is to create the folder structure and share which the main one that you will see will be HR/Payroll. Then I remove the Everyone permissions from these, and record and export the current ACL as your before-state evidence. Then for the third step, I assigned the NTFS perms to the three groups using powershell, you can see who get what permissions on access-test-results.md, then I exported the updated ACL. Then for the fourth step, I signed into the HR-Staff account and tested its permissions on the payroll folder which you can see in access-test-results.md. 

Evidence List: 

Step 1: Screenshot of Get-LocalGroup output showing all three groups, and confirming hr-staff-test appears in HR-Staff but not in Administrators.

Step 2: acl-before.txt and a screenshot of Get-SmbShareAccess output confirming Everyone is not listed.

Step 3: Terminal screenshot of icacls output and Get-SmbShareAccess showing all three groups with correct permission levels. Also acl-after.txt

Step 4: Screenshots of each test outcome taken while signed in as hr-staff-test and access-test-results.md with all four test results recorded.

Portfolio Card: I built a secure HR folder share at ACME, assigned group-based NTFS and share permissions, tested effective access from a test account, and documented the permission model so it can be verifiable.

Troubleshooting Narrative

What went wrong, or what could realistically have gone wrong? 

When I created the HR Test account, I could not find it on the sign in screen.

What evidence did you check first?

I made sure it was a user in computer management

What did you try?

I added it to the user group

What fixed it, or what would you try next?

Adding it to the user group fixed it

How did you verify the result?

By being able to see the account on the login screen

What was the support or security impact of the issue or fix?

Support impact could be it generating support tickets. No security impact
