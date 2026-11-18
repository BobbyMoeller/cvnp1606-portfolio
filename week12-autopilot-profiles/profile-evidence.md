Device Configuration Profile Evidence

This Windows 10/11 Settings Catalog profile enforces a 900-second (15-minute) screen saver timeout, prevents users from modifying screen saver settings, and sets app camera access to "User in control." This addresses ACME’s baseline security needs by ensuring that unattended workstations time out to reduce unauthorized viewing, while preserving user control over camera permissions for legitimate video meetings.

The profile targets the `ACME-Pilot-Devices` group with no assignment filters applied. Scoping to a dedicated pilot group is appropriate because it allows to test setting behavior and catch any conflicts on a controlled test machine before rolling the policy out to production endpoints.
