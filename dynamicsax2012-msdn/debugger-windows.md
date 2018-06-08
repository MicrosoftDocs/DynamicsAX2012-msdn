---
title: Debugger Windows
TOCTitle: Debugger Windows
ms:assetid: e9803fd3-c468-4d69-9b0d-88fb416b8ad8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa569670(v=AX.60)
ms:contentKeyID: 35239324
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Debugger Windows 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following table describes the windows that make up the Microsoft Dynamics AX debugger:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Topic</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="variables-window.md">Variables Window</a></p></td>
<td><p>Explains how to use the <strong>Variables</strong> window.</p></td>
</tr>
<tr class="even">
<td><p><a href="watch-window.md">Watch Window</a></p></td>
<td><p>Explains how to use the <strong>Watch</strong> window.</p></td>
</tr>
<tr class="odd">
<td><p><a href="output-window.md">Output Window</a></p></td>
<td><p>Explains how to use the <strong>Output</strong> window.</p></td>
</tr>
<tr class="even">
<td><p><a href="call-stack-window.md">Call Stack Window</a></p></td>
<td><p>Explains how to use the <strong>Call Stack</strong> window.</p></td>
</tr>
<tr class="odd">
<td><p><a href="breakpoints-window.md">Breakpoints Window</a></p></td>
<td><p>Explains how to use the <strong>Breakpoints</strong> window.</p></td>
</tr>
</tbody>
</table>


These windows display detailed information about the current state of the executing code while you are debugging. You can move, undock, resize, or hide these windows. The chosen window layout persists between sessions. It is also possible to print or copy text from any window.


> [!NOTE]
> <P>To restore the debugger UI to the default window layout, press CTRL+ALT+D or click <STRONG>View</STRONG> &gt; <STRONG>Restore Default Layout</STRONG>.</P>



## Sorting in the Debugger Windows

The **Variables** and **Watch** windows each have a **Name** column that can be sorted. The default sorting order for each column is ascending, and the sort uses the complete text of the column to determine the order. The current sort direction is denoted by a small arrow inside the **Name** column. Clicking the column header reverses the current sort direction.

Sorting works separately for each window, including views that are grouped together. For example, in the **Watch** window, you can sort the **Watch 1** view separately from the **Watch 3** view. The current sorting does not persist across debugger instances. When the debugger is in break mode, the sorting state of each window is maintained. If you close the debugger, all sorting reverts to the default sorting the next time that the debugger is opened.

## Window Specifics

Deleting entries from the **Watch** window does not affect the current sort. When a new watch is added, it is added in ascending order regardless of the current sort order. The **Name** column has been re-sorted before the new watch appears in the correct position in the list.

## See also

[Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

