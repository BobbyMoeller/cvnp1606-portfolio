Bobby Moeller

Matt M

CVNP1606

9/13/2026

AI Disclosure: I did not use AI in this scenario

In this scenario, My computany that I am working for, ACME is onboarding a group of seasonal staff who need Windows access to complete their work but must not have administrator rights on their machines. My job is to create and configure the required accounts, audit local group membership, and write a short memo explaining how the access decisions were made.

The first step for this scenario was to restore the clean baseline made in week 1. Then for step two, I made a standard user account by going into computer management > local users and groups > users > new user. I named it seasonal-staff. By default, they are a standard user. Then on step 3 I logged out of my admin account and signed into the new account. In the new account, I tried to open an application as an administrator and recorded the UAC elevation prompt. Then for step 4, I logged back into my admin account and used PowerShell to audit the local group membership by using the commands Get-LocalUser, and Get-LocalGroupMember -Group "Administrators". Then I exported the results by using the Out-File and -Append command. Then for step 5, I created the least privilege memo called least-privilege-memo.md. 

Evidence List: 
Step 1: A screenshot of the Snapshot Manager on VM Ware and a screenshot of the desktop after loading the snapshot.
Step 2: A screenshot of the newly created standard user account and what group it is in.
Step 3: A screenshot of the UAC elevation prompt.
Step 4: A screenshot of the commands used to audit the local group membership and local-users-export.txt
Step 5: least-privilege-memo.md

Portfolio Card: I created and audited local Windows accounts that can be used for seasonal staff and other temp workers, tested how UAC elevation behavior works in a Windows 11 enviornment, and wrote a memo explaining why each access decision protects endpoints.
