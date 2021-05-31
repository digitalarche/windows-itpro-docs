---
title: Audit Other Privilege Use Events (Windows 10)
description: Learn about the audit other privilege use events, an auditing subcategory that should not have any events in it but enables generation of event 4985(S).
ms.assetid: 5f7f5b25-42a6-499f-8aa2-01ac79a2a63c
ms.reviewer: 
manager: dansimp
ms.author: dansimp
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.localizationpriority: none
author: dansimp
ms.date: 04/19/2017
ms.technology: mde
---

# Audit Other Privilege Use Events

**Applies to**
- Windows 10
- Windows Server 2016


This auditing subcategory should not have any events in it, but for some reason Success auditing will enable generation of event 4985(S): The state of a transaction has changed.

| Computer Type     | General Success | General Failure | Stronger Success | Stronger Failure | Comments                                                              |
|-------------------|-----------------|-----------------|------------------|------------------|-----------------------------------------------------------------------|
| Domain Controller | No              | No              | No               | No               | This auditing subcategory doesn’t have any informative events inside. |
| Member Server     | No              | No              | No               | No               | This auditing subcategory doesn’t have any informative events inside. |
| Workstation       | No              | No              | No               | No               | This auditing subcategory doesn’t have any informative events inside. |

**Events List:**

-   [4985](event-4985.md)(S): The state of a transaction has changed.



