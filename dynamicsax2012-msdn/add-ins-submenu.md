---
title: Add-Ins Submenu
TOCTitle: Add-Ins Submenu
ms:assetid: afcfe28f-76ae-4920-b57b-735b701ff9d4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa855790(v=AX.60)
ms:contentKeyID: 35249733
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Add-Ins Submenu [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, the **Add-Ins** submenu in the Application Object Tree (AOT) shortcut menu is context-sensitive. This means that the available commands in the **Add-Ins** submenu are dependent on the node selected. This topic lists and describes the commands that are available on the **Add-Ins** menu.

On the **Command** menu, find shortcut menu commands that are not context-sensitive. A command that is executed from the **Command** menu retrieves information about all elements in the AOT.

You can customize and add more commands to the **Add-Ins** menu. For more information, see [How to: Add Items to the AOT Add-Ins Menu](how-to-add-items-to-the-aot-add-ins-menu.md).

The following table lists commands that are available on the **Add-Ins** menu.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Command</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>AIF Document Service Wizard</strong></p></td>
<td><p>Calls the <strong>AIF Document Service Wizard</strong> and enables you to create a document service from an existing query. For more information, see <a href="https://msdn.microsoft.com/en-us/library/aa856656(v=ax.60)">Creating New Document Services</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Auto-report</strong></p></td>
<td><p>Opens the <strong>Autoreport</strong> dialog box, which enables you to view information for the fields that are contained in the <strong>AutoReport</strong> field group on the table.</p></td>
</tr>
<tr class="odd">
<td><p>Change current model</p></td>
<td><p>Allows you to change the active model.</p></td>
</tr>
<tr class="even">
<td><p><strong>Check Best Practices</strong></p></td>
<td><p>Checks whether your X++ code complies with Microsoft Dynamics AX best practices.</p>

> [!note]  
> <P>This command does not check all best practices and does not guarantee that your X++ code complies with Microsoft Dynamics AX standards. For more information, see <a href="best-practices-for-microsoft-dynamics-ax-development.md">Best Practices for Microsoft Dynamics AX Development</a>.</P>

</td>
</tr>
<tr class="odd">
<td><p><strong>Compile forward</strong></p></td>
<td><p>Compiles the selected node and all of the child nodes.</p></td>
</tr>
<tr class="even">
<td><p><strong>Copy</strong></p></td>
<td><p>Enables you to copy the complete path or the name of an element.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cross-reference</strong></p></td>
<td><ul>
<li><p><strong>Used by</strong> – Shows where the selected application object is used.</p></li>
<li><p><strong>Using (instant view)</strong> – Shows elements that the selected element uses.</p></li>
<li><p><strong>Names</strong> – Shows a list of application objects and lists their name and type.</p></li>
<li><p><strong>Using</strong> – Shows elements that the selected element uses.</p></li>
<li><p><strong>Update</strong> – Updates cross-reference information about the selected application object.</p></li>
</ul>
<p>For more information, see <a href="cross-reference-tool.md">Cross-reference Tool</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Replace</strong></p></td>
<td><p>Enables you to find and replace text in the X++ code editor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Find and replace</strong></p></td>
<td><p>Enables you to find and replace text in the AOT. For more information, see <a href="https://msdn.microsoft.com/en-us/library/aa585062(v=ax.60)">Find and replace Form</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Open new window</strong></p></td>
<td><p>Opens the selected node and its subnodes in a new window.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Register service</strong></p></td>
<td><p>Opens the <strong>AIF Services</strong> form used to configure services for the Application Integration Framework (AIF).</p></td>
</tr>
<tr class="even">
<td><p><strong>Reverse Engineer</strong></p></td>
<td><p>Opens the <strong>Reverse Engineering</strong> tool that you can use to create UML models in Microsoft Office Visio that are based on the selected application object. For more information, see <a href="reverse-engineering-tool.md">Reverse Engineering Tool</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Syntactic renaming</strong></p></td>
<td><p>Enables you to replace text in a specific element. The command resembles the <strong>Replace</strong> command. In addition to the search and replace text functionalities, you can also specify the type and name of the element.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source Code Titlecase Update</strong></p></td>
<td><p>This command is used to correct title casing for application object names. For example, classes begin with uppercase characters, as in AddressCheck, and methods begin with lowercase characters, as in classDeclaration. For more information, see <a href="https://msdn.microsoft.com/en-us/library/cc582735(v=ax.60)">Source Code Title Case Update Form</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Table browser</strong></p></td>
<td><p>Enables you to view or update data in the selected table.</p></td>
</tr>
<tr class="even">
<td><p><strong>View in Browser</strong></p></td>
<td><p>Enables you to open the selected Web form in a browser.</p></td>
</tr>
</tbody>
</table>


## See also

[Shortcut Menu Commands: AOT](shortcut-menu-commands-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

