Bobby Moeller

Matt M

CVNP1606

10/19/2026

AI Disclaimer: Did not use AI in this scenario

In this scenario, I investigated Windows event logs, built a chronological event timeline, and write a defensible root-cause analysis that can be presented to a auditor.

For the first step, I restored my clean Windows 11 baseline. Then for step 2, I went through Event Viewer to look and learn the different log types. Then for step 3, I filtered the logs for critical and error event. Because this scenario wants events 6008 and 41, I used to power off function in VMware to simulate an unexpected shutdown. Then for step 4, I used the PowerShell command, Get-WinEvent, to get the system log by those two event ids. Then for step 5, I built the event timeline on event-timeline.md, which showed when the events happened and more about them. Then lastly for step 6, I wrote the root cause analysis which you can see below. 

Portfolio Card: I am able to use Event Viewer and PowerShell commands such as Get-WinEvent, to be able investigate an unexpected reboot. I also am able to build an event timeline, and write a root-cause analysis that can be used for an audit.


Evidence List: 

Screenshots: Labeled which the correlating step.

event-export.txt: The two events 41 and 6008.

event-timeline.md: Timeline and more about these events.


Root-Cause Analysis:

Hypothesis: My hypothesis is that this system experienced an unexpected shutdown which could be caused by a power interruption or a forced power off. 

Supporting Evidence: The two main events that happened at 10:58PM (41) and 11:00PM (6008) both correlate to a system that has experienced unexpected shutdown.

Alternative Causes Considered: Another possible cause of this could be where the CPU overheats so much that the system will cut power to save itself. I don't think this is the case because the computer would shut down after a few minutes of operation every time it was on if that was the case.

Escalation Note: You should escalate if you see temps on the CPU or GPU over 100 degrees C, all software problems are ruled out, or the problem persists after remediation. 


