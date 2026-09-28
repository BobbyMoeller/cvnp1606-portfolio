Bobby Moeller

Matt M

CVNP1606

9/6/2026

AI Disclaimer: Did not use AI in this scenario


In this scenario, I am a junior technician at Nexus Support Services. Riley Chen, ACME's branch manager, has submitted a helpdesk ticket reporting that her meeting workstation freezes for 10 to 15 seconds when switching applications. The problem is worst during the first 10 minutes after login. My lead has asked Nexus to investigate the endpoint, identify the bottleneck using evidence, apply one safe remediation, and document the before and after state so the fix can be reviewed or replicated by another technician.


The first step of this scenario was to restore my Windows 11 baseline. Then I used this PowerShell script to simulate startup congestion, 1..4 | ForEach-Object { Start-Job -ScriptBlock { while ($true) { $x = 1..1000 | Measure-Object -Sum } } } Then I let it run for 5 mins to let the computer reach a slow state. Then using a combination of Task Manager, PowerShell, and with step 2, resource manager, get the metric before I try to remedy the situation. Then for step 3, we saw if any startup apps were causing problems but since the PowerShell script did not make a startup app there were no startup app that were causing a problem. Then for step 4, I found the bottleneck, which was the CPU, and formed a hypothesis. Then for step 5, I applied a remedy, which was closing the PowerShell processes and document what I did like I did in Step 1 for the final step, 6.


Evidence: A group of screenshot that are labeled for each step. They can be found in the [Screenshot Folder](week05-performance-report/Screenshots)


Portfolio Card: I diagnosed a slow Windows endpoint using Task Manager, Resource Monitor, and PowerShell evidence, identified a startup congestion bottleneck, applied a remediation the would be safe for the user, and documented the before and after state for a simulated branch manager's meeting workstation.


Troubleshooting Narrative: 


What performance symptom did you observe or simulate, and what was the business impact for Riley? 

I simulated a CPU bottleneck, and it impacted the ability for Riley to compete work at a good pace. 


What evidence did you check first, and what did it show?

I checked the processes in Task Manager, and it showed that PowerShell was taking most of the CPU.


What was your bottleneck hypothesis, and what specific metric supported it?

That the PowerShell processes where causing it and the proof was the high CPU load.


What remediation did you apply, and why was it safe to do without escalating?

I ended the PowerShell; this was safe because it saved the work before closing.


How did you verify the result, and did the metrics improve?

I verified it by using Task Manger and it did improve the CPU load.


What would you do if the metrics did not improve after your remediation?

Look at other processes or start up apps.
