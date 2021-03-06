---
title: Differences between Surface Hub and Windows 10 Enterprise
description: This topic explains the differences between Windows 10 Team and Windows 10 Enterprise.
keywords: change history
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: surfacehub
author: isaiahng
localizationpriority: medium
---

# Differences between Surface Hub and Windows 10 Enterprise

The Surface Hub operating system, Windows 10 Team, is based on Windows 10 Enterprise, providing rich support for enterprise management, security, and other features. However, there are important differences between them. While the Enterprise edition is designed for PCs, Windows 10 Team is designed from the ground up for large screens and meeting rooms. When you evaluate security and management requirements for Surface Hub, it's best to consider it as a new operating system. This article is designed to help highlight the key differences between Windows 10 Team on Surface Hub and Windows 10 Enterprise, and what the differences mean for your organization.

## User interface

### Shell (OS user interface)

The Surface Hub's shell is designed from the ground up to be large screen and touch optimized. It doesn't use the same shell as Windows 10 Enterprise.

*Organization policies that this may affect:* <br> Settings related to controls in the Windows 10 Enterprise shell don't apply for Surface Hub.

### Lock screen and screensaver

Surface Hub doesn't have a lock screen or a screen saver, but it has a similar feature called the welcome screen. The welcome screen shows scheduled meetings from the device account's calendar, and easy entry points to the Surface Hub's top apps - Skype for Business, Whiteboard, and Connect.

*Organization policies that this may affect:* <br> Settings for lock screen, screen timeout, and screen saver don't apply for Surface Hub.

### User logon

Surface Hub is designed to be used in communal spaces, such as meeting rooms. Unlike Windows PCs, anyone can walk up and use a Surface Hub without logging on. The system always runs as a local, auto logged-in, low-privilege user. It doesn't support logging in any additional users - including admin users.

> [!NOTE]
> Surface Hub supports signing in to Microsoft Edge and other apps. However, these credentials are deleted when users press **End session**. 

*Organization policies that this may affect:* <br> Generally, Surface Hub uses lockdown features rather than user access control to enforce security. Policies related to password requirements, interactive logon, user accounts, and access control don't apply for Surface Hub.

### Saving and browsing files

Users have access to a limited set of directories on the Surface Hub:
- Music
- Videos
- Documents
- Pictures
- Downloads

Files saved locally in these directories are deleted when users press **End session**. To save content created during a meeting, users should save files to a USB drive or to OneDrive.

*Organization policies that this may affect:* <br> Policies related to access permissions and ownership of files and folders don't apply for Surface Hub. Users can't browse and save files to system directories and network folders.

## Applications

### Default applications

With few exceptions, the default Universal Windows Platform (UWP) apps on Surface Hub are also available on Windows 10 PCs.

UWP apps pre-installed on Surface Hub:
- Alarms & Clock
- Calculator
- Connect
- Excel Mobile
- Feedback Hub
- File Explorer*
- Get Started
- Maps
- Microsoft Edge
- Microsoft Power BI
- OneDrive
- Photos
- PowerPoint Mobile
- Settings*
- Skype for Business*
- Store
- Whiteboard*
- Word Mobile

*Apps with an asterisk (&ast;) are unique to Surface Hub*

*Organization policies that this may affect:* <br> Use guidelines for Windows 10 Enterprise to determine the features and network requirements for default apps on the Surface Hub.

### Installing apps, drivers, and services

To help preserve the appliance-like nature of the device, Surface Hub only supports installing Universal Windows Platform (UWP) apps, and does not support installing classic Win32 apps, services and drivers. Furthermore, only admins have access to install UWP apps.

*Organization policies that this may affect:* <br> Employees can only use the apps that have been installed by admins, helping mitigate against unintended use. Surface Hub doesn't support installing Win32 agents required by most traditional PC management and monitoring tools.

## Security and lockdown

For Surface Hub to be used in communal spaces, such as meeting rooms, its custom OS implements many of the security and lockdown features available in Windows 10.

