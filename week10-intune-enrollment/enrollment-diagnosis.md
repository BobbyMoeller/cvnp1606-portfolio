Enrollment Diagnosis: Partial Join Failure

Device State section:
AzureAdJoined : YES
WorkplaceJoined : NO
DomainJoined : NO
MdmUrl : (blank)

In this state, the device successfully authenticates and appears in the Entra ID (Azure AD) directory, but it never appears in Intune under Devices → All devices.

The Root Cause:
AzureAdJoined : YES means that the first half of the process, the authentication and joining the Entra ID directory, was  successful. But, a blank MdmUrl means the second half of the process, which is the Intune MDM enrollment, never happened. The device joined the directory but was never handed off to the MDM authority. This points to one of two configuration issues on the backend:
Missing License: The user account does not have a valid Intune license assigned.
MDM Scope Misconfiguration: MDM Automatic Enrollment is disabled, or the user is not included in the MDM user scope in the tenant settings. 

Remediation:

Verify Licensing:
Navigate to the Microsoft 365 admin center or Entra ID portal.
Check the user's account and ensure they have an active license that includes Intune.

Verify MDM User Scope:
Navigate to the Intune admin center.
Go to Devices → Enrollment → Windows tab → Automatic Enrollment.
Ensure the MDM user scope is set to All.
Ensure the MAM user scope is set to None.

Re-enroll the Device:
Disconnect the device from Entra ID (via Settings > Accounts > Access work or school) and rejoin it once the configurations are corrected.

Verification:
After the user rejoins the device, open PowerShell (no administrator rights needed) and run:
dsregcmd /status

Scroll to the Device State section. The remediation is successful when AzureAdJoined is YES and MdmUrl has thre Intune enrollment URL.