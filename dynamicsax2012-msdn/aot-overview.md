---
title: AOT Overview
TOCTitle: AOT Overview
ms:assetid: 96ab1dac-794e-4029-b04c-8fe9f8ef757b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa843974(v=AX.60)
ms:contentKeyID: 35247671
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# AOT Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, the Application Object Tree (AOT) contains all of the definitions of elements that are used to build Microsoft Dynamics AX, such as classes, tables, forms, and so on. This topic provides an overview of the AOT and defines the top-level nodes.

To create a new element in the AOT, right-click the relevant node, and then click **New**. In addition, drag-and-drop operations are available for many elements.

All elements under the top-level nodes have:

  - A shortcut menu. To open the shortcut menu, right-click an element. For more information, see [Shortcut Menu Commands: AOT](shortcut-menu-commands-aot.md).

  - Properties. To see the properties and property values of an element, right-click the element and then click **Properties**. The **Properties** sheet is displayed. For more information, see [Application Object Properties](application-object-properties.md).

The AOT contains the top-level nodes described in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Node</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Data Dictionary</strong></p></td>
<td><p>Contains the data types and tables that make up the database. Also contains objects to control access to the data. It contains the following subnodes:</p>
<p><strong>Tables</strong>: Tables that contain the Microsoft Dynamics AX data.</p>
<p><strong>Maps</strong>: Enables you to create associations between closely related (but non-identical) table fields and methods.</p>
<p><strong>Views</strong>: Enables you to join data from different tables, and then to select which fields you want to display.</p>
<p><strong>Extended Data Types</strong>: Data types that extend one of the primitive data types or another extended data type.</p>
<p><strong>Base Enums</strong>: Enumerable types that contain a list of literals.</p>
<p><strong>License Codes</strong>: Determines which components of Microsoft Dynamics AX functionality are available to a company.</p>
<p><strong>Configuration Keys</strong>: Allows administrators to enable or disable features in the application for all users.</p>
<p><strong>Security Keys</strong>: Security keys are obsolete in Microsoft Dynamics AX 2012 and only exist to use for reference during a code upgrade. There is a new security framework, which is called role-based security. For more information on the new security framework, see <a href="role-based-security-in-the-aot-for-developers.md">Role-based Security in the AOT for Developers</a>.</p>
<p><strong>Table Collections</strong>: Collections of tables that contain data that is often shared between companies.</p>
<p><strong>Perspectives</strong>: Collections of tables that were used to organize information for report models.</p></td>
</tr>
<tr class="even">
<td><p><strong>Macros</strong></p></td>
<td><p>Contains the source code for the macros used by the standard application. In addition to viewing the existing code, you can add your own macros.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Classes</strong></p></td>
<td><p>Contains the source code for the application (X++) classes.</p>
<p>You can also use system classes (also known as kernel classes). They are listed in the <strong>System Documentation\Classes</strong> node.</p></td>
</tr>
<tr class="even">
<td><p><strong>Forms</strong></p></td>
<td><p>Dialog boxes in the user interface that are used to access the database.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Parts</strong></p></td>
<td><p>Contains controls you can use to retrieve and show a collection of data. For more information, see <a href="parts.md">Parts</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data Sets</strong></p></td>
<td><p>Provides a generic data access layer that allows for external presentation layers to bind to Microsoft Dynamics AX tables and data types. For more information, see <a href="data-sets-for-enterprise-portal.md">Data Sets for Enterprise Portal</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SSRS Reports</strong></p></td>
<td><p>Contains SQL Server Reporting Services reports that are included with Microsoft Dynamics AX.</p></td>
</tr>
<tr class="even">
<td><p><strong>Reports</strong></p></td>
<td><p>Enables users to print or display summary information from the database.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Visual Studio Projects</strong></p></td>
<td><p>Contains projects created in Visual Studio and added to Microsoft Dynamics AX by using Application Explorer. Project types that can be added to this node include Dynamics AX Model Projects, C Sharp Projects, Visual Basic Projects, Web Application Projects, and Analysis Services Projects. For more information, see <a href="visual-studio-integration.md">Visual Studio Integration</a> and <a href="how-to-add-a-visual-studio-project-to-the-aot.md">How to: Add a Visual Studio Project to the AOT</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Report Libraries</strong></p></td>
<td><p>Used to store Microsoft Dynamics AX 2009 SQL Server Reporting Services report libraries that are being upgraded for the Microsoft Dynamics AX 2012 AOT environment.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Queries</strong></p></td>
<td><p>Used as the source of records for forms and reports.</p></td>
</tr>
<tr class="even">
<td><p><strong>Jobs</strong></p></td>
<td><p>Typically holds small X++ programs that are used to test new code.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Menus</strong></p></td>
<td><p>Contains the menus you want the end user to see.</p></td>
</tr>
<tr class="even">
<td><p><strong>Menu Items</strong></p></td>
<td><p>Contains a complete list of the items that can be presented in a menu. Menu items act as a higher layer of abstraction for forms, reports, and so on.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Web</strong></p></td>
<td><p>Contains objects related to Web development.</p></td>
</tr>
<tr class="even">
<td><p><strong>Services</strong></p></td>
<td><p>Contains services that are exposed by Microsoft Dynamics AX.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Service Groups</strong></p></td>
<td><p>Contains collections of services that are frequently consumed and managed together. All the services in a service group are published in a single WSDL file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Workflow</strong></p></td>
<td><p>Contains the workflow model elements used to create a workflow configuration. This node contains <strong>Categories</strong>, <strong>Tasks</strong>, <strong>Approvals</strong>, and <strong>Templates</strong>. For more information, see <a href="implementing-workflow-for-microsoft-dynamics-ax.md">Implementing Workflow for Microsoft Dynamics AX</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Security</strong></p></td>
<td><p>Contains the objects you use to implement application security, such as roles and permissions.</p></td>
</tr>
<tr class="even">
<td><p><strong>Resources</strong></p></td>
<td><p>Contains references to image and animation files.</p></td>
</tr>
<tr class="odd">
<td><p>Label Files</p></td>
<td><p>Contains label files that store labels for all user interface elements. For more information, see <a href="label-editor.md">Label Editor</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>References</strong></p></td>
<td><p>Contains references to Microsoft .NET assemblies and to external Web services. Both types of references can be used in X++ statements.</p></td>
</tr>
<tr class="odd">
<td><p>Help Documentation Sets</p></td>
<td><p>Specifies the documentation sets on the Help Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>System Documentation</strong></p></td>
<td><p>Contains items that represent system (kernel) classes, functions, tables, and so on.</p></td>
</tr>
</tbody>
</table>


## See also

[Application Object Tree (AOT)](application-object-tree-aot.md)

[Application Object Properties](application-object-properties.md)

[MorphX Development Projects](morphx-development-projects.md)

[MorphX Development Tools](morphx-development-tools.md)

[Shortcut Keys: AOT](shortcut-keys-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

