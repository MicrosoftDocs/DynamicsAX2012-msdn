---
title: APIs in the Standard Application
TOCTitle: APIs
ms:assetid: d4fae32d-be56-4389-8c87-7b67a570e4bb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa873132(v=AX.60)
ms:contentKeyID: 35252018
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# APIs in the Standard Application 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The internal APIs (Application Programming Interfaces) in the application must be used when interfacing to their part of the application.

The application must provide APIs for accessing and protecting the functionality in the application that might be of use in other modules.

Characteristics of an internal API are as follows:

  - It is class-based.

  - The user of the API should only know what the API does or is used for. They shouldn't have to know how the API is implemented.

The purpose of the API can be the following:

  - To provide a simple interface to some complex structures.

  - To provide a well-defined interface to some widely used functionality.

  - To protect the underlying database structures from incorrect use.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

