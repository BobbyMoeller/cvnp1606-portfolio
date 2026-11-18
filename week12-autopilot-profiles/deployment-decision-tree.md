Windows Autopilot Deployment Decision Tree:


Scenario 1: New Hire Receiving a Laptop on Their First Day at the ACME Office
Selected Mode: User-driven
Why This Is Correct: The new hire is physically on-site with fast corporate network access and IT support nearby if needed. With User-driven mode, the employee powers on the factory-fresh laptop, connects to the network, and signs in with their ACME Microsoft Entra ID credentials. Autopilot automatically joins the device to Entra ID, enrolls it in Intune, assigns the new hire as the primary user, and applies their role-specific apps and policies without requiring IT to touch the hardware beforehand.
Unsuitable Alternative: Self-deploying. Self-deploying mode skips the user sign-in prompt during Out-of-Box Experience (OOBE) and does not assign a primary user to the device. Because a new hire needs a dedicated personal workstation tied to their identity and user-targeted apps, Self-deploying would not work.


Scenario 2: Shared Kiosk Device in the ACME Break Room with No Assigned User
Selected Mode: Self-deploying
Why This Is Correct: Self-deploying mode is built specifically for kiosks, digital signage, and shared devices that have no primary user. A technician only needs to power on the device and connect it to Ethernet; using TPM 2.0 hardware attestation, the device automatically joins Entra ID, enrolls in Intune, and applies the locked-down kiosk configuration with zero manual sign-in or interaction.
Unsuitable Alternative: User-driven. User-driven mode requires an individual user to authenticate with Entra ID credentials during OOBE to complete enrollment. This breaks the zero-touch, userless design required for a shared break room kiosk.


Scenario 3: Remote Employee Receiving a Pre-Staged Laptop Shipped from the Nexus Warehouse
Selected Mode: Pre-provisioning (White Glove)
Why It Is Correct: Pre-provisioning splits the setup into two phases. A technician at the Nexus warehouse boots the laptop (pressing the Windows key five times at OOBE), connects it to a fast wired network, and pre-installs all heavy device-level applications, Windows updates, and security policies before resealing and shipping it. When the remote employee receives the laptop on potentially slower home Wi-Fi, they sign in and reach a fully configured desktop in minutes rather than waiting hours for large downloads.
Unsuitable Alternative: Self-deploying. Self-deploying mode cannot bind the laptop to the remote employee's Entra ID account or deliver their user-targeted profiles and applications.


Scenario 4: Replacement Laptop for an Existing Employee Whose Primary Device Failed
Selected Mode: User-driven
Why It Is Correct: When an existing employee's primary device fails, minimizing downtime is the top priority. IT can hand the employee a spare Autopilot-registered laptop directly from stock. The employee signs in with their existing Entra ID credentials, and Intune automatically restores their user-assigned applications, policies, and cloud-synced files (via OneDrive Known Folder Move) without IT needing to manually image or pre-stage the machine.
Unsuitable Alternative: Self-deploying. Self-deploying mode provisions a generic, userless device and will not associate the replacement laptop with the employee's Entra ID account or trigger the automatic deployment of their user-assigned apps and personal workspace settings.