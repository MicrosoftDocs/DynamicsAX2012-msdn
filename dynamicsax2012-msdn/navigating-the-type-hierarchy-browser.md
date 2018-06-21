---
title: Navigating the Type Hierarchy Browser
TOCTitle: Navigating the Type Hierarchy Browser
ms:assetid: fc4910d4-39af-4111-b109-33ad670df076
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg865415(v=AX.60)
ms:contentKeyID: 35254199
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Navigating the Type Hierarchy Browser [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to navigate tables, classes, and data types in the **Type hierarchy browser**.

## Navigating Tables

Tables are listed under the **Common** node in the **Type hierarchy browser**. All tables, maps, and views extend the system table named Common.

The right pane of the **Type hierarchy browser** displays the fields, methods, and properties of the table that is selected in the left pane. The first column in the right pane lists the fields, methods, and properties of the selected table. The following columns list the fields, methods, and properties of the tables that have been inherited by the selected table. You can click the type at the top of each column to open that type in a new AOT. A shaded box is displayed in each column where a field, method, or property has been overridden. If a method can be edited, you can click on the shaded box next to that method to open the code editor.


> [!NOTE]
> <P>Maps and views are included along with the tables in the Type Hierarchy browser.</P>



### ![Gg865415.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg865415.collapse_all(en-us,AX.60).gif")Shortcut Menu Options for Tables

When you right-click a table in the left pane of the **Type hierarchy browser**, a shortcut menu opens with the following options:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Option</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Compile</strong></p></td>
<td><p>Enables you to compile the current table and related tables:</p>
<ul>
<li><p><strong>This table</strong>: compiles only the current table.</p></li>
<li><p><strong>Forward</strong>: compiles the current table and all its children.</p></li>
<li><p><strong>Backward</strong>: traverses the tree to the parent of the current table; compiles the root table and its children down to and including the current table.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Edit</strong></p></td>
<td><p>Opens the table in the code editor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Add-Ins</strong></p></td>
<td><p>Provides access to the <a href="add-ins-submenu.md">Add-Ins Submenu</a>.</p></td>
</tr>
</tbody>
</table>


## Navigating Classes

Classes are listed under the **Object** node in the **Type hierarchy browser**. All classes extend the system class named Object. Information is available for application and system classes.

The right pane of the **Type hierarchy browser** displays the methods and properties of the class that is selected in the left pane. The first column in the right pane lists the methods and properties of the selected class. The following columns list the methods and properties of the classes that have been inherited by the selected class. A shaded box is displayed in each column where a method or property has been overridden. If a method can be edited, you can click on the shaded box next to that method to open the code editor.

### ![Gg865415.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg865415.collapse_all(en-us,AX.60).gif")Shortcut Menu Options for Classes

When you click a class in the right-pane of the **Type hierarchy browser**, a shortcut menu opens with the following options:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Option</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Compile</strong></p></td>
<td><p>Enables you to compile the current class and related classes:</p>
<ul>
<li><p><strong>This class</strong>: compiles only the current class.</p></li>
<li><p><strong>Forward</strong>: compiles the current class and all its children.</p></li>
<li><p><strong>Backward</strong>: traverses the tree to the parent of the current class; compiles the root class and its children down to and including the current class.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Edit</strong></p></td>
<td><p>Opens the class in the code editor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Add-Ins</strong></p></td>
<td><p>Provides access to the <a href="add-ins-submenu.md">Add-Ins Submenu</a>.</p></td>
</tr>
</tbody>
</table>


## Navigating Data Types

Extended data types are listed under the **Container**, **Date**, **Enum**, **Guid**, **int**, **Int64**, **Real**, **str**, **timeOfDay**, or **UtcDateTime** nodes, depending on which primitive data type they extend.

The right pane shows the properties for the data types, and enables you to see which level they are defined on.

### ![Gg865415.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg865415.collapse_all(en-us,AX.60).gif")Shortcut Menu Options for Data Types

When you right-click a data type in the left pane of the **Type hierarchy browser**, a shortcut menu opens with the following options:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Option</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Add-Ins</strong></p></td>
<td><p>Provides access to the <a href="add-ins-submenu.md">Add-Ins Submenu</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[Type Hierarchy Browser and Type Hierarchy Context](type-hierarchy-browser-and-type-hierarchy-context.md)

[How to: Open the Type Hierarchy Browser](how-to-open-the-type-hierarchy-browser.md)

[How to: Open the Type Hierarchy Context](how-to-open-the-type-hierarchy-context.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

