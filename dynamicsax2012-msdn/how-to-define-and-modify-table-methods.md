---
title: 'How to: Define and Modify Table Methods'
TOCTitle: 'How to: Define and Modify Table Methods'
ms:assetid: 66389832-d1d7-4d79-a943-1fecd527f289
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa653071(v=AX.60)
ms:contentKeyID: 35244698
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Define and Modify Table Methods [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you create a new table in the Application Object Tree (AOT), MorphX automatically creates several methods for it. By adding X++ code to these system-defined methods, you can modify the default behavior of the system. You can also define your own methods. The system- and the user-defined methods share the same scope in the table. This makes it easy to add new methods and use them from the system defined methods. Notice that you cannot modify the return type, parameter list, or parameter types for the system defined methods, but you can add parameters if you declare a default value for them. This differs from any additional methods you define. These can be modified in any way; you can modify the return type, the parameter list, and parameter types.

To manage changes to AOT objects, a version control system is available. For more information, see [Version Control System](version-control-system.md).

## Modify a System-defined Method for a Table

1.  In the AOT, expand the **Data Dictionary** node, and then locate the table that you want to modify.

2.  Expand the **Methods** node for the table, and then double-click the method that you want to modify.

3.  Modify or add to the code as necessary.

4.  Compile and then click Save.

## Create a New Method

1.  In the AOT, locate the table that you want to modify.

2.  Right-click the **Methods** node for the table, and then click **New Method** on the shortcut menu.

3.  Rename the new method.

4.  Double-click the new method to open the code editor.

5.  Add code to the method in the editor.

6.  Compile and then click Save.

Table methods can access all the other available methods. Any method defined for a table shares the same scope.

## See also

[How to: Create Tables](how-to-create-tables.md)

[Table Methods](https://msdn.microsoft.com/en-us/library/aa625830\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

