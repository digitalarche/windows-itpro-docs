---
title: FAQ - Microsoft Defender Application Guard (Windows 10)
description: Learn about the commonly asked questions and answers for Microsoft Defender Application Guard.
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 05/12/2021
ms.reviewer:
manager: dansimp
ms.custom: asr
ms.technology: mde
---

# Frequently asked questions - Microsoft Defender Application Guard

**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)

This article lists frequently asked questions with answers for Microsoft Defender Application Guard (Application Guard). Questions span features, integration with the Windows operating system, and general configuration.

## Frequently Asked Questions

### Can I enable Application Guard on machines equipped with 4-GB RAM?

We recommend 8-GB RAM for optimal performance but you can use the following registry DWORD values to enable Application Guard on machines that aren't meeting the recommended hardware configuration.

`HKLM\software\Microsoft\Hvsi\SpecRequiredProcessorCount` (Default is four cores.)

`HKLM\software\Microsoft\Hvsi\SpecRequiredMemoryInGB` (Default is 8 GB.)

`HKLM\software\Microsoft\Hvsi\SpecRequiredFreeDiskSpaceInGB` (Default is 5 GB.)

### Can employees download documents from the Application Guard Edge session onto host devices?

In Windows 10 Enterprise edition, version 1803, users are able to download documents from the isolated Application Guard container to the host PC. This capability is managed by policy.

In Windows 10 Enterprise edition, version 1709, or Windows 10 Professional edition, version 1803, it is not possible to download files from the isolated Application Guard container to the host computer. However, employees can use the **Print as PDF** or **Print as XPS** options and save those files to the host device.

### Can employees copy and paste between the host device and the Application Guard Edge session?

Depending on your organization's settings, employees can copy and paste images (.bmp) and text to and from the isolated container.

### Why don't employees see their favorites in the Application Guard Edge session?

Depending on your organization’s settings, it might be that Favorites Sync is turned off. To manage the policy, see: [Microsoft Edge and Microsoft Defender Application Guard | Microsoft Docs](/deployedge/microsoft-edge-security-windows-defender-application-guard)

### Why aren’t employees able to see their extensions in the Application Guard Edge session?

Make sure to enable the extensions policy on your Application Guard configuration.

### How do I configure Microsoft Defender Application Guard to work with my network proxy (IP-Literal Addresses)?

Application Guard requires proxies to have a symbolic name, not just an IP address. IP-Literal proxy settings such as `192.168.1.4:81` can be annotated as `itproxy:81` or using a record such as `P19216810010` for a proxy with an IP address of `192.168.100.10`. This applies to Windows 10 Enterprise edition, version 1709 or higher. These would be for the proxy policies under Network Isolation in Group Policy or Intune.

### Which Input Method Editors (IME) in 19H1 are not supported?

The following Input Method Editors (IME) introduced in Windows 10, version 1903 are currently not supported in Microsoft Defender Application Guard:

- Vietnam Telex keyboard
- Vietnam number key-based keyboard
- Hindi phonetic keyboard
- Bangla phonetic keyboard
- Marathi phonetic keyboard
- Telugu phonetic keyboard
- Tamil phonetic keyboard
- Kannada phonetic keyboard
- Malayalam phonetic keyboard
- Gujarati phonetic keyboard
- Odia phonetic keyboard
- Punjabi phonetic keyboard

### I enabled the hardware acceleration policy on my Windows 10 Enterprise, version 1803 deployment. Why are my users still only getting CPU rendering?

This feature is currently experimental only and is not functional without an additional registry key provided by Microsoft. If you would like to evaluate this feature on a deployment of Windows 10 Enterprise, version 1803, contact Microsoft and we’ll work with you to enable the feature.

### What is the WDAGUtilityAccount local account?

WDAGUtilityAccount is part of Application Guard, beginning with Windows 10, version 1709 (Fall Creators Update). It remains disabled by default, unless Application Guard is enabled on your device. WDAGUtilityAccount is used to sign in to the Application Guard container as a standard user with a random password. It is NOT a malicious account. If *Run as a service* permissions are revoked for this account, you might see the following error:

**Error: 0x80070569, Ext error: 0x00000001; RDP: Error: 0x00000000, Ext error: 0x00000000 Location: 0x00000000**

We recommend that you do not modify this account.

### How do I trust a subdomain in my site list?

To trust a subdomain, you must precede your domain with two dots (..). For example: `..contoso.com` ensures that `mail.contoso.com` or `news.contoso.com` are trusted. The first dot represents the strings for the subdomain name (mail or news), and the second dot recognizes the start of the domain name (`contoso.com`). This prevents sites such as `fakesitecontoso.com` from being trusted.

### Are there differences between using Application Guard on Windows Pro vs Windows Enterprise?

When using Windows Pro or Windows Enterprise, you have access to using Application Guard in Standalone Mode. However, when using Enterprise you have access to Application Guard in Enterprise-Managed Mode. This mode has some extra features that the Standalone Mode does not. For more information, see [Prepare to install Microsoft Defender Application Guard](./install-md-app-guard.md).

### Is there a size limit to the domain lists that I need to configure?

