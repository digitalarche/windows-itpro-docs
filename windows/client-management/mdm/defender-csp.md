---
title: Defender CSP
description: Learn how the Windows Defender configuration service provider is used to configure various Windows Defender actions across the enterprise.
ms.assetid: 481AA74F-08B2-4A32-B95D-5A3FD05B335C
ms.reviewer: 
manager: dansimp
ms.author: dansimp
ms.topic: article
ms.prod: w10
ms.technology: windows
author: manikadhiman
ms.localizationpriority: medium
ms.date: 08/11/2020
---

# Defender CSP

> [!WARNING]
> Some information relates to prereleased products, which may be substantially modified before it's commercially released. Microsoft makes no warranties, expressed or implied, concerning the information provided here.

The Windows Defender configuration service provider is used to configure various Windows Defender actions across the enterprise.

The following shows the Windows Defender configuration service provider in tree format.
```
./Vendor/MSFT
Defender
----Detections
--------ThreatId
------------Name
------------URL
------------Severity
------------Category
------------CurrentStatus
------------ExecutionStatus
------------InitialDetectionTime
------------LastThreatStatusChangeTime
------------NumberOfDetections
----Health
--------ProductStatus (Added in Windows 10 version 1809)
--------ComputerState
--------DefenderEnabled
--------RtpEnabled
--------NisEnabled
--------QuickScanOverdue
--------FullScanOverdue
--------SignatureOutOfDate
--------RebootRequired
--------FullScanRequired
--------EngineVersion
--------SignatureVersion
--------DefenderVersion
--------QuickScanTime
--------FullScanTime
--------QuickScanSigVersion
--------FullScanSigVersion
--------TamperProtectionEnabled (Added in Windows 10, version 1903)
--------IsVirtualMachine (Added in Windows 10, version 1903)
----Configuration (Added in Windows 10, version 1903)
--------TamperProetection (Added in Windows 10, version 1903)
--------EnableFileHashcomputation (Added in Windows 10, version 1903)
--------SupportLogLocation (Added in the next major release of Windows 10)
----Scan
----UpdateSignature
----OfflineScan (Added in Windows 10 version 1803)
```
<a href="" id="detections"></a>**Detections**  
An interior node to group all threats detected by Windows Defender.

Supported operation is Get.

<a href="" id="detections-threatid"></a>**Detections/**<strong>*ThreatId*</strong>  
The ID of a threat that has been detected by Windows Defender.

Supported operation is Get.

<a href="" id="detections-threatid-name"></a>**Detections/*ThreatId*/Name**  
The name of the specific threat.

The data type is a string.

Supported operation is Get.

<a href="" id="detections-threatid-url"></a>**Detections/*ThreatId*/URL**  
URL link for additional threat information.

The data type is a string.

Supported operation is Get.

<a href="" id="detections-threatid-severity"></a>**Detections/*ThreatId*/Severity**  
Threat severity ID.

The data type is integer.

The following list shows the supported values:

-   0 = Unknown
-   1 = Low
-   2 = Moderate
-   4 = High
-   5 = Severe

Supported operation is Get.

<a href="" id="detections-threatid-category"></a>**Detections/*ThreatId*/Category**  
Threat category ID.

The data type is integer.

The following table describes the supported values:

| Value | Description                 |
|-------|-----------------------------|
| 0     | Invalid                     |
| 1     | Adware                      |
| 2     | Spyware                     |
| 3     | Password stealer            |
| 4     | Trojan downloader           |
| 5     | Worm                        |
| 6     | Backdoor                    |
| 7     | Remote access Trojan        |
| 8     | Trojan                      |
| 9     | Email flooder               |
| 10    | Keylogger                   |
| 11    | Dialer                      |
| 12    | Monitoring software         |
| 13    | Browser modifier            |
| 14    | Cookie                      |
| 15    | Browser plugin              |
| 16    | AOL exploit                 |
| 17    | Nuker                       |
| 18    | Security disabler           |
| 19    | Joke program                |
| 20    | Hostile ActiveX control     |
| 21    | Software bundler            |
| 22    | Stealth modifier            |
| 23    | Settings modifier           |
| 24    | Toolbar                     |
| 25    | Remote control software     |
| 26    | Trojan FTP                  |
| 27    | Potential unwanted software |
| 28    | ICQ exploit                 |
| 29    | Trojan telnet               |
| 30    | Exploit                     |
| 31    | File sharing program        |
| 32    | Malware creation tool       |
| 33    | Remote control software     |
| 34    | Tool                        |
| 36    | Trojan denial of service    |
| 37    | Trojan dropper              |
| 38    | Trojan mass mailer          |
| 39    | Trojan monitoring software  |
| 40    | Trojan proxy server         |
| 42    | Virus                       |
| 43    | Known                       |
| 44    | Unknown                     |
| 45    | SPP                         |
| 46    | Behavior                    |
| 47    | Vulnerability               |
| 48    | Policy                      |
| 49    | EUS (Enterprise Unwanted Software)|
| 50    | Ransomware                  |
| 51    | ASR Rule                    |

