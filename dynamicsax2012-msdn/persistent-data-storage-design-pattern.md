---
title: Persistent Data Storage Design Pattern
TOCTitle: Persistent Data Storage
ms:assetid: 397a0c1b-2015-4997-bfab-c82232154756
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa636810(v=AX.60)
ms:contentKeyID: 35242875
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Persistent Data Storage Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When working with persistent storage not described in the Data Dictionary, add version control features to read previously saved data to be read later when the structure is changed.

## Situation

Your program saves some data for later use in a structure not supported by the Data Dictionary.

You later change the format of the data to be stored.

You want to read and recognize data stored in old formats rather than having problems with the data, eventually deleting it.

## Solution

Whenever you save data persistently in structures unknown to the Data Dictionary (such as contents of containers in the database or data in flat files on a disk), add a version number to the structure as the first entry.

When you write data, set the initial version number to 1. When you later modify the structure, it should still be possible to read the old structure and increment the version number. Make it possible to also read the new structure.

When reading data, process it based on the version number found as the first entry.

If you read data older than the current version, interpret it as best you can, or, if you cannot use it in any meaningful way, abort the operation with a meaningful message to the user.

## Background

Structures that were supposed to remain unchanged may eventually change. It is often the case that old data cannot be read when it is needed the most.

Known uses:

  - All pack/unpack methods on RunBase

  - AOT Export file format (.xpo)

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

