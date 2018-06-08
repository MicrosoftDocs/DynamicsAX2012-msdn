---
title: 'Walkthrough: Debugging a Managed Code Event Handler'
TOCTitle: 'Walkthrough: Debugging a Managed Code Event Handler'
ms:assetid: 2c47b232-939d-4d86-a40e-d6fe5a6c6348
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889149(v=AX.60)
ms:contentKeyID: 35272042
ms.date: 11/21/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Walkthrough: Debugging a Managed Code Event Handler 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can write an event handler in managed code that is called before or after an X++ class method or when a delegate fires. This topic shows you how to debug the managed code post-event handler you created by following the steps in [Walkthrough: Creating an Event Handler in Visual Studio](walkthrough-creating-an-event-handler-in-visual-studio.md).

## Prerequisites

To complete this walkthrough you will need:

  - Microsoft Dynamics AX with Visual Studio Tools installed

  - Visual Studio 2010

  - Code artifacts from the completed walkthrough topic [Walkthrough: Creating an Event Handler in Visual Studio](walkthrough-creating-an-event-handler-in-visual-studio.md)

## Debugging the Event Handler

The following procedures explain how to debug a managed code post-event handler that is called from X++. In this scenario, the event handler was created in C\# and is called after the X++ class method MyClass.myMethod fires. You can debug the event handler in one of two ways:

  - From X++ - You debug by starting in X++ and then switching into the Visual Studio debugger. First, you manually attach to the Microsoft Dynamics AX process from Visual Studio and then switch to X++ to begin debugging. Because the event handler is managed code, you set the breakpoints and debug in Visual Studio; however, context automatically switches from the Microsoft Dynamics AX Debugger to the Visual Studio Debugger.

  - From Visual Studio - You debug the complete scenario from Visual Studio. First, you set the **Debug Target** and **Startup Element** properties on the project in Visual Studio. Then when you start the project, Visual Studio will attach to the correct process, run the code you specify in the **Startup Element** property, and then stop at the breakpoints in the managed code.


> [!WARNING]
> <P>To step through these procedures, you must have the code artifacts deployed from topic <A href="walkthrough-creating-an-event-handler-in-visual-studio.md">Walkthrough: Creating an Event Handler in Visual Studio</A>.</P>



### To debug the event handler from X++

1.  Open Microsoft Dynamics AX and navigate to the **Jobs** node in the AOT.

2.  Start Visual Studio and open the project MyEventHandler.

3.  Open the MyPostEventHandler class and set a breakpoint on the following line of code:
    
    ``` csharp
    Global.info("MyPostEventHandler.PostMyMethod called");
    ```

4.  Select **Debug** \> **Attach to Process**.

5.  From the **Available Processes** field, select the process Ax32.exe and then click **Attach**. This is the Microsoft Dynamics AX client process. You must attach to the client process because the code that is being tested runs on the client.

6.  Switch to the Microsoft Dynamics AX client. Right-click the callMyClass job and select **Open**. The X++ code runs and then context switches to Visual Studio with the cursor positioned on the breakpoint that you previously set.

### To debug the event handler from Visual Studio

1.  Start Visual Studio and open the project MyEventHandler.

2.  Open the MyPostEventHandler class and set a breakpoint on the following line of code:
    
    ``` csharp
    Global.info("MyPostEventHandler.PostMyMethod called");
    ```

3.  In Solution Explorer, click the project MyEventHandler. In the Properties Pane, set the **Debug Target** property to **Client** and set the **Startup Element** property to **Jobs\\callMyClass**.

4.  Press F5 to start debugging. Visual Studio automatically attaches to the client process and calls the callMyClass job because you set the values of the **Debug Target** and **Startup Element** properties. After the debugger calls the callMyClass job, the method will fire, the post-event handler will be called, and code execution will stop at the breakpoint that you set in step 2.

## Next Steps

This scenario shows you how to debug a post-event handler. You follow the same procedure to debug a pre-event handler. When debugging a pre-event handler, you may want to set a breakpoint in the X++ class method. This enables you to continue to debug after the pre-event handler completes and control is transferred to the X++ class method.

## See also

[Walkthrough: Creating an Event Handler in Visual Studio](walkthrough-creating-an-event-handler-in-visual-studio.md)

