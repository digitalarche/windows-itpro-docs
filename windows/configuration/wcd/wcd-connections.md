---
title: Connections (Windows 10)
description: This section describes the Connections settings that you can configure in provisioning packages for Windows 10 using Windows Configuration Designer.
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
author: greg-lindsay
ms.localizationpriority: medium
ms.author: greglin
ms.topic: article
ms.date: 04/30/2018
ms.reviewer: 
manager: dansimp
---

# Connections (Windows Configuration Designer reference)

Use to configure settings related to various types of phone connections.

## Applies to

| Setting groups  | Desktop editions | Mobile editions | Surface Hub | HoloLens | IoT Core |
| --- | :---: | :---: | :---: | :---: | :---: |
| All settings  | X |  X  | X |  |  |


For each setting group:
1. In **Available customizations**, select the setting group (such as **Cellular**), enter a friendly name for the connection, and then click **Add**.
2. In **Available customizations**, select the name that you just created. 

## Cellular

See [CM_CellularEntries configuration service provider (CSP)](/windows/client-management/mdm/cm-cellularentries-csp) for settings and values.

## EnterpriseAPN

See [Configure cellular settings for tablets and PCs](../provisioning-apn.md) and 
[EnterpriseAPN CSP](/windows/client-management/mdm/enterpriseapn-csp) for settings and values.

## General

Use **General > DataRoam** to set the default value for the **Default roaming options** option in the **Settings > cellular + SIM** area on the device. Select between **DoNotRoam**, **DomesticRoaming**, or **InternationalRoaming**. 

## Policies

See [CMPolicy CSP](/windows/client-management/mdm/cmpolicy-csp) for settings and values.

## Proxies

See [CM_ProxyEntries CSP](/windows/client-management/mdm/cm-proxyentries-csp) for settings and values.