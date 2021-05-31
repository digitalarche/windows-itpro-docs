---
title: Available Microsoft Defender SmartScreen Group Policy and mobile device management (MDM) settings (Windows 10)
description: A list of all available settings for Microsoft Defender SmartScreen using Group Policy and mobile device management (MDM) settings.
keywords: SmartScreen Filter, Windows SmartScreen, Microsoft Defender SmartScreen
ms.prod: m365-security
ms.mktglfcycl: explore
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.localizationpriority: medium
ms.date: 09/28/2020
ms.reviewer: 
manager: dansimp
ms.author: dansimp
ms.technology: mde
---
# Available Microsoft Defender SmartScreen Group Policy and mobile device management (MDM) settings
**Applies to:**

- Windows 10
- Windows 10 Mobile

Microsoft Defender SmartScreen works with Intune, Group Policy, and mobile device management (MDM) settings to help you manage your organization's computer settings. Based on how you set up Microsoft Defender SmartScreen, you can show employees a warning page and let them continue to the site, or you can block the site entirely.

See [Windows 10 (and later) settings to protect devices using Intune](/intune/endpoint-protection-windows-10#windows-defender-smartscreen-settings) for the controls you can use in Intune.


## Group Policy settings
SmartScreen uses registry-based Administrative Template policy settings.
<table>
<tr>
<th align="left">Setting</th>
<th align="left">Supported on</th>
<th align="left">Description</th>
</tr>
<tr>
<td><b>Windows 10, version 2004:</b><br>Administrative Templates\Windows Components\Windows Defender SmartScreen\Explorer\Configure Windows Defender SmartScreen<p>
<td><b>Windows 10, version 1703:</b><br>Administrative Templates\Windows Components\Windows Defender SmartScreen\Explorer\Configure Windows Defender SmartScreen<p><b>Windows 10, Version 1607 and earlier:</b><br>Administrative Templates\Windows Components\File Explorer\Configure Windows SmartScreen<br><br>
<b>At least Windows Server 2012, Windows 8 or Windows RT</b></td>
<td>This policy setting turns on Microsoft Defender SmartScreen.<p>If you enable this setting, it turns on Microsoft Defender SmartScreen and your employees are unable to turn it off. Additionally, when enabling this feature, you must also pick whether Microsoft Defender SmartScreen should Warn your employees or Warn and prevent bypassing the message (effectively blocking the employee from the site).<p>If you disable this setting, it turns off Microsoft Defender SmartScreen and your employees are unable to turn it on.<p>If you don't configure this setting, your employees can decide whether to use Microsoft Defender SmartScreen.</td>
</tr>
<tr>
<td><b>Windows 10, version 2004:</b><br>Administrative Templates\Windows Components\Windows Defender SmartScreen\Explorer\Configure App Install Control</td>
<td><b>Windows 10, version 1703:</b><br>Administrative Templates\Windows Components\Windows Defender SmartScreen\Explorer\Configure App Install Control</td>
<td>This policy setting is intended to prevent malicious content from affecting your user's devices when downloading executable content from the internet.</br></br> This setting does not protect against malicious content from USB devices, network shares, or other non-internet sources.</p><p><b>Important:</b> Using a trustworthy browser helps ensure that these protections work as expected.</p></td>
</tr>
<tr>
<td><b>Windows 10, version 2004:</b><br>Administrative Templates\Windows Components\Windows Defender SmartScreen\Microsoft Edge\Configure Windows Defender SmartScreen (Microsoft Edge version 45 and earlier)<p>Administrative Templates\Microsoft Edge\SmartScreen settings\Configure Microsoft Defender SmartScreen (Microsoft Edge version 77 or later)<p><b>Windows 10, version 1703:</b><br>Administrative Templates\Windows Components\Windows Defender SmartScreen\Microsoft Edge\Configure Windows Defender SmartScreen (Microsoft Edge version 45 and earlier)<p>Administrative Templates\Microsoft Edge\SmartScreen settings\Configure Microsoft Defender SmartScreen (Microsoft Edge version 77 or later)<p><b>Windows 10, Version 1607 and earlier:</b><br>Administrative Templates\Windows Components\Microsoft Edge\Configure Windows SmartScreen</td>
<td>Microsoft Edge on Windows 10 or later</td>
<td>This policy setting turns on Microsoft Defender SmartScreen.<p>If you enable this setting, it turns on Microsoft Defender SmartScreen and your employees are unable to turn it off.<p>If you disable this setting, it turns off Microsoft Defender SmartScreen and your employees are unable to turn it on.<p>If you don't configure this setting, your employees can decide whether to use Microsoft Defender SmartScreen.</td>
</tr>
<tr>
<td><b>Windows 10, version 2004:</b><br>Administrative Templates\Windows Components\Windows Defender SmartScreen\Microsoft Edge\Prevent bypassing Windows Defender SmartScreen prompts for files (Microsoft Edge version 45 and earlier)<p>Administrative Templates\Microsoft Edge\SmartScreen settings\Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads (Microsoft Edge version 77 or later)<p><b>Windows 10, version 1703:</b><br>Administrative Templates\Windows Components\Windows Defender SmartScreen\Microsoft Edge\Prevent bypassing Windows Defender SmartScreen prompts for files (Microsoft Edge version 45 and earlier)<p>Administrative Templates\Microsoft Edge\SmartScreen settings\Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads (Microsoft Edge version 77 or later)<p><b>Windows 10, Version 1511 and 1607:</b><br>Administrative Templates\Windows Components\Microsoft Edge\Prevent bypassing Windows SmartScreen prompts for files</td>
<td>Microsoft Edge on Windows 10, version 1511 or later</td>
<td>This policy setting stops employees from bypassing the Microsoft Defender SmartScreen warnings about potentially malicious files.<p>If you enable this setting, it stops employees from bypassing the warning, stopping the file download.<p>If you disable or don't configure this setting, your employees can bypass the warnings and continue to download potentially malicious files.</td>
</tr>
<tr>
<td><b>Windows 10, version 2004:</b><br>Administrative Templates\Windows Components\Windows Defender SmartScreen\Microsoft Edge\Prevent bypassing Windows Defender SmartScreen prompts for sites (Microsoft Edge version 45 and earlier)<p>Administrative Templates\Microsoft Edge\SmartScreen settings\Prevent bypassing Microsoft Defender SmartScreen prompts for sites (Microsoft Edge version 77 or later)<p><b>Windows 10, version 1703:</b><br>Administrative Templates\Windows Components\Windows Defender SmartScreen\Microsoft Edge\Prevent bypassing Windows Defender SmartScreen prompts for sites (Microsoft Edge version 45 and earlier)<p>Administrative Templates\Microsoft Edge\SmartScreen settings\Prevent bypassing Microsoft Defender SmartScreen prompts for sites (Microsoft Edge version 77 or later)<p><b>Windows 10, Version 1511 and 1607:</b><br>Administrative Templates\Windows Components\Microsoft Edge\Prevent bypassing Windows SmartScreen prompts for sites</td>
<td>Microsoft Edge on Windows 10, version 1511 or later</td>
<td>This policy setting stops employees from bypassing the Microsoft Defender SmartScreen warnings about potentially malicious sites.<p>If you enable this setting, it stops employees from bypassing the warning, stopping them from going to the site.<p>If you disable or don't configure this setting, your employees can bypass the warnings and continue to visit a potentially malicious site.</td>
</tr>
<tr>
<td>Administrative Templates\Windows Components\Internet Explorer\Prevent managing SmartScreen Filter</td>
<td>Internet Explorer 9 or later</td>
<td>This policy setting prevents the employee from managing Microsoft Defender SmartScreen.<p>If you enable this policy setting, the employee isn't prompted to turn on Microsoft Defender SmartScreen. All website addresses that are not on the filter's allow list are sent automatically to Microsoft without prompting the employee.<p>If you disable or don't configure this policy setting, the employee is prompted to decide whether to turn on Microsoft Defender SmartScreen during the first-run experience.</td>
</tr>
<tr>
<td>Administrative Templates\Windows Components\Internet Explorer\Prevent bypassing SmartScreen Filter warnings</td>
<td>Internet Explorer 8 or later</td>
<td>This policy setting determines whether an employee can bypass warnings from Microsoft Defender SmartScreen.<p>If you enable this policy setting, Microsoft Defender SmartScreen warnings block the employee.<p>If you disable or don't configure this policy setting, the employee can bypass Microsoft Defender SmartScreen warnings.</td>
</tr>
<tr>
<td>Administrative Templates\Windows Components\Internet Explorer\Prevent bypassing SmartScreen Filter warnings about files that are not commonly downloaded from the Internet</td>
<td>Internet Explorer 9 or later</td>
<td>This policy setting determines whether the employee can bypass warnings from Microsoft Defender SmartScreen. Microsoft Defender SmartScreen warns the employee about executable files that Internet Explorer users do not commonly download from the Internet.<p>If you enable this policy setting, Microsoft Defender SmartScreen warnings block the employee.<p>If you disable or don't configure this policy setting, the employee can bypass Microsoft Defender SmartScreen warnings.</td>
</tr>
</table>

## MDM settings
If you manage your policies using Microsoft Intune, you'll want to use these MDM policy settings. All settings support both desktop computers (running Windows 10 Pro or Windows 10 Enterprise, enrolled with Microsoft Intune) and Windows 10 Mobile devices.  <br><br> 
For Microsoft Defender SmartScreen Edge MDM policies, see [Policy CSP - Browser](/windows/client-management/mdm/policy-csp-browser).
<table>
<tr>
<th align="left">Setting</th>
<th align="left">Supported versions</th>
<th align="left">Details</th>
</tr>
<tr>
<td>AllowSmartScreen</td>
<td>Windows 10</td>
<td>
<ul>
<li><b>URI full path.</b> ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen</li>
<li><b>Data type.</b> Integer</li>
<li><b>Allowed values:</b><ul>
<li><b>0 .</b> Turns off Microsoft Defender SmartScreen in Edge.</li>
<li><b>1.</b> Turns on Microsoft Defender SmartScreen in Edge.</li></ul></li></ul>
</td>
</tr>
<tr>
<td>EnableAppInstallControl</td>
<td>Windows 10, version 1703</td>
<td>
<ul>
<li><b>URI full path.</b> ./Vendor/MSFT/Policy/Config/SmartScreen/EnableAppInstallControl</li>
<li><b>Data type.</b> Integer</li>
<li><b>Allowed values:</b><ul>
<li><b>0 .</b> Turns off Application Installation Control, allowing users to download and install files from anywhere on the web.</li>
<li><b>1.</b> Turns on Application Installation Control, allowing users to install apps from the Microsoft Store only.</li></ul></li></ul>
</td>
</tr>
<tr>
<td>EnableSmartScreenInShell</td>
<td>Windows 10, version 1703</td>
<td>
<ul>
<li><b>URI full path.</b> ./Vendor/MSFT/Policy/Config/SmartScreen/EnableSmartScreenInShell</li>
<li><b>Data type.</b> Integer</li>
<li><b>Allowed values:</b><ul>
<li><b>0 .</b> Turns off Microsoft Defender SmartScreen in Windows for app and file execution.</li>
<li><b>1.</b> Turns on Microsoft Defender SmartScreen in Windows for app and file execution.</li></ul></li></ul>
</td>
</tr>
<tr>
<td>PreventOverrideForFilesInShell</td>
<td>Windows 10, version 1703</td>
<td>
<ul>
<li><b>URI full path.</b> ./Vendor/MSFT/Policy/Config/SmartScreen/PreventOverrideForFilesInShell</li>
<li><b>Data type.</b> Integer</li>
<li><b>Allowed values:</b><ul>
<li><b>0 .</b> Employees can ignore Microsoft Defender SmartScreen warnings and run malicious files.</li>
<li><b>1.</b> Employees can't ignore Microsoft Defender SmartScreen warnings and run malicious files.</li></ul></li></ul>
</td>
</tr>
<tr>
<td>PreventSmartScreenPromptOverride</td>
<td>Windows 10, Version 1511 and later</td>
<td>
<ul>
<li><b>URI full path.</b> ./Vendor/MSFT/Policy/Config/Browser/PreventSmartscreenPromptOverride</li>
<li><b>Data type.</b> Integer</li>
<li><b>Allowed values:</b><ul>
<li><b>0 .</b> Employees can ignore Microsoft Defender SmartScreen warnings.</li>
<li><b>1.</b> Employees can't ignore Microsoft Defender SmartScreen warnings.</li></ul></li></ul>
</td>
</tr>
<tr>
<td>PreventSmartScreenPromptOverrideForFiles</td>
<td>Windows 10, Version 1511 and later</td>
<td>
<ul>
<li><b>URI full path.</b> ./Vendor/MSFT/Policy/Config/Browser/PreventSmartScreenPromptOverrideForFiles</li>
<li><b>Data type.</b> Integer</li>
<li><b>Allowed values:</b><ul>
<li><b>0 .</b> Employees can ignore Microsoft Defender SmartScreen warnings for files.</li>
<li><b>1.</b> Employees can't ignore Microsoft Defender SmartScreen warnings for files.</li></ul></li></ul>
</td>
</tr>
</table>

## Recommended Group Policy and MDM settings for your organization
By default, Microsoft Defender SmartScreen lets employees bypass warnings. Unfortunately, this feature can let employees continue to an unsafe site or to continue to download an unsafe file, even after being warned. Because of this possibility, we strongly recommend that you set up Microsoft Defender SmartScreen to block high-risk interactions instead of providing just a warning.

To better help you protect your organization, we recommend turning on and using these specific Microsoft Defender SmartScreen Group Policy and MDM settings.
<table>
<tr>
<th align="left">Group Policy setting</th>
<th align="left">Recommendation</th>
</tr>
<tr>
<td>Administrative Templates\Windows Components\Microsoft Edge\Configure Windows Defender SmartScreen (Microsoft Edge version 45 and earlier)<p>Administrative Templates\Microsoft Edge\SmartScreen settings\Configure Microsoft Defender SmartScreen (Microsoft Edge version 77 or later)</td>
<td><b>Enable.</b> Turns on Microsoft Defender SmartScreen.</td>
</tr>
<tr>
<td>Administrative Templates\Windows Components\Microsoft Edge\Prevent bypassing Windows Defender SmartScreen prompts for sites (Microsoft Edge version 45 and earlier)<p>Administrative Templates\Microsoft Edge\SmartScreen settings\Prevent bypassing Windows Defender SmartScreen prompts for sites (Microsoft Edge version 77 or later)</td>
<td><b>Enable.</b> Stops employees from ignoring warning messages and continuing to a potentially malicious website.</td>
</tr>
<tr>
<td>Administrative Templates\Windows Components\Microsoft Edge\Prevent bypassing Windows Defender SmartScreen prompts for files (Microsoft Edge version 45 and earlier)<p>Administrative Templates\Microsoft Edge\SmartScreen settings\Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads (Microsoft Edge version 77 or later) </td>
<td><b>Enable.</b> Stops employees from ignoring warning messages and continuing to download potentially malicious files.</td>
</tr>
<tr>
<td>Administrative Templates\Windows Components\File Explorer\Configure Windows Defender SmartScreen</td>
<td><b>Enable with the Warn and prevent bypass option.</b> Stops employees from ignoring warning messages about malicious files downloaded from the Internet.</td>
</tr>
</table>
<p>
<table>
<tr>
<th align="left">MDM setting</th>
<th align="left">Recommendation</th>
</tr>
<tr>
<td>Browser/AllowSmartScreen</td>
<td><b>1.</b> Turns on Microsoft Defender SmartScreen.</td>
</tr>
<tr>
<td>Browser/PreventSmartScreenPromptOverride</td>
<td><b>1.</b> Stops employees from ignoring warning messages and continuing to a potentially malicious website.</td>
</tr>
<tr>
<td>Browser/PreventSmartScreenPromptOverrideForFiles</td>
<td><b>1.</b> Stops employees from ignoring warning messages and continuing to download potentially malicious files.</td>
</tr>
<tr>
<td>SmartScreen/EnableSmartScreenInShell</td>
<td><b>1.</b> Turns on Microsoft Defender SmartScreen in Windows.<p>Requires at least Windows 10, version 1703.</td>
</tr>
<tr>
<td>SmartScreen/PreventOverrideForFilesInShell</td>
<td><b>1.</b> Stops employees from ignoring warning messages about malicious files downloaded from the Internet.<p>Requires at least Windows 10, version 1703.</td>
</tr>
</table> 

## Related topics
- [Threat protection](../index.md)

- [Microsoft Defender SmartScreen overview](microsoft-defender-smartscreen-overview.md)

- [Available Group Policy and Mobile Device Management (MDM) settings for Microsoft Edge](/microsoft-edge/deploy/available-policies)