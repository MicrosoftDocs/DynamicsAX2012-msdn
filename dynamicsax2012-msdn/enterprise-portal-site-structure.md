---
title: Enterprise Portal Site Structure
TOCTitle: Site Structure
ms:assetid: 12ffbaa1-b291-4bc3-a350-4ba27f7aee4c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc583064(v=AX.60)
ms:contentKeyID: 35244926
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enterprise Portal Site Structure 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

SharePoint is the core technology for Enterprise Portal. A single SharePoint site is the base for an Enterprise Portal installation. The various components for Enterprise Portal are stored in this site. The following illustration shows the overall site structure for Enterprise Portal.

![Enterprise Portal Site Structure](images/Cc583064.EP_Structure(AX.60).gif "Enterprise Portal Site Structure")

**Enterprise Portal Site Structure**

The Web Modules resource in the AOT defines the overall structure and top-level navigation for Enterprise Portal. You will learn more about this in [Web Modules Overview](web-modules-overview.md).

## Role Center Pages

The main Enterprise Portal site contains several role center pages that are customized for each role in the company. The first page the user sees when they open Enterprise Portal is the role center they are assigned to. The page contains the most relevant content for the specific user.

## Module Sites

The main Enterprise Portal site contains several subsites. Each subsite is referred to as a module site. These module sites have names such as Sales, Purchase, and Project. They represent distinct areas in which users can perform tasks in Enterprise Portal.

## Pages

Each module site contains the various pages that are used for that site. The module site has a site home page that shows the most important content for the module site. The site home page is displayed when the user clicks the top-level navigation tab for the module site. Other pages like list pages and task pages are also found in the module site.