Surface Hub implements these Windows 10 security features:
- [UEFI Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)
- [User Mode Code Integrity (UMCI) with Device Guard](https://technet.microsoft.com/itpro/windows/keep-secure/introduction-to-device-guard-virtualization-based-security-and-code-integrity-policies)
- [Application restriction policies using AppLocker](https://technet.microsoft.com/itpro/windows/keep-secure/applocker-overview)
- [BitLocker Drive Encryption](https://technet.microsoft.com/itpro/windows/keep-secure/bitlocker-overview)
- [Trusted Platform Module (TPM)](https://technet.microsoft.com/itpro/windows/keep-secure/trusted-platform-module-overview)
- [Windows Defender](https://technet.microsoft.com/itpro/windows/keep-secure/windows-defender-in-windows-10)
- [User Account Control (UAC)](https://technet.microsoft.com/itpro/windows/keep-secure/user-account-control-overview) for access to the Settings app

These Surface Hub features provide additional security:
- Custom UEFI firmware
- Custom shell and Start menu limits device to meeting functions
- Custom File Explorer only grants access to files and folders under My Documents
- Custom Settings app only allows admins to modify device settings
- Downloading advanced Plug and Play drivers is disabled

*Organization policies that this may affect:* <br> Consider these features when performing your security assessment for Surface Hub.

## Management

### Device settings

Device settings can be configured through the Settings app. The Settings app is customized for Surface Hub, but also contains many familiar settings from Windows 10 Desktop. A User Accounts Control (UAC) prompt appears when opening up the Settings app to verify the admin's credentials, but this does not log in the admin.

*Organization policies that this may affect:* <br> Employees can use the Surface Hub for meetings, but cannot modify any device settings. In addition to lockdown features, this ensures that employees only use the device for meeting functions.

### Administrative features

The administrative features in Windows 10 Enterprise, such as the Microsoft Management Console, Run, Command Prompt, PowerShell, registry editor, event viewer, and task manager are not supported on Surface Hub. The Settings app contains all of the administrative features locally available on Surface Hub.

*Organization policies that this may affect:* <br> Surface Hubs are not managed like traditional PCs. Use MDM to configure settings and OMS to monitor your Surface Hub.

### Remote management and monitoring

Surface Hub supports remote management through mobile device management (MDM), and monitoring through Operations Management Suite (OMS).

*Organization policies that this may affect:* <br> Surface Hub doesn't support installing Win32 agents required by most traditional PC management and monitoring tools, such as System Center Operations Manager.

### Group policy

Surface Hub does not support group policy, including auditing. Instead, use MDM to apply policies to your Surface Hub. For more information about MDM, see [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md).

*Organization policies that this may affect:* <br> Use MDM to manage Surface Hub rather than group policy.

### Remote assistance

Surface Hub does not support remote assistance.

*Organization policies that this may affect:* <br> Policies related to remote assistance don't apply for Surface Hub.

## Network

### Domain join and Azure Active Directory (Azure AD) join 

Surface Hub uses domain join and Azure AD join primarily to provide a directory-backed admin group. Users can't log in with a domain account. For more information, see [Admin group management](admin-group-management-for-surface-hub.md).

*Organization policies that this may affect:* <br> Group policies are not applied when a Surface Hub is joined to your domain. Policies related to domain membership don't apply for Surface Hub.

### Accessing domain resources

Users can sign in to Microsoft Edge to access intranet sites and online resources (such as Office 365). If your Surface Hub is configured with a device account, the system uses it to access Exchange and Skype for Business. However, Surface Hub doesn't support accessing domain resources such as file shares and printers.

*Organization policies that this may affect:* <br> Policies related to accessing domain objects don't apply for Surface Hub.

<!--
### Endpoints



*Organization policies that this may affect:* <br> 
-->

### Telemetry

The Surface Hub OS uses the Windows 10 Connected User Experience and Telemetry component to gather and transmit telemetry data. For more information, see [Configure Windows telemetry in your organization](https://technet.microsoft.com/itpro/windows/manage/configure-windows-telemetry-in-your-organization).

*Organization policies that this may affect:* <br> Configure telemetry levels for Surface Hub in the same way as you do for Windows 10 Enterprise.