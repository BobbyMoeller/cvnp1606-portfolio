Security Concepts: Windows Hello for Business and Windows LAPS

Section A: Windows Hello for Business
Windows Hello for Business replaces traditional passwords with a PIN or biometric sign-in. 

How it works: It requires an Entra ID or Active Directory. During setup, the device generates a cryptographic key pair. The private key is securely stored within the device’s hardware TPM and never leaves the device. Authentication relies on verifying the user to unlock access to this private key.

Why it is stronger: A standard password or a PIN can be used by an attacker from anywhere if stolen. WHfB is far more secure because it is bound to that physical device. Even if a bad actor intercepts or learns the PIN, they cannot authenticate from a different machine because they do not have the physical device housing the required private key.

Section B: Windows LAPS
What problem it solves: Every Windows machine in a normal environment uses the exact same local administrator password. This creates a severe security vulnerability. If an attacker compromises a single machine and extracts that local admin password, they can gain administrative access to every other machine in the network.

How it works: Windows LAPS mitigates this risk by automatically generating a unique, highly complex, and random password for the local administrator account on each specific device. This password is securely stored in Entra ID (or AD) and automatically rotates on a regular, configurable schedule. Authorized admins retrieve the current password from the Entra portal only when maintenance is required.

Why it matters for ACME: ACME’s cashier kiosks require technicians to use a shared local admin account for daily maintenance. Without LAPS, compromising one kiosk would expose the admin credentials for the entire fleet. With LAPS, every single kiosk has its own unique, frequently changing password. If one kiosk is compromised, the attacker gains no access to the other kiosks.