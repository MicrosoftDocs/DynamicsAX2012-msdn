---
title: Extended Field IDs
TOCTitle: Extended Field IDs
ms:assetid: 511dfa4b-d268-4243-b061-08854d952c2f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa630118(v=AX.60)
ms:contentKeyID: 35244216
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Extended Field IDs 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Extended field IDs are used to refer to a particular field within a field array. An extended field ID's array index is packed in the high word, and the actual field ID is packed in the low word as shown in the following figure.

![Storage in an extended field ID](images/Aa630118.ExtFieldID(en-us,AX.60).gif "Storage in an extended field ID")

**Storage of an array index and field ID in an extended field ID**

The following methods are available in the [Global Class](https://msdn.microsoft.com/en-us/library/gg836018\(v=ax.60\)) to manipulate extended field IDs:

  - fieldExt2Id – Converts an extended field ID to an ordinary ID.

  - fieldId2Ext – Converts an ordinary field ID to an extended ID.

  - fieldExt2Idx – Returns the array index of an extended field ID.

Non-array fields also have an array index and are treated as an array field that contains only one element, meaning that their array index is 1. This index can hold the value 0 or 1. The same field can have two different field IDs, one being 1\<\<16 bigger than the other. These two IDs can be used interchangeably, and the system processes them as if they were identical.

It is best practice to use the fieldExt2Id method to remove the array index part of a field ID, if it is not needed.

## See also

[Best Practices: Table Fields](best-practices-table-fields.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

