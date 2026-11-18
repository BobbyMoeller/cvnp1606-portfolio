Conditional Access Implementation Memo:

To: IT Support & Helpdesk
Subject* Conditional Access Enforcements and User Experience

If the Conditional Access policy were switched from report-only to enforced, Emily Park would be blocked from accessing Outlook or any Office 365 resources on her unmanaged device. Instead of her Outlook, she would see a prompt stating that her device must be managed and compliant with organizational security policies to gain access.

When Emily calls the helpdesk encountering this block, the correct response would be to explain that ACME now requires devices accessing corporate data to meet baseline security standards. The technician should then guide her through enrolling her unmanaged device into Intune so it can be evaluated, marked as compliant, and granted secure access.

Deploying this policy in Report-only mode first is critical. It allows IT administrators to log the outcome of the policy against real user sign-ins without actually blocking anyone's workflow. This provides visibility into how many users would be affected, allowing us to fix any issues before enforcing a block. 