Supported operation is Get.

<a href="" id="detections-threatid-currentstatus"></a>**Detections/*ThreatId*/CurrentStatus**  
Information about the current status of the threat.

The data type is integer.

The following list shows the supported values:

-   0 = Active
-   1 = Action failed
-   2 = Manual steps required
-   3 = Full scan required
-   4 = Reboot required
-   5 = Remediated with noncritical failures
-   6 = Quarantined
-   7 = Removed
-   8 = Cleaned
-   9 = Allowed
-   10 = No Status ( Cleared)

Supported operation is Get.

<a href="" id="detections-threatid-executionstatus"></a>**Detections/*ThreatId*/ExecutionStatus**  
Information about the execution status of the threat.

The data type is integer.

Supported operation is Get.

<a href="" id="detections-threatid-initialdetectiontime"></a>**Detections/*ThreatId*/InitialDetectionTime**  
The first time this particular threat was detected.

The data type is a string.

Supported operation is Get.

<a href="" id="detections-threatid-lastthreatstatuschangetime"></a>**Detections/*ThreatId*/LastThreatStatusChangeTime**  
The last time this particular threat was changed.

The data type is a string.

Supported operation is Get.

<a href="" id="detections-threatid-numberofdetections"></a>**Detections/*ThreatId*/NumberOfDetections**  
Number of times this threat has been detected on a particular client.

The data type is integer.

Supported operation is Get.

<a href="" id="health"></a>**Health**  
An interior node to group information about Windows Defender health status.

Supported operation is Get.

<a href="" id="health-productstatus"></a>**Health/ProductStatus**  
Added in Windows 10, version 1809. Provide the current state of the product. This is a bitmask flag value that can represent one or multiple product states from below list.

The data type is integer. Supported operation is Get.

Supported product status values:  
-  No status                                                        = 0
-  Service not running                                              = 1 << 0
-  Service started without any malware protection engine            = 1 << 1
-  Pending full scan due to threat action                           = 1 << 2
-  Pending reboot due to threat action                              = 1 << 3
-  ending manual steps due to threat action                        = 1 << 4
-  AV signatures out of date                                        = 1 << 5
-  AS signatures out of date                                        = 1 << 6
-  No quick scan has happened for a specified period                = 1 << 7
-  No full scan has happened for a specified period                 = 1 << 8
-  System initiated scan in progress                                = 1 << 9
-  System initiated clean in progress                               = 1 << 10
-  There are samples pending submission                             = 1 << 11
-  Product running in evaluation mode                               = 1 << 12
-  Product running in non-genuine Windows mode                      = 1 << 13
-  Product expired                                                  = 1 << 14
-  Off-line scan required                                           = 1 << 15
-  Service is shutting down as part of system shutdown              = 1 << 16
-  Threat remediation failed critically                             = 1 << 17
-  Threat remediation failed non-critically                         = 1 << 18
-  No status flags set (well initialized state)                     = 1 << 19
-  Platform is out of date                                          = 1 << 20
-  Platform update is in progress                                   = 1 << 21
-  Platform is about to be outdated                                 = 1 << 22
-  Signature or platform end of life is past or is impending        = 1 << 23
-  Windows SMode signatures still in use on non-Win10S install      = 1 << 24

Example:

```xml
<SyncML xmlns="SYNCML:SYNCML1.1">
  <SyncBody>
    <Get>
      <CmdID>1</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/Defender/Health/ProductStatus</LocURI>
          </Target>
        </Item>
    </Get>
    <Final/>
  </SyncBody>
</SyncML>
```

<a href="" id="health-computerstate"></a>**Health/ComputerState**  
Provide the current state of the device.

The data type is integer.

The following list shows the supported values:

-   0 = Clean
-   1 = Pending full scan
-   2 = Pending reboot
-   4 = Pending manual steps (Windows Defender is waiting for the user to take some action, such as restarting the computer or running a full scan)
-   8 = Pending offline scan
-   16 = Pending critical failure (Windows Defender has failed critically and an Administrator needs to investigate and take some action, such as restarting the computer or reinstalling Windows Defender)

Supported operation is Get.

