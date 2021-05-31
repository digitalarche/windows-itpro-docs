---
title: Multivariant (Windows 10)
description: This section describes the Multivariant settings that you can configure in provisioning packages for Windows 10 using Windows Configuration Designer.
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
author: greg-lindsay
ms.localizationpriority: medium
ms.author: greglin
ms.topic: article
ms.reviewer: 
manager: dansimp
---

# Multivariant (Windows Configuration Designer reference)

Use to select a default profile for mobile devices that have multivariant configurations. 

## Applies to

| Setting   | Desktop editions | Mobile editions | Surface Hub | HoloLens | IoT Core |
| --- | :---: | :---: | :---: | :---: | :---: |
| DefaultProfile |   | X |  |  |  |

If you will be adding [multivariant settings](../provisioning-packages/provisioning-multivariant.md) to your provisioning package,  you can use the **DefaultProfile** setting to specify which variant should be applied by default if OOBE is skipped. In the **DefaultProfile** field, enter the UINAME from your customizations.xml that you want to use as default.