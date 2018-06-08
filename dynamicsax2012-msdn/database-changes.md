---
title: Database Changes
TOCTitle: Database Changes
ms:assetid: b79fae98-c6e8-45bf-b0fd-cd262def5675
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272128(v=AX.60)
ms:contentKeyID: 36542143
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Database Changes 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Several of the database features added in Microsoft Dynamics AX 2012 will affect your Enterprise Portal application. The following sections discuss each of these features and how they affect the Enterprise Portal application that you are converting.


> [!TIP]
> <P>If you have to make database changes for your Enterprise Portal application, try to make them all at the same time at the start of the conversion process to Microsoft Dynamics AX 2012. Making the database changes in incremental steps is possible, but it can cause re-work for other parts of your Enterprise Portal application.</P>



## Surrogate Keys

Several tables in Microsoft Dynamics AX have implemented surrogate keys. You will have to modify your data sets and User Controls to use these surrogate key values instead of the key values that were previously used. You might also decide to implement surrogate keys for some of the tables you created for your Enterprise Portal application. See [Surrogate Keys](surrogate-keys.md) for more information.

## Table Inheritance

Table inheritance has been implemented throughout Microsoft Dynamics AX. Tables that you access with your Enterprise Portal application may now be part of a table hierarchy. If your application accesses tables that are part of a hierarchy, you will have to modify the data sets and User Controls that access those tables. Make sure that the data sets for your application access the appropriate table in the hierarchy. Also, update any fields in User Controls to make sure that they are accessing data from the correct table in the hierarchy.

If you create your own tables for your Enterprise Portal application, you should re-examine them to determine whether they would benefit from a table hierarchy. Using a table hierarchy can provide a better user experience for your Enterprise Portal application.

See [Table Inheritance](table-inheritance.md) for more information about how to work with tables that are part of a table hierarchy.

