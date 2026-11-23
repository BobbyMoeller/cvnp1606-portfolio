# App Deployment Worksheet — Week 13 (Intune Application Lifecycle)

## Tenant Context:
* **Live Intune Tenant Status:** 0 Windows apps currently deployed.

## Win32 App Deployment Analysis (Steps 3 & 4)

| # | Field | Value / Analysis |
| :- | :--- | :--- |
| **1** | **App Name and Version** | **Name:** `ACME-Notepad++-ARM64` (Publisher: `Notepad++`)<br>**Version:** `8.9.8.1` (ARM64)<br>**Requirements:** ARM64 OS architecture, minimum OS `Windows 11 24H2`. |
| **2** | **Source Type** | **Windows app (Win32)** Official Notepad++ `.exe` installer (`npp.8.9.8.1.Installer.arm64.exe`)
| **3** | **Silent Install Switch** | **Install command:** `npp.8.9.8.1.Installer.arm64.exe /S`<br>**Uninstall command:** `"C:\Program Files\Notepad++\uninstall.exe" /S`<br>**Install behavior:** `System` (Device restart behavior: `No specific action`)<br>**Purpose of silent switch:** The `/S` switch (uppercase for NSIS installers) hides all wizard prompts and UI windows so Intune can install and uninstall the application unattended in the background. |
| **4** | **Detection Rule Type and Logic** | **Rules format:** Manually configure detection rules<br>**Rule type:** `File`<br>**Path:** `C:\Program Files\Notepad++`<br>**Detection logic:** Intune checks whether the `C:\Program Files\Notepad++` directory/file exists on the target device before and after executing the install command. If the path is present, Intune marks the app as installed and skips re-running the installer. |
| **5** | **Target Group** | `ACME-Pilot-Devices` (Included) |
| **6** | **Assignment Type** | **Required** (End user notifications: `Show all toast notifications`; Availability and Installation deadline: `As soon as possible`; Delivery optimization priority: `Content download in background`).<br> |
| **7** | **Failure Behavior (If Detection Rule Fails to Match)** | If the detection rule fails to match after installation, if a future installer changes the install directory from `C:\Program Files\Notepad++` or if the path contains a typo, Intune will assume the application is not installed even though the installer ran. Intune will report an installation failure in Device install status and repeatedly re-download and re-run `npp.8.9.8.1.Installer.arm64.exe /S` on subsequent check-in cycles, causing reinstallation loops, wasted resources, and unnecessary load until the detection rule is corrected. |