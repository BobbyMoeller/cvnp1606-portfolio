Bobby Moeller

Matt M

CVNP1606

10/5/2026

In this scenario, Emily Park is a remote ACME employee who works from home. She contacted the helpdesk this morning saying she cannot reach the ACME intranet or access shared drives. She can load some external websites but cannot get to any ACME resources. Her laptop was working normally yesterday. Emily is not technical and will need step-by-step guidance if she is expected to do anything on her own. My job is to diagnose the fault layer, collect evidence, fix or guide the fix, and write instructions Emily can follow herself if the issue recurs.

The first step of this lab was to load up my clean Windows 11 snapshot. Then I opened PowerShell and ran the ipconfig /all command to see my network information. Then for step 2, I tested each layer and saw if there were any faults. Then for step 3, I used Test-NetConnection to check specific port reachability which contacting google on port 443 was successful. Then for step 4, I exported all diagnostic evidence to connectivity-evidence.txt. Then for step 5, I identified the specific fault layer and write the root-cause explanation, which you can see below. Then for step 6, I wrote instructions for Emily and how to escalate if she needed to. 

Evidence: A group of screenshot that are labeled for each step. They can be found in the Screenshot Folder

Root-Cause Explanation: The root cause of Emily's connectivity issue is an *internal DNS resolution failure caused by an unconfigured or external DNS server. 

While the physical connection, local IP configuration, and default gateway routing are fully functional, shown by the ping 8.8.8.8 evidence. The diagnostic command nslookup acme.internal failed with: Unknown can't find acme.internal: Non-existent domain. This proves that the workstation is trying to query a public or unmapped DNS server that has no record of acme.internal. Also running Test-NetConnection -ComputerName 8.8.8.8 -Port 80 failed with TcpTestSucceeded : False, showing that connectivity to specific ports must be verified beyond basic ICMP ping.

Portfolio Card: I isolated a Windows connectivity issue across IP, DNS, and gateway checks, then turned the technical worded fix into instructions a remote user could follow without IT knowledge.
