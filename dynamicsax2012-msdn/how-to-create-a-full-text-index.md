---
title: 'How to: Create a Full Text Index'
TOCTitle: 'How to: Create a Full Text Index'
ms:assetid: 473ac994-5ccd-4ac7-83c3-c6c38949bfca
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845129(v=AX.60)
ms:contentKeyID: 35243009
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Full Text Index 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to create a full text index on a table in Microsoft Dynamics AX.

A full text index contains information about each significant word in the indexed string field, not for only the word at the start of the string. This provides fast access to table rows that have a target word embedded in a string field.

You can create a maximum of one full text index per table. You can have multiple columns of type **String** in a single full text index. Also, the **StringSize** property of the string field can be set to a number or to **(Memo)**. Also, the full text index field can be based on an extended data type.

## Create a Full Text Index

This section describes how to create a full text index on a table by using the AOT.

1.  Create a table named **FtiTable** with two string fields named **Field1** and **Field2**. If you need information about how to create a table, see [How to: Create Tables](how-to-create-tables.md).

2.  For better testing, increase the **StringSize** property from its default value to **64** on both fields.

3.  Set the **TableGroup** property to **Main** on the **FriTable** table.
    

    > [!NOTE]
    > <P>A table can have a full text index only if the <STRONG>TableGroup</STRONG> property is set to <STRONG>Main</STRONG> or <STRONG>Group</STRONG> on the table.</P>



4.  Expand the **FtiTable** node, right-click the **Full Text Indexes** node, and then click **New Full Text Index**. This creates a node named **FullTextIndex1**.

5.  Right-click the **FullTextIndex1** node, and then click **New Field**.

6.  Click the new index field node so that you can see its properties in the **Properties** window.

7.  In the **Properties** window for the new index field, set the **DataField** property to **Field2**.

8.  Repeat the previous three steps to add **Field1** as a second column to **FullTextIndex1**. Or instead you can drag the **FtiTable** \> **Fields** \> **Field1** node and drop it onto the **FullTextIndex1** node.

## Next Steps

For information about how to create queries that benefit from a full text index, see [How to: Use a Full Text Index](how-to-use-a-full-text-index.md).

## See also

[Full Text Index Overview](full-text-index-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

