---
title: 5068(S, F) A cryptographic function provider operation was attempted. (Windows 10)
description: Describes security event 5068(S, F) A cryptographic function provider operation was attempted.
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.localizationpriority: none
author: dansimp
ms.date: 04/19/2017
ms.reviewer: 
manager: dansimp
ms.author: dansimp
ms.technology: mde
---

# 5068(S, F): A cryptographic function provider operation was attempted.

**Applies to**
-   Windows 10
-   Windows Server 2016


This event generates in BCryptAddContextFunctionProvider() and BCryptRemoveContextFunctionProvider() functions. These are Cryptographic Next Generation (CNG) functions.

For more information about Cryptographic Next Generation (CNG) visit these pages:

-   <https://msdn.microsoft.com/library/windows/desktop/aa376214(v=vs.85).aspx>

-   <https://www.microsoft.com/download/details.aspx?id=1251>

-   <https://www.microsoft.com/download/details.aspx?id=30688>

This event is mainly used for Cryptographic Next Generation (CNG) troubleshooting.

There is no example of this event in this document.

***Subcategory:***&nbsp;[Audit Other Policy Change Events](audit-other-policy-change-events.md)

***Event Schema:***

*A cryptographic function provider operation was attempted.*

*Subject:*

> *Security ID:%1*
>
> *Account Name:%2*
>
> *Account Domain:%3*
>
> *Logon ID:%4*

*Configuration Parameters:*

> *Scope:%5*
>
> *Context:%6*
>
> *Interface:%7*
>
> *Function:%8*
>
> *Provider:%9*
>
> *Position:%10*

*Operation:%11*

*Return Code:%12*

***Required Server Roles:*** None.

***Minimum OS Version:*** Windows Server 2008, Windows Vista.

***Event Versions:*** 0.

## Security Monitoring Recommendations

-   Typically this event is required for detailed monitoring of CNG-related cryptographic functions. If you need to monitor or troubleshoot actions related to specific cryptographic functions, review this event to see if it provides the information you need.

