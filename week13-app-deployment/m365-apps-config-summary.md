# Microsoft 365 Apps Configuration Summary — Week 13


## Suite Configuration (ACME)
To reduce the installation time, minimize resource usage, and limit unnecessary software, only productivity apps  required by ACME users should be included in the suite configuration:

* **Included Apps:** Word, Excel, PowerPoint, Outlook, OneNote, OneDrive Desktop, and Microsoft Teams.
* **Excluded Apps:** Access, Publisher, and Skype for Business.
* **Configuration Format:** Configuration designer (64-bit architecture).

---

## Update Channel Comparison

| Update Channel | Release Cadence | Characteristics |
| :--- | :--- | :--- |
| **Current Channel** | As soon as updates are available (unpredictable schedule) | Delivers the newest features fastest alongside security and non-security updates. Best suited for pilot testers rather than general endpoints. |
| **Monthly Enterprise Channel** | Once per month on the second Tuesday (Patch Tuesday) | Bundles feature, security, and non-security updates that have already been validated in Current Channel. Provides a predictable, stable monthly update. |
| **Semi-Annual Enterprise Channel** | New features twice a year (January and July); security and non-security updates monthly | Used for devices requiring extended feature-testing lead time. As of the July 2026 update, Microsoft is going to be unifying this channel into Monthly Enterprise Channel, so any new deployments should default to Monthly Enterprise Channel. |

---

## Channel Recommendation for ACME
* **Recommended Channel:** **Monthly Enterprise Channel**
* **Justification:** Monthly Enterprise Channel gives ACME a predictable Patch Tuesday update schedule that goes cleanly with standard Windows patching and change-control windows. Because the updates are pre-validated in Current Channel first, ACME maintains high stability while still receiving timely security and non-security fixes. Additionally, because Microsoft is unifying Semi-Annual Enterprise Channel into Monthly Enterprise Channel as of July 2026, Monthly Enterprise Channel is the standard choice for all new deployments.

---
