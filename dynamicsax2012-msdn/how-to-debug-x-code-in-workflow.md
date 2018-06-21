---
title: 'How to: Debug X++ Code in Workflow'
TOCTitle: 'How to: Debug X++ Code in Workflow'
ms:assetid: 22ad39c4-b908-4799-9f66-8fdcb3bd9bda
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dd638052(v=AX.60)
ms:contentKeyID: 35241576
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Debug X++ Code in Workflow [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The process to debug X++ code in Microsoft Dynamics AX workflow depends on where the code is used in the workflow. The workflow submit code is native X++, and the workflow event handler code is compiled into CIL. The following procedures describe how to enable debugging for the server, how to debug the workflow submit code, and how to debug workflow event handler code.

### To enable debugging for the server

1.  Log into the server that is running the AOS.

2.  Open the Microsoft Dynamics AX Server Configuration utility with administrative privileges (**Start** \> **Administrative Tools** \> **Microsoft Dynamics AX 2012 Server Configuration**). To run the utility with administrative privileges, you must right-click its icon in the **Start** menu and click **Run as administrator**.

3.  Create a new configuration that allows for debugging.
    
    1.  Click **Manage** and then click **Create configuration**. In the Create Configuration window, name the new configuration, such as "DAX Debugging". Click **OK**.
    
    2.  On the **Application Object Server** tab, select **Enable breakpoints to debug code X++ code running on this server**. Click **Apply**. If you receive a message about the AOS, indicate that it should be restarted.

4.  Click **OK** to close the configuration window.

### To debug the submit code for workflow

1.  Open the Development Workspace.

2.  In the AOT, locate the submit code that you want to debug. Typically, this will be the main method of your submit to workflow class.

3.  Set breakpoints in the X++ code by using the **Code Editor**.

4.  In Microsoft Dynamics AX, perform the submit operation for workflow. The Debugger should open and stop at the breakpoint you set.

### To debug workflow event handler or workflow provider code

1.  Start Visual Studio. If User Account Control (UAC) is active, make sure you start Visual Studio with administrative privileges.

2.  In the **View** menu, click **Application Explorer**.

3.  In the **Classes** node of **Application Explorer**, locate the class that contains the workflow event handler or workflow provider that you want to debug.

4.  Double-click the method that you want to debug.

5.  Insert breakpoints into the method.

6.  In the **Debug** menu, click **Attach to Process**.

7.  Click **Select** and mark **Managed (v4.0)**. Click **OK**.

8.  In the **Available Processes** list, select the **Ax32Serv.exe** process. If you do not see the process in the list, make sure that **Show processes from all users** and **Show processes in all sessions** are marked.

9.  Click **Attach**. The symbols for debugging will be loaded, and the breakpoints you set should be enabled.

10. In Microsoft Dynamics AX, perform the workflow action. When the workflow event is processed, execution should stop at the breakpoint you set.

## See also

[Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

