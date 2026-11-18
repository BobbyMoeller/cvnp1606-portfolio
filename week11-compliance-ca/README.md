Bobby Moeller

Matt M

CVNP1606

11/18/2026

In this scenario, Riley Chen, ACME branch manager, has escalated a concern to Jordan Lee, Nexus Support Services Lead Technician: several ACME remote employees, including Emily Park, are signing in to Microsoft 365 from personal devices and endpoints that have not been through the Intune enrollment process. ACME’s IT governance policy requires that only compliant, managed devices access company data. My job is to create or analyze a Windows compliance policy, connect it to Conditional Access logic in report-only mode, and document what would happen to a noncompliant device like Emily’s if the policy were enforced. I will also document Windows Hello for Business and LAPS as endpoint identity controls.

The first thing I did was to go to Intune and create the Windows compliance policy. This policy required that the devices have BitLocker enabled, OS version 10.0.19041 or newer, and Microsoft Defender Antimalware enabled. Then for the second step, I read the generated report to see what I got. Then for the third step, I went on Entra and created a new Conditional Access policy in report-only mode. Then for step four, I checked to see if my device had Windows Hello for Business enabled.


Evidence: 

Screenshot Folder:  Screenshots for each step

compliance-policy-summary.md

conditional-access-memo.md

laps-hello-note.md

security-exception-note-template.md


Portfolio Card: I was able to create a Windows compliance policy in Intune, then connect it to a Conditional Access policy in report-only mode and documented how noncompliance would affect remote employees how a security exception process should happen.
