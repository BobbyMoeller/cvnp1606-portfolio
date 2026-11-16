Entra ID & Intune Tenant Setup Notes

Tenant Name: ACME

Trial Expiry Date: 12/16/2026

Device Group 1: ACME-All-Devices
Membership Type: Dynamic 
Reasoning: Dynamic membership was chosen so that each device that joins the Entra ID tenant is automatically added to this group. This makes sure that the baseline security policiess are applied automatically.

Device Group 2: ACME-Pilot-Devices
Membership Type: Assigned
Reasoning: Assigned membership was chosen because this group requires control. This allows the administrator to manually hand-pick specific test devices to test new configurations or updates safely before rolling them out to the other group.