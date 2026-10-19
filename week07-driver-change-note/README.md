Bobby Moeller

Matt M

CVNP1606

10/18/2026

AI Disclaimer: Did not use AI in this scenario

In this scenario, I am a junior technician at Nexus Support Services. ACME's office manager, Alex Torres, reports that last Tuesday's Windows Update knocked out two devices in the main office: the HP LaserJet printer and a USB headset used for calls. Both need to be working before end of day. Your lead has asked you to investigate the driver state, make a safe remediation decision, and document the change with a rollback plan so another technician could reverse it if needed.

The first step I took was to read the device manager and recording what the problem was, a disabled audio driver. Then for step 2, I ran a PowerShell command, Get-PnpDevice | Where-Object {$_.Status -ne "OK"} to get the driver with problems. The audio driver showed and error. Then for step 3, I looked at the driver version, date, and Hardware ID in Device Manager and recorded it. Then for step 4, I check to see if I could roll back the driver (I couldn't) and thought of what options I had. Then for step 5, I made to choice to reenable the drive and documented it in change-note.md. Then for step 6, I made sure to make sure the device was working after that change. Then lastly for step 7, I wrote a rollback plan incase if anything went wrong. 

Portfolio Card: I can identify a driver problem after a update, roll back a driver safely, and write a change note and rollback plan so the team could reverse the fix if it caused new problems.

Evidence List: 

Screenshots: Labeled with what step they go to.

change-note.md: The change note.

hardware-inventory.txt: Inventory of the problem device.

rollback-plan.md: My rollback plan.


Troubleshooting Narrative:

What could realistically have gone wrong? A display driver crashed, which caused the graphics card to stop working.

What evidence did you check first? I checked device manager and saw a red X.

What did you try? I uninstalled the driver and restarted the computer

What fixed it, or what would you try next? Installing the newest driver fixed the problem.

How did you verify the result? Looking at device manager to make sure the device status is ok.

What was the support or security impact of the issue or fix? This fix restored the display which is crucial to productivity.



