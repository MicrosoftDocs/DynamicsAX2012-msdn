---
title: Extended Data Types in the Database
TOCTitle: Extended Data Types in the Database
ms:assetid: 350998d3-c696-4077-95c4-ef636cdf9721
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb381156(v=AX.60)
ms:contentKeyID: 35242003
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Extended Data Types in the Database 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Extended data types (EDTs) are user-defined types. EDTs are based on the primitive data types boolean, integer, real, string, and date, and the composite type container. You can also base an EDT on another EDT. EDTs can be used to define fields in tables as well as to define variables in X++ code.

This feature is not implemented as an X++ language construct. Extended data types are defined in the Application Object Tree (AOT) under the **Data Dictionary** \> **Extended Data Types** node.


> [!WARNING]
> <P>Starting in Microsoft Dynamics AX 2012, you can no longer define relations under an EDT element in the AOT. If your system has any EDT relations, you should migrate those relations to the appropriate table elements. For more information, see <A href="edt-relation-migration-tool.md">EDT Relation Migration Tool</A>.</P>



## In This Section

This section contains the following topics:

[Extended Data Types (EDTs)](extended-data-types-edts.md)

[How to: Create an Extended Data Type](how-to-create-an-extended-data-type.md)

[How to: Define an Extended Data Type as an Array](how-to-define-an-extended-data-type-as-an-array.md)

[EDT Relation Migration Tool](edt-relation-migration-tool.md)

## See also

[Extended Data Types (EDTs)](extended-data-types-edts.md)

[Database for Microsoft Dynamics AX](database-for-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

