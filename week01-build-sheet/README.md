Bobby Moeller
Matt M

CVNP1606

9/6/2026

In this scenario, I am a junior technician at Nexus Support Services. ACME is getting new branch-office computers, and my lead needs one clean Windows 11 VM baseline that can be reused for later troubleshooting. My job is to build the endpoint, verify the state of it, capture the evidence, and document the setup so another technician could repeat it. In this scenario, we had to use a variety of tools such as, an compatible computer, Windows 11 iso, git, github, and VMware.

The first step of this scenario was to create the windows 11 VM, I did this by making sure my computer met the specs provided, then downloading and installing VMware. Then I set up a VM with the provided Windows 11 iso provided and downloaded. Then the second step was to set up the new Windows 11 Out of Box Experience, in our new VM. I did that by setting it up to the parameters sat and created an local admin account called acme.com. Then the third step was to make sure our Windows image was updated. I did this by going to Windows settings, then to Windows update, then I updated all the things that needed updates. Then the fourth step was to create a standard test account. I did this by going into setting, then account, then creating a new local account, then I checked that account to make sure it did not have admin privileges. Then for step five, I had to capture the system inventory. I did this by using PowerShell to show me the machine name, Windows edition, OS build, and firmware type and output it into a text file called inventory.txt as you can see in this folder. Then for the last step, step six, I had to create a clean snapshot of the VM. I did this by going into VMware, opening the VM, going to the VM option at the top, then Snapshot, then take snapshot. 

Evidence List:
Step 1: A screenshot of the VM hardware summary showing edition, RAM, and disk size after Windows finishes installing and boots to the desktop.
Step 2: A screenshot of the Windows desktop with your username visible in the Start menu.
Step 3: A screenshot of Windows Update showing "You're up to date".
Step 4: Screenshots showing both accounts exist and that the test account is set to standard. (Took 2 screenshots labeled Step 4 Evidence Part 1 and Step 4 Evidence Part 2)
Step 5: A screenshot of the terminal output and I included inventory.txt in my submission folder.
Step 6: A screenshot of the snapshot manager showing the snapshot name and timestamp.

AI Disclosure: I did not use Ai for this assignment

Portfolio Card: I built and documented a Windows 11 VM baseline, so when troubleshooting you have a clean state that is known to be good.

