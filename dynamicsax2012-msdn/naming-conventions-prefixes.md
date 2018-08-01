---
title: 'Naming Conventions: Prefixes'
TOCTitle: Prefixes
ms:assetid: ad8010d1-018b-4a1a-874e-980fabf97f9f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa854590(v=AX.60)
ms:contentKeyID: 35249722
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Naming Conventions: Prefixes [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

## Subject Area Object Prefix

A subject area specific application object is prefixed with the name of the subject area the object belongs to, for example Cust\*, Invent\*, Ledger\*, Proj\*, Vend\*.

Examples:

WMSOrderSplit

CustBankAccount

CustBalanceCurrency

InventAccountType

## Application Area Object Prefix

An application area object is prefixed with the name of the application area the object belongs to.

Examples:

Aif\*

Sys\*.

## The DEL\_ Prefix

DEL\_ is a special prefix. It is an abbreviation for Deleted and is used for application objects that will be deleted. After an object is prefixed with DEL\_, it will be supported for a release and then deleted in the next version of the product.

DEL\_ tables and fields are necessary to allow data update. Such objects allow access to old data that must be migrated to a new location.

When an object with a DEL\_ prefix is introduced, the update mechanisms handle changes in the standard application, for example by moving fields and X++ code to the table that replaces the one with the DEL\_ prefix. But, if you have written X++ code that references an application object that has been given a DEL\_ prefix, you have to update these references yourself.

## See also

[Naming Conventions](naming-conventions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

