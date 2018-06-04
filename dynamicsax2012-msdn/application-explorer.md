---
title: Application Explorer
TOCTitle: Application Explorer
ms:assetid: c92a4400-a087-4d7b-b2b0-4b82cff0c682
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc637855(v=AX.60)
ms:contentKeyID: 28119585
ms.date: 11/21/2012
mtps_version: v=AX.60
f1_keywords:
- Microsoft.Dynamics.Framework.Design.UI.ApplicationExplorer
---

# Application Explorer 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Application Explorer is a tool in Visual Studio that provides a view into the model store in Microsoft Dynamics AX. You can use Application Explorer to view model elements in the model store and perform tasks. Application Explorer is only available in Visual Studio after you have installed the Visual Studio Tools as part of your Microsoft Dynamics AX installation process. For more information, see [Install Visual Studio Tools](https://msdn.microsoft.com/en-us/library/dd309576\(v=ax.60\)). For more information about Microsoft Dynamics AX development with Visual Studio, see the following:

  - [Visual Studio Integration](visual-studio-integration.md)

  - [Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md)

To open Application Explorer, do the following:

1.  In Visual Studio, click **View** \> **Application Explorer**.


> [!NOTE]
> <P>The Application Explorer window opens in the last saved position. To reposition the window, right-click the title bar and select a docking option.</P>



The following illustration shows the Application Explorer window in Visual Studio. The root node or top-level node shows you information about the model store. The format of the data in the root node is \<Configuration Name\> (Layer Name) \[Model Name\]\>. You can configure Application Explorer to reference a specific Microsoft Dynamics AX client configuration. For more information, see [How to: Open Visual Studio with a Specific Configuration](how-to-open-visual-studio-with-a-specific-configuration.md).

![Application Explorer window](images/Cc637855.ApplicationExplorer(AX.60).gif "Application Explorer window")

## Application Explorer Features

The following table lists some of the features of Application Explorer and describes how to use these features.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Multi-select operations</p></td>
<td><p>You can select multiple elements in the Application Explorer, adjacent or nonadjacent, by using the SHIFT or CTRL keys. For more information, see <a href="keyboard-shortcuts-in-application-explorer.md">Keyboard Shortcuts in Application Explorer</a>.</p></td>
</tr>
<tr class="even">
<td><p>Edit</p></td>
<td><p>You can right-click some elements in Application Explorer and select <strong>Edit</strong>. Depending on which item is selected, the appropriate editor will run. For example, if you right-click a project in the C Sharp Projects folder, the system will open Visual Studio and the currently selected project.</p></td>
</tr>
<tr class="odd">
<td><p>Drag-and-drop operations from Application Explorer</p></td>
<td><p>Application Explorer supports drag-and-drop operations. This means you can use the mouse to drag elements from the Application Explorer window to a project or solution in Visual Studio. For example, you can add an X++ class to a project by dragging it from the <strong>Classes</strong> node in the Application Explorer to an open project in Solution Explorer.</p></td>
</tr>
<tr class="even">
<td><p>Find as you type</p></td>
<td><p>To navigate in Application Explorer, you can use the &quot;find as you type&quot; feature by typing a letter on the keyboard. For example, when focused on the <strong>SSRS Reports</strong> &gt; <strong>Reports</strong> expanded node, typing the letter d will move the focus to the next report that starts with the letter d.</p></td>
</tr>
<tr class="odd">
<td><p>Shortcut menus</p></td>
<td><p>When you right-click an element, a shortcut menu is displayed with options specific to the selected item. If you use multi-select, only options applicable to all of the selected elements are available from the shortcut menu.</p></td>
</tr>
<tr class="even">
<td><p>View code</p></td>
<td><p>When you right-click a method, a job, or a macro, you can select <strong>View code</strong>. The code for that element appears in the Visual Studio code editor.</p></td>
</tr>
<tr class="odd">
<td><p>Window docking</p></td>
<td><p>You can dock Application Explorer by using the standard Visual Studio docking window commands. In addition, you can float the Application Explorer window anywhere inside, or even outside the Visual Studio user interface. To change docking options, right-click the Application Explorer window title bar, and then click a new docking option.</p></td>
</tr>
</tbody>
</table>



> [!TIP]
> <P>If you make changes in the Application Object Tree (AOT) in MorphX when you have Visual Studio open, those changes may not be immediately reflected in Application Explorer; for example, if you add a new class in the AOT. To refresh Application Explorer, right-click the <STRONG>Classes</STRONG> node and then click <STRONG>Refresh</STRONG>.</P>



## See also

[Keyboard Shortcuts in Application Explorer](keyboard-shortcuts-in-application-explorer.md)

[How to: Open Visual Studio with a Specific Configuration](how-to-open-visual-studio-with-a-specific-configuration.md)

[Visual Studio Integration](visual-studio-integration.md)

