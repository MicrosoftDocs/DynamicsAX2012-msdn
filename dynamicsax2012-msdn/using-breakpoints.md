---
title: Using Breakpoints
TOCTitle: Using Breakpoints
ms:assetid: 481ce532-c0cc-47d5-90a6-c6df9bf05a7d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa569664(v=AX.60)
ms:contentKeyID: 35239286
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using Breakpoints [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In the Microsoft Dynamics AX debugger, breakpoints allow you to suspend code execution where and when you need to. This allows you to run code until execution reaches a statement on which a breakpoint it set rather than stepping through the code, line-by-line. A breakpoint does not terminate code execution, but instead suspends it. When the debugger has reached a breakpoint and the code execution is suspended, the debugger is said to be in break mode.

Breakpoints can be set from both the debugger and the code editor in the client. The effect of a breakpoint is similar to a Stop statement in Microsoft Visual Basic or a call to System.Diagnostics.Debugger.Break in C\#.


> [!NOTE]
> <P>You can also set a breakpoint in your X++ code by using the breakpoint statement.</P>



Breakpoints are persisted on a per-user basis. For example, if a breakpoint is inserted by user 1, user 2 cannot see the breakpoints that user 1 has set. This is true regardless of where the code with the breakpoint is running.

Breakpoint changes are reflected in both the code editor and the debugger. If a breakpoint is inserted in the code editor, the breakpoint will appear in the debugger. If a breakpoint is inserted in the debugger, the breakpoint will appear in the code editor.

## Setting Breakpoints

You can set breakpoints in the X++ code editor and in the debugger.

To set a breakpoint in the X++ code editor:

1.  Position the cursor where you want to insert the breakpoint.

2.  In the **Debug** menu, select **Toggle breakpoint**, or press F9.

To set a breakpoint in the debugger:

1.  Position the cursor where you want to insert the breakpoint.

2.  Click the **Insert/Remove Breakpoint** icon on the debugger toolbar, or press F9.

When a breakpoint is inserted in the code editor, the entire line changes color to indicate that there is a breakpoint in the line. In the debugger, a red dot appears in the margin of the source window to the left of the line.


> [!NOTE]
> <P>Setting breakpoints can be performed only on lines with executable X++ statements on them. Blank lines, lines with only braces or semicolons, and variable declarations without assignments are not valid lines for setting breakpoints.</P>



## Working with Existing Breakpoints

  - To see a list of breakpoints from the Microsoft Dynamics AX X++ code editor, click **Breakpoints** on the **Edit** menu, or press SHIFT+F9. In the debugger, the breakpoints are listed in the **Breakpoints** window.

  - To enable or disable a breakpoint, press CTRL+F9, or click the **Enable/Disable Breakpoint** icon on the debugger toolbar. Disabling a breakpoint is an alternative to removing one. Disabling makes the breakpoint inactive, but it remains in the list of existing breakpoints. There is no need to remove a breakpoint if it might be needed later.

  - To insert or remove a breakpoint, you can press F9, click the **Insert/Remove Breakpoint** icon on the debugger toolbar, or right-click in the left margin in the **Output** window and then click **Insert Breakpoint** or **Remove Breakpoint**. Breakpoints can also be removed from the **Breakpoints** window by right-clicking and then clicking **Remove Breakpoint**.

## See also

[Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md)

[Breakpoints Window](breakpoints-window.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

