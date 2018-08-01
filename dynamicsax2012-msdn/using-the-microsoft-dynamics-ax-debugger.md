---
title: Using the Microsoft Dynamics AX Debugger
TOCTitle: Using the Microsoft Dynamics AX Debugger
ms:assetid: 05df0da1-843d-4773-8228-c5222072ba4e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa569639(v=AX.60)
ms:contentKeyID: 35239261
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using the Microsoft Dynamics AX Debugger [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When a debugging session starts, the Microsoft Dynamics AX debugger is automatically started by either the Microsoft Dynamics AX client or the Microsoft Dynamics AX Business Connector, if the debugger has been enabled. For more information about how to enable the debugger, see [How to: Enable the Debugger](how-to-enable-the-debugger.md).


> [!TIP]
> <P>In order to access the debugger, you must be a member of the Microsoft Dynamics AX Debugging Users group in Windows. If you are not a member of this group, you will see an error message when the debugger starts. Contact your system administrator to add you to this group. After you are added to this group, you must log out and log in to Windows again.</P>



## Breakpoints

When you want to debug X++ code, you must first set one or more breakpoints in the source code by using the code editor in the client. For information about how to set breakpoints, see [Using Breakpoints](using-breakpoints.md). When the code is run and the line where a breakpoint is set is executed, execution is suspended and the debugger is automatically started. The debugger shows the location in the source code where code execution was stopped.

You can insert, remove, enable, or disable breakpoints in both the code window and the [Breakpoints Window](breakpoints-window.md). Breakpoints are preserved between debugging sessions.

## Stepping Through Code

When the code execution has been stopped at a breakpoint, you can continue, end, or single-step through the source code.

Single-stepping commands are as follows:

  - **Step Into** – The execution steps into the current line if it contains a function or a method call.

  - **Step Over** – The execution steps to the next line of code in the current function or method.

  - **Step Out** – The execution steps out of the current function or method.

## Run to Cursor

**Run to Cursor** executes code until it reaches the location of the cursor in the code window. Conceptually, it is similar to a temporary breakpoint set at the position of the cursor.

## Show Next Statement

**Show Next Statement** displays the location of the current execution point. The feature is helpful when you have been browsing in other source code windows in the debugger, and the location of the current execution point is not obvious.

## Set Next Statement

**Set Next Statement** lets the user choose which line of code is run next. This is denoted by the yellow arrow in the margin of the source window. Choosing which line of code runs next can be done only inside the uppermost method on the call stack.

There are three ways to use this functionality:

  - Position the cursor on the line that you want to set as the current statement, and on the **Debug** menu, click **Set Next Statement**.
    
    \- or -

  - Right-click the line that you want to be the current statement, and from the shortcut menu, click **Set Next Statement**.
    
    \- or -

  - Drag the yellow arrow in the left margin of the code window to the line that you want to set as the current statement. A blinking red arrow indicates the line that is the current target of the **Set Next Statement** action.

You can use **Set Next Statement** only on lines with executable X++ statements on them—blank lines, lines with only braces or semicolons, and variable declarations are not valid targets.

## Changing the value of a variable

You can change the value of a variable during the debugging process. This enables you to test new values without having to recompile the class.

To change the value of a variable:

1.  In the **Variables** window or **Watch** window, double-click the value of the variable you want to change.

2.  Enter the new value.

## Copying Contents to the Clipboard

Shortcut menu items for copying the contents of a debugger window to the Clipboard have been added. You can choose **Copy Selected Line(s)** or **Copy All Lines**. The **Call Stack**, **Variables**, and **Watch** windows have this capability.

When a row is copied, the text is put on the Clipboard in the following formats:

  - **Variable** window format and **Watch** window format:
    
    \<NAME:\>\<new line\>\<tab\>\<Name text\>\<new line\>
    
    \<VALUE:\>\<new line\>\<tab\>\<Value text\>\<new line\>
    
    \<TYPE:\>\<new line\>\<tab\>\<Type text\>\<new line\>

If you copy selected lines from the **Locals** window to the Clipboard, the content resembles the following:

    NAME:
        args
    VALUE:
        null
    TYPE:
        Args
    NAME:
        i
    VALUE:
        45
    TYPE:
        int
    NAME:
        returnValue
    VALUE:
        The result is 45.
    TYPE:
        str
    NAME:
        testString
    VALUE:
        This is a string
    TYPE:
        str

If the **Name** text is longer than 50 characters, it is truncated. If the **Value** text is longer than 2,048 characters, it is also truncated.

  - **Call Stack** window format:
    
    \<\[S\] or \[C\]\>\<4 spaces\>\<Path text padded to 100 characters with spaces\>\<line number\>\<new line\>

The \[S\] and \[C\] represent whether the code is running on the server (the AOS) or on the client.

## See also

[Using Breakpoints](using-breakpoints.md)

[Debugger Windows](debugger-windows.md)

[Debugger Shortcut Keys](debugger-shortcut-keys.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

