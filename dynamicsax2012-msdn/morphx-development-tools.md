---
title: MorphX Development Tools
TOCTitle: MorphX Development Tools
ms:assetid: ab958faf-428d-4730-af69-926cc4363b96
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa853691(v=AX.60)
ms:contentKeyID: 35249628
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# MorphX Development Tools 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

MorphX development tools are available in the **Tools** menu. Many are also available from the [Add-ins shortcut menu](add-ins-submenu.md) in the Application Object Tree (AOT). When tools are activated from the **Add-Ins** menu, they take the current AOT node as the point of departure.

The [X++ code editor](x-code-editor.md), the [X++ compiler](code-compiler.md), the [Reverse Engineering Tool](reverse-engineering-tool.md), and the [tracing tools](tracing-with-the-tools-menu.md) are not available from the **Development tools** menu or the AOT **Add-Ins** menu. The code editor opens when you double-click a method or create a new job. The compiler can be accessed from the Code editor window. To open the Reverse Engineering tool, right-click a project, and then select **Add-Ins** \> **Reverse Engineer**. For information about enabling the tracing tools, see [Setting Up the Tracing Tools](setting-up-the-tracing-tools.md).

The development tools available in the **Development tools** and **Add-Ins** menus are described in the following table.


> [!NOTE]
> <P>The Code Explorer, Benchmark, and Visual MorphXplorer tools are no longer available. The Reverse Engineering tool has replaced the Visual MorphXplorer tool.</P>



