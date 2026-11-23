# Change-Control Note — Win32 Application Deployment

**Application:** `ACME-Notepad++-ARM64` (Notepad++ `8.9.8.1` ARM64, Publisher: Notepad++)

**Deployment Tool:** Microsoft Intune (Win32 App Management)

## 1. What change are you making?

Deploying **Notepad++ 8.9.8.1 ARM64** (`ACME-Notepad++-ARM64`) as a packaged Win32 application (`.intunewin`) via Microsoft Intune. The package runs will run without needed input in the **System** context using the install command `npp.8.9.8.1.Installer.arm64.exe /S` with device restart behavior set to **No specific action**. Target requirements restrict installation to **ARM64** devices running **Windows 11 24H2** or later. A manually configured **File** detection rule checks for `C:\Program Files\Notepad++` to confirm installation state and prevent duplicate installs.

## 2. Which devices or users are affected?

* **Target Group:** `ACME-Pilot-Devices` (Included)
* **Assignment Type:** **Required**
* **Delivery & User Impact:** Content downloads in the background and installs it as soon as possible with toast notifications shown to the user (`Show all toast notifications`). Because the installer runs silently with `/S` and restart behavior is set to `No specific action`, no unexpected restart or user prompts will show.

## 3. What is the pilot approach?

This deployment is applied only to the **`ACME-Pilot-Devices`** group rather than all endpoints. Pilot devices will be monitored for around 24–48 hours to make sure the installation is silent under the System context, confirm the `C:\Program Files\Notepad++` detection rule evaluates cleanly without it looping, and verify the normal application launch on the Windows 11 24H2 ARM64 machine before expanding the assignment to broader production device groups.

## 4. What does success look like?

Deployment would be considered successful when all of the following things are met:

* **Detection Rule Passes:** Intune's File detection rule (`C:\Program Files\Notepad++`) shows as true after installation with zero loops.
* **Intune Reporting:** The **Device install status**  reports **Installed** (return code `0` or `1707`) for all devices in `ACME-Pilot-Devices` with no errors.
* **Company Portal Health:** No installation failure alerts or sync errors appear in Company Portal.
* **User Validation:** Users confirm Notepad++ 8.9.8.1 launches cleanly and opens/saves text files without errors.

## 5. What is the rollback plan?

If `ACME-Notepad++-ARM64` causes crashes, compatibility issues, or unexpected endpoint behavior:

1. Open the app in the Microsoft Intune admin center (**Apps → Windows apps → `ACME-Notepad++-ARM64` → Properties → Assignments → Edit**).
2. Remove `ACME-Pilot-Devices` from the **Required** assignment section and add `ACME-Pilot-Devices` to the **Uninstall** assignment section.
3. Save the assignment change so Intune automatically executes the configured silent uninstall command (`"C:\Program Files\Notepad++\uninstall.exe" /S`) on the targeted devices at their next check-in.
4. Confirm removal in **Device install status** and verify on a pilot device that `C:\Program Files\Notepad++` is no longer present.