<a href="" id="health-defenderenabled"></a>**Health/DefenderEnabled**  
Indicates whether the Windows Defender service is running.

The data type is a Boolean.

Supported operation is Get.

<a href="" id="health-rtpenabled"></a>**Health/RtpEnabled**  
Indicates whether real-time protection is running.

The data type is a Boolean.

Supported operation is Get.

<a href="" id="health-nisenabled"></a>**Health/NisEnabled**  
Indicates whether network protection is running.

The data type is a Boolean.

Supported operation is Get.

<a href="" id="health-quickscanoverdue"></a>**Health/QuickScanOverdue**  
Indicates whether a Windows Defender quick scan is overdue for the device.

A Quick scan is overdue when a scheduled Quick scan did not complete successfully for 2 weeks and [catchup Quick scans](./policy-csp-defender.md#defender-disablecatchupquickscan) are disabled (default).

The data type is a Boolean.

Supported operation is Get.

<a href="" id="health-fullscanoverdue"></a>**Health/FullScanOverdue**  
Indicates whether a Windows Defender full scan is overdue for the device.

A Full scan is overdue when a scheduled Full scan did not complete successfully for 2 weeks and [catchup Full scans](./policy-csp-defender.md#defender-disablecatchupfullscan) are disabled (default).

The data type is a Boolean.

Supported operation is Get.

<a href="" id="health-signatureoutofdate"></a>**Health/SignatureOutOfDate**  
Indicates whether the Windows Defender signature is outdated.

The data type is a Boolean.

Supported operation is Get.

<a href="" id="health-rebootrequired"></a>**Health/RebootRequired**  
Indicates whether a device reboot is needed.

The data type is a Boolean.

Supported operation is Get.

<a href="" id="health-fullscanrequired"></a>**Health/FullScanRequired**  
Indicates whether a Windows Defender full scan is required.

The data type is a Boolean.

Supported operation is Get.

<a href="" id="health-engineversion"></a>**Health/EngineVersion**  
Version number of the current Windows Defender engine on the device.

The data type is a string.

Supported operation is Get.

<a href="" id="health-signatureversion"></a>**Health/SignatureVersion**  
Version number of the current Windows Defender signatures on the device.

The data type is a string.

Supported operation is Get.

<a href="" id="health-defenderversion"></a>**Health/DefenderVersion**  
Version number of Windows Defender on the device.

The data type is a string.

Supported operation is Get.

<a href="" id="health-quickscantime"></a>**Health/QuickScanTime**  
Time of the last Windows Defender quick scan of the device.

The data type is a string.

Supported operation is Get.

<a href="" id="health-fullscantime"></a>**Health/FullScanTime**  
Time of the last Windows Defender full scan of the device.

The data type is a string.

Supported operation is Get.

<a href="" id="health-quickscansigversion"></a>**Health/QuickScanSigVersion**  
Signature version used for the last quick scan of the device.

The data type is a string.

Supported operation is Get.

<a href="" id="health-fullscansigversion"></a>**Health/FullScanSigVersion**  
Signature version used for the last full scan of the device.

The data type is a string.

Supported operation is Get.

<a href="" id="health-tamperprotectionenabled"></a>**Health/TamperProtectionEnabled**  
Indicates whether the Windows Defender tamper protection feature is enabled.​

The data type is a Boolean.

Supported operation is Get.

<a href="" id="health-isvirtualmachine"></a>**Health/IsVirtualMachine**  
Indicates whether the device is a virtual machine.

The data type is a string.

Supported operation is Get.

<a href="" id="configuration"></a>**Configuration**  
An interior node to group Windows Defender configuration information.

Supported operation is Get.

<a href="" id="configuration-tamperprotection"></a>**Configuration/TamperProtection**  
Tamper protection helps protect important security features from unwanted changes and interference.  This includes real-time protection, behavior monitoring, and more. Accepts signed string to turn the feature on or off. Settings are configured with an MDM solution, such as Intune and is available in Windows 10 Enterprise E5 or equivalent subscriptions.

Send off blob to device to reset tamper protection state before setting this configuration to "not configured" or "unassigned" in Intune.

The data type is a Signed blob.

Supported operations are Add, Delete, Get, Replace.

Intune tamper protection setting UX supports three states:  
- Not configured (default): Does not have any impact on the default state of the device.
- Enabled: Enables the tamper protection feature.
- Disabled: Turns off the tamper protection feature.

When enabled or disabled exists on the client and admin moves the setting to not configured, it will not have any impact on the device state. To change the state to either enabled or disabled would require to be set explicitly.

<a href="" id="configuration-disablelocaladminmerge"></a>**Configuration/DisableLocalAdminMerge**<br>
This policy setting controls whether or not complex list settings configured by a local administrator are merged with managed settings. This setting applies to lists such as threats and exclusions.

If you disable or do not configure this setting, unique items defined in preference settings configured by the local administrator will be merged into the resulting effective policy. In the case of conflicts, management settings will override preference settings.

If you enable this setting, only items defined by management will be used in the resulting effective policy. Managed settings will override preference settings configured by the local administrator.

> [!NOTE]
> Applying this setting will not remove exclusions from the device registry, it will only prevent them from being applied/used. This is reflected in **Get-MpPreference**.

Supported OS versions:  Windows 10

The data type is integer.

Supported operations are Add, Delete, Get, Replace.

Valid values are:  
- 1 – Enable.
- 0 (default) – Disable.

<a href="" id="configuration-disablecputhrottleonidlescans"></a>**Configuration/DisableCpuThrottleOnIdleScans**<br>	
Indicates whether the CPU will be throttled for scheduled scans while the device is idle.  This feature is enabled by default and will not throttle the CPU for scheduled scans performed when the device is otherwise idle, regardless of what ScanAvgCPULoadFactor is set to. For all other scheduled scans this flag will have no impact and normal throttling will occur.	

The data type is integer.	

Supported operations are Add, Delete, Get, Replace.	

Valid values are:	
-	1 (default) – Enable.	
-	0 – Disable.

<a href="" id="configuration-meteredconnectionupdates"></a>**Configuration/MeteredConnectionUpdates**<br>
Allow managed devices to update through metered connections. Data charges may apply.

The data type is integer.

Supported operations are Add, Delete, Get, Replace.

Valid values are:
- 1 – Enable.
- 0 (default) – Disable.

<a href="" id="configuration-allownetworkprotectiononwinserver"></a>**Configuration/AllowNetworkProtectionOnWinServer**<br>
This settings controls whether Network Protection is allowed to be configured into block or audit mode on Windows Server. If false, the value of EnableNetworkProtection will be ignored.

The data type is integer.

Supported operations are Add, Delete, Get, Replace.

Valid values are:
- 1 – Enable.
- 0 (default) – Disable.

<a href="" id="configuration-exclusionipaddress"></a>**Configuration/ExclusionIpAddress**<br>
Allows an administrator to explicitly disable network packet inspection made by wdnisdrv on a particular set of IP addresses.

The data type is string.

Supported operations are Add, Delete, Get, Replace.

<a href="" id="configuration-enablefilehashcomputation"></a>**Configuration/EnableFileHashComputation**  
Enables or disables file hash computation feature.
When this feature is enabled Windows defender will compute hashes for files it scans.

The data type is integer.

Supported operations are Add, Delete, Get, Replace.

Valid values are:  
- 1 – Enable.
- 0 (default) – Disable.

<a href="" id="configuration-supportloglocation"></a>**Configuration/SupportLogLocation**  
The support log location setting allows the administrator to specify where the Microsoft Defender Antivirus diagnostic data collection tool (**MpCmdRun.exe**) will save the resulting log files. This setting is configured with an MDM solution, such as Intune, and is available for Windows 10 Enterprise. 

Data type is string.

Supported operations are Add, Delete, Get, Replace.

Intune Support log location setting UX supports three states:  

- Not configured (default) - Does not have any impact on the default state of the device. 
- 1 - Enabled. Enables the Support log location feature. Requires admin to set custom file path.
- 0 - Disabled. Turns off the Support log location feature. 

When enabled or disabled exists on the client and admin moves the setting to not configured, it will not have any impact on the device state. To change the state to either enabled or disabled would require to be set explicitly.  

More details:  

- [Microsoft Defender AV diagnostic data](/microsoft-365/security/defender-endpoint/collect-diagnostic-data)  
- [Collect investigation package from devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)  

<a href="" id="scan"></a>**Scan**  
Node that can be used to start a Windows Defender scan on a device.

Valid values are:
- 1 - quick scan
- 2 - full scan

Supported operations are Get and Execute.

<a href="" id="updatesignature"></a>**UpdateSignature**  
Node that can be used to perform signature updates for Windows Defender.

Supported operations are Get and Execute.

<a href="" id="offlinescan"></a>**OfflineScan**  
Added in Windows 10, version 1803. OfflineScan action starts a Microsoft Defender Offline scan on the computer where you run the command. After the next OS reboot, the device will start in Microsoft Defender Offline mode to begin the scan.

Supported operations are Get and Execute.

## Related topics

[Configuration service provider reference](configuration-service-provider-reference.md)
