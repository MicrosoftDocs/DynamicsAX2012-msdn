---
title: Call Stack Window
TOCTitle: Call Stack Window
ms:assetid: 834c7482-aa7c-45b7-8e7f-0a4288b04a74
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa569667(v=AX.60)
ms:contentKeyID: 35239301
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Call Stack Window 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The **Call Stack** window in the Microsoft Dynamics AX debugger displays the stack method calls. This lets you see which method called the one that is currently being shown. The **Call Stack** window displays only X++ code frames. No kernel code is shown.

Selecting a method on the call stack changes the call stack level. The source code for the selected method is displayed in the code window. Changing the call stack level also updates the **Variables** and **Watch** windows so that they display the variables that are within the scope of the selected call stack level.

## Call Stack Windows Header

The **Call Stack** windows header consists of the following three columns:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Column</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Location</strong></p></td>
<td><p>Displays the location that the current frame is running on—client or server—as denoted by two separate icons</p></td>
</tr>
<tr class="even">
<td><p><strong>Path</strong></p></td>
<td><p>Displays the Application Object Tree (AOT) path to the methods that are on the call stack.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Line</strong></p></td>
<td><p>Displays the line in each method that called into the method above it.</p></td>
</tr>
</tbody>
</table>


## Frame List

The frame list displays an ordered list of all the methods that were called to reach the current execution point. The top frame is always the current method that you are debugging. When this frame is active, a yellow arrow appears in the column next to the **Path**. When you are stepping through the code, the line number of this method changes to match the number of the current line. The line numbers of all other frames remain constant because the entry point from those methods does not change.

## Changing the Active Frame

Double-clicking on any frame makes it the active frame in the code editor. If the active frame is the top one on the call stack, a yellow arrow appears next to the location icon. If the frame is the second or a lower one on the call stack, a green arrow appears and points to the line that was called to enter the method—one level above the active frame.

When a new frame is set to active, the **Locals**, **This**, and **Watch** views of the **Variables** window are updated automatically to show the appropriate values for the relevant variables. If the user does any step action or runs to a breakpoint, the call stack automatically sets the top frame as the active frame and re-opens its corresponding code editor view.

Executing **Show Next Statement** also returns the call stack to the top frame and displays the matching code window. **Set Next Statement** can be done only when the top frame is the active frame.


> [!NOTE]
> <P>To change which frame is being viewed without changing the active frame click the <STRONG>Window</STRONG> menu and select a different frame from the bottom of the menu items list.</P>



## See also

[Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md)

[Debugger Windows](debugger-windows.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