<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tool</p></th>
<th><p>Opened from</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Application objects</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Application objects</strong> menu</p>
<p><strong>Add-Ins</strong> menu</p></td>
<td><p>Lists application objects, grouped by object type.</p></td>
</tr>
<tr class="even">
<td><p>Axd Wizard</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Wizards</strong> menu</p></td>
<td><p>Helps you to create a XML document (Axd) class</p></td>
</tr>
<tr class="odd">
<td><p>Check Best Practices</p></td>
<td><p><strong>Add-Ins</strong> menu</p></td>
<td><p>Checks whether your X++ code is in compliance with Microsoft Dynamics AX standards.</p>
<p><strong>Note</strong>   This command does not check all best practices and does not guarantee that your X++ code complies with Microsoft Dynamics AX standards. For more information, see <a href="best-practices-for-microsoft-dynamics-ax-development.md">Best Practices for Microsoft Dynamics AX Development</a>.</p></td>
</tr>
<tr class="even">
<td><p>Class Wizard</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Wizards</strong> menu</p></td>
<td><p>Helps you to create a new class.</p></td>
</tr>
<tr class="odd">
<td><p><a href="how-to-use-the-code-profiler.md">Code profiler</a></p></td>
<td><p><strong>Tools</strong> menu</p></td>
<td><p>Records the execution time of each line of code and enables you to analyze the data to find performance bottlenecks.</p></td>
</tr>
<tr class="even">
<td><p>Code Upgrade</p></td>
<td><p><strong>Tools</strong> menu</p></td>
<td><p>Helps you to compare and merge your X++ source code when upgrading to a new version of Microsoft Dynamics AX.</p></td>
</tr>
<tr class="odd">
<td><p>COM Class Wrapper Wizard</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Wizards</strong> menu</p></td>
<td><p>Helps you to create a wrapper class for a COM object. Ensures type safety when using dynamic binding.</p></td>
</tr>
<tr class="even">
<td><p><a href="compare-tool.md">Compare</a></p></td>
<td><p><strong>Add-Ins</strong> menu</p></td>
<td><p>Enables you to compare the current object with another object or another version of the same object.</p></td>
</tr>
<tr class="odd">
<td><p>Compare layers</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Code upgrade</strong> menu</p></td>
<td><p>Enables you to compare any two application object layers. For example, the current SYS layer and the OLD SYS layer. Creates a project that contains objects that only exist in one layer and objects that are different in the two layers.</p></td>
</tr>
<tr class="even">
<td><p>Create upgrade project</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Version upgrade</strong> menu</p></td>
<td><p>Analyzes your system and creates a project that contains the application objects that must be upgraded manually.</p></td>
</tr>
<tr class="odd">
<td><p><a href="cross-reference-tool.md">Cross-reference</a></p></td>
<td><p><strong>Tools</strong> menu</p>
<p><strong>Add-Ins</strong> menu</p></td>
<td><p>Enables you to see relationships between objects. You can see which objects use the current object and which other objects the current object uses.</p></td>
</tr>
<tr class="even">
<td><p>Debugger</p></td>
<td><p><strong>Tools</strong> menu</p></td>
<td><p>Enables you to debug your X++ code.</p>
<p>For more information, see the Debugger Help. It is available from the <strong>Help</strong> menu in the debugger and from the Microsoft Dynamics AX Debugger node in the table of contents of the Help opened from the <strong>Help</strong> &gt; <strong>Developer Help</strong> menu.</p></td>
</tr>
<tr class="odd">
<td><p>Financial Dimensions Wizard</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Wizards</strong> menu</p></td>
<td><p>Helps you add a new financial dimension to the system.</p></td>
</tr>
<tr class="even">
<td><p>Images</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Web development</strong> menu</p></td>
<td><p>Enables you to manage the images available for use in Web applications.</p></td>
</tr>
<tr class="odd">
<td><p>Label editor</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Label</strong> menu</p></td>
<td><p>Enables you to create, edit, and delete labels.</p></td>
</tr>
<tr class="even">
<td><p>Label log</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Label</strong> menu</p></td>
<td><p>Displays the history of labels in the application.</p></td>
</tr>
<tr class="odd">
<td><p><a href="how-to-create-a-label-file.md">Label file wizard</a></p></td>
<td><p><strong>Tools</strong> &gt; <strong>Label</strong> menu</p>
<p><strong>Tools</strong> &gt; <strong>Wizards</strong> menu</p></td>
<td><p>Enables you to create a new label file.</p></td>
</tr>
<tr class="even">
<td><p>Label intervals</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Label</strong> menu</p></td>
<td><p>Enables you to specify which label IDs can be used with a particular label file.</p></td>
</tr>
<tr class="odd">
<td><p>Legacy Help Texts</p></td>
<td><p><strong>Development tools</strong> menu</p></td>
<td><p>Obsolete.</p>
<p>In previous versions of Microsoft Dynamics AX, this tool enabled you to view and edit the HTML source of Help topics available for application objects.</p></td>
</tr>
<tr class="even">
<td><p>Legacy Help Validation</p></td>
<td><p><strong>Development tools</strong> menu</p></td>
<td><p>Obsolete.</p>
<p>In previous versions of Microsoft Dynamics AX, this tool enabled you to search for text and tags in documentation objects to find Help topics that do not conform to best practices for Microsoft Dynamics AX documentation.</p></td>
</tr>
<tr class="odd">
<td><p>Locked application objects</p></td>
<td><p><strong>Development tools</strong> &gt; <strong>Application objects</strong> menu</p></td>
<td><p>Displays a list of the application objects that are currently locked.</p></td>
</tr>
<tr class="even">
<td><p>Number of records</p></td>
<td><p><strong>Tools</strong> menu</p></td>
<td><p>Counts the number of records in each table in the current company.</p></td>
</tr>
<tr class="odd">
<td><p>Old application objects</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Application objects</strong> menu</p></td>
<td><p>Displays the system's old application objects and a detailed log of each object's history.</p></td>
</tr>
<tr class="even">
<td><p>Refresh AOD</p></td>
<td><p><strong>Development tools</strong> &gt; <strong>Application objects</strong> menu</p></td>
<td><p>Flushes cached application object information.</p></td>
</tr>
<tr class="odd">
<td><p>Refresh runtime model data</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Caches</strong> menu</p></td>
<td><p>Flushes cached model metadata information.</p></td>
</tr>
<tr class="even">
<td><p>Refresh Data</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Caches</strong> menu</p></td>
<td><p>Flushes cached database records.</p></td>
</tr>
<tr class="odd">
<td><p>Refresh Dictionary</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Caches</strong> menu</p></td>
<td><p>Flushes cached application object dictionary information.</p></td>
</tr>
<tr class="even">
<td><p>Reindex</p></td>
<td><p><strong>Development tools</strong> &gt; <strong>Application objects</strong> menu</p></td>
<td><p>Re-indexes the AOT.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/aa620747(v=ax.60)">Report Wizard</a></p></td>
<td><p><strong>Tools</strong> &gt; <strong>Wizards</strong> menu</p></td>
<td><p>Helps you to create a new report.</p></td>
</tr>
<tr class="even">
<td><p>Source Code Titlecase Update</p></td>
<td><p><strong>Add-Ins</strong> menu</p></td>
<td><p>Applies the correct case to objects names used in your code. For example, classes begin with an uppercase letter (for example, AddressCheck) and methods begin with a lowercase letter (for example, classDeclaration).</p></td>
</tr>
<tr class="odd">
<td><p>Style sheets and Themes</p></td>
<td><p><strong>Development tools</strong> menu</p></td>
<td><p>Enables you to create style sheets and themes. Themes are style sheets with a set of images that define the overall look of a Web site. For more information, see <a href="how-to-create-new-sharepoint-themes.md">How to: Create New SharePoint Themes</a>.</p></td>
</tr>
<tr class="even">
<td><p>Table browser</p></td>
<td><p><strong>Add-Ins</strong> menu</p></td>
<td><p>Enables you to view or update data in the current table.</p></td>
</tr>
<tr class="odd">
<td><p>Table definitions</p></td>
<td><p><strong>Tools</strong> menu</p>
<p><strong>Add-Ins</strong> menu</p></td>
<td><p>Enables you to generate a report that presents an overview of selected tables. The overview includes fields, types, labels, configuration keys, and HelpTexts.</p></td>
</tr>
<tr class="even">
<td><p><a href="type-hierarchy-browser-and-type-hierarchy-context.md">Type Hierarchy Browser and Type Hierarchy Context</a></p></td>
<td><p><strong>Tools</strong> &gt; <strong>Type hierarchy browser</strong></p>
<p><strong>Add-Ins</strong> &gt; <strong>Type hierarchy browser</strong></p>
<p><strong>Tools</strong> &gt; <strong>Type hierarchy context</strong></p></td>
<td><p>Enables you to view the hierarchy of a table, class, enum, or extended data type (EDT).</p></td>
</tr>
<tr class="odd">
<td><p><a href="unit-test-framework.md">Unit Test</a></p></td>
<td><p><strong>Tools</strong> menu</p></td>
<td><p>Enables you to use the Unit Test Framework.</p></td>
</tr>
<tr class="even">
<td><p>Usage data</p></td>
<td><p><strong>Development tools</strong> &gt; <strong>Application objects</strong> menu</p></td>
<td><p>Enables you to view the settings that a user has selected while using Microsoft Dynamics AX. These preferences are saved to make it faster for the user to use the same functionality the next time.</p></td>
</tr>
<tr class="odd">
<td><p><a href="version-control-system.md">Version control</a></p></td>
<td><p><strong>Development tools</strong> menu</p></td>
<td><p>Provides version control for all AOT objects, projects, and label files.</p></td>
</tr>
<tr class="even">
<td><p>Web sites</p></td>
<td><p><strong>Tools</strong> &gt; <strong>Web development</strong> menu</p></td>
<td><p>Enables you to set up and administrate your Web sites.</p></td>
</tr>
<tr class="odd">
<td><p><a href="how-to-create-wizards.md">Wizard wizard</a></p></td>
<td><p><strong>Tools</strong> &gt; <strong>Wizards</strong> menu</p></td>
<td><p>Helps you to create your own wizard.</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