Yes, both the Enterprise Resource domains that are hosted in the cloud and the domains that are categorized as both work and personal have a 16383-B limit.

### Why does my encryption driver break Microsoft Defender Application Guard?

Microsoft Defender Application Guard accesses files from a VHD mounted on the host that needs to be written during setup. If an encryption driver prevents a VHD from being mounted or from being written to, Application Guard does not work and results in an error message (**0x80070013 ERROR_WRITE_PROTECT**).

### Why do the Network Isolation policies in Group Policy and CSP look different?

There is not a one-to-one mapping among all the Network Isolation policies between CSP and GP. Mandatory network isolation policies to deploy Application Guard are different between CSP and GP.

- Mandatory network isolation GP policy to deploy Application Guard: **DomainSubnets or CloudResources**

- Mandatory network isolation CSP policy to deploy Application Guard: **EnterpriseCloudResources or (EnterpriseIpRange and EnterpriseNetworkDomainNames)**

- For EnterpriseNetworkDomainNames, there is no mapped CSP policy.

Application Guard accesses files from a VHD mounted on the host that needs to be written during setup. If an encryption driver prevents a VHD from being mounted or from being written to, Application Guard does not work and results in an error message (**0x80070013 ERROR_WRITE_PROTECT**).

### Why did Application Guard stop working after I turned off hyperthreading?

If hyperthreading is disabled (because of an update applied through a KB article or through BIOS settings), there is a possibility Application Guard no longer meets the minimum requirements.

### Why am I getting the error message "ERROR_VIRTUAL_DISK_LIMITATION"?

Application Guard might not work correctly on NTFS compressed volumes. If this issue persists, try uncompressing the volume.

### Why am I getting the error message "ERR_NAME_NOT_RESOLVED" after not being able to reach the PAC file?

This is a known issue. To mitigate this you need to create two firewall rules. For information about creating a firewall rule by using Group Policy, see the following resources:

- [Create an inbound icmp rule](../windows-firewall/create-an-inbound-icmp-rule.md)
- [Open Group Policy management console for Microsoft Defender Firewall](../windows-firewall/open-the-group-policy-management-console-to-windows-firewall-with-advanced-security.md)

#### First rule (DHCP Server)
1. Program path: `%SystemRoot%\System32\svchost.exe`

2. Local Service: `Sid:  S-1-5-80-2009329905-444645132-2728249442-922493431-93864177  (Internet Connection Service (SharedAccess))`

3. Protocol UDP

4. Port 67

#### Second rule (DHCP Client)
This is the same as the first rule, but scoped to local port 68. In the Microsoft Defender Firewall user interface go through the following steps:

1. Right-click on inbound rules, and then create a new rule.

2. Choose **custom rule**.

3. Specify the following program path: `%SystemRoot%\System32\svchost.exe`.

4. Specify the following settings:
    - Protocol Type: UDP
    - Specific ports: 67
    - Remote port: any

5. Specify any IP addresses.

6. Allow the connection.

7. Specify to use all profiles.

8. The new rule should show up in the user interface. Right click on the **rule** > **properties**.

9. In the **Programs and services** tab, under the **Services** section, select **settings**.

10. Choose **Apply to this Service** and select **Internet Connection Sharing (ICS) Shared Access**.

### Why can I not launch Application Guard when Exploit Guard is enabled?

There is a known issue such that if you change the Exploit Protection settings for CFG and possibly others, hvsimgr cannot launch. To mitigate this issue, go to **Windows Security** > **App and Browser control** > **Exploit Protection Setting**, and then switch CFG to **use default**.

### How can I disable portions of ICS without breaking Application Guard?

ICS is enabled by default in Windows, and ICS must be enabled in order for Application Guard to function correctly. We do not recommend disabling ICS; however, you can disable ICS in part by using a Group Policy and editing registry keys.

1. In the Group Policy setting, **Prohibit use of Internet Connection Sharing on your DNS domain network**, set it to **Disabled**.

2. Disable IpNat.sys from ICS load as follows: <br/>
`System\CurrentControlSet\Services\SharedAccess\Parameters\DisableIpNat = 1`

3. Configure ICS (SharedAccess) to enabled as follows: <br/>
`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SharedAccess\Start = 3`

4. (This is optional) Disable IPNAT as follows: <br/>
`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\IPNat\Start = 4`

5. Reboot the device.

### Why doesn't the container fully load when device control policies are enabled?

Allow-listed items must be configured as "allowed" in the Group Policy Object to ensure AppGuard works properly.

Policy: Allow installation of devices that match any of the following device IDs:

- `SCSI\DiskMsft____Virtual_Disk____`
- `{8e7bd593-6e6c-4c52-86a6-77175494dd8e}\msvhdhba`
- `VMS_VSF`
- `root\Vpcivsp`
- `root\VMBus`
- `vms_mp`
- `VMS_VSP`
- `ROOT\VKRNLINTVSP`
- `ROOT\VID`
- `root\storvsp`
- `vms_vsmp`
- `VMS_PP`

Policy: Allow installation of devices using drivers that match these device setup classes
- `{71a27cdd-812a-11d0-bec7-08002be2092f}`

## See also

[Configure Microsoft Defender Application Guard policy settings](./configure-md-app-guard.md)
