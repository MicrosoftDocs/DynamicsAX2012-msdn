---
title: 'Walkthrough: Creating an Event Handler in Visual Studio'
TOCTitle: 'Walkthrough: Creating an Event Handler in Visual Studio'
ms:assetid: 4aa960dc-c897-4deb-9d35-f5c29716db07
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889181(v=AX.60)
ms:contentKeyID: 35272070
ms.date: 11/21/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Walkthrough: Creating an Event Handler in Visual Studio 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic shows you how to create a managed code event handler that is triggered by the execution of an X++ method. An event handler can run before an X++ method starts, after an X++ method completes, or when a delegate fires. In this scenario, the event is triggered by the completion of an X++ method. For more information about events and event handlers, see [Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md).

This walkthrough illustrates the following tasks:

  - Creating the X++ class that has a method event to which the event handler subscribes

  - Creating the assembly that contains the managed code event handler in Visual Studio

  - Adding code to the managed code event handler

  - Creating an X++ job to test the event handler

## Prerequisites

To complete this walkthrough you need:

  - Microsoft Dynamics AX with Visual Studio Tools installed

  - Visual Studio 2010

## Creating the X++ Class

The following procedure explains how to create the X++ class and method. The event handler that you will create in the following procedure subscribes to this event and will run after the X++ class method completes. In this topic, you create this class to demonstrate how to create an event handler and associate it with an X++ class method. But, typically, you will already have an X++ class method. Therefore, you can go to the procedure Creating the Event Handler in Visual Studio.

### To create the X++ class

1.  In Microsoft Dynamics AX, in the Application Object Tree (AOT), right-click the **Classes** node and then click **New Class**. Set the **Name** property to MyClass.

2.  To add a new method, right-click the class and then click **New** \> **Method**. Replace the method code with the following code:
    
        public void myMethod()
        {
            info("MyClass.myMethod called.");
        }
    
    This writes a string to the Infolog window so that you can verify that the method was called.

3.  Press F7 to compile the class.

4.  Close the Microsoft Dynamics AX client.

## Creating the Event Handler in Visual Studio

The following procedure explains how to create the managed code post-event handler in Visual Studio. In this procedure, you select the X++ class that you created and then create the event handler in that context. This process creates the event handler and the subscription between the class method and the event handler.

### To create the event handler

1.  In Visual Studio, create a new C\# class library project by clicking **File** \> **New** \> **Project**.

2.  In the **Installed Templates** tree, select **C\#** and then select the **Class Library** template. Change the name to MyEventHandler and then click **OK**.

3.  In Solution Explorer, rename Class1 to MyPostEventHandler. When prompted to update any references to Class1, click **OK**.

4.  Save the project and then compile it by clicking **Build** \> **Build MyEventHandler**.

5.  In Solution Explorer, add the project to the AOT. To do this, right-click the MyEventHandler project and then click **Add MyEventHandler to AOT**. After you add the project to the AOT, a reference to the Microsoft.Dynamics.AX.ManagedInterop assembly is added to the **References** folder in Solution Explorer.

6.  In Visual Studio, click **View** \> **Application Explorer** to open the Application Explorer. Navigate to MyClass by expanding the **Classes** node and locating MyClass.

7.  Be sure that the Visual Studio code editor is open and your cursor is positioned inside the curly braces in the public class MyPostEventHandler definition.

8.  In Application Explorer, right-click the method MyClass.myMethod and select **Add post-event handler**. The system will add the event handler code to the MyPostEventHandler class and it will resemble the following:
    
    ``` csharp
    namespace MyEventHandler
    {
        public class MyPostEventHandler
        {
    
            // Do not change the name of the event handler method. If you rename the method, the event handler will not work.
            [Microsoft.Dynamics.AX.ManagedInterop.XppClassDefiningEventAttribute(@"\Classes\MyClass")]
            static public void PostMyMethod(XppPrePostArgs args)
            {
    
            }
        }
    }
    ```
    
    In addition to creating the event handler class method, the system performs these tasks:
    
    1.  Adds the [XppPrePostArgs Class](https://msdn.microsoft.com/en-us/library/gg835235\(v=ax.60\)) to the project. You can see this class in Solution Explorer. For more information, see [Walkthrough: Adding an X++ Object to a Visual Studio Project](walkthrough-adding-an-x-object-to-a-visual-studio-project.md) and [.NET Interop from X++](net-interop-from-x.md).
    
    2.  Adds an event handler subscription with a default name of EventHandlerSubscription1 to the MyClass.myMethod method and populates all the necessary properties. This creates the association between the MyClass.myMethod method and the MyEvenHandler.PostMyMethod event handler. If you navigate to the MyClass.myMethod.EventHandlerSubscription1 node and then right-click and select Properties, you can see that the subscription points to the managed code MyEventHandler.MyPostEventHandler class method.
    
    3.  Sets the deployment properties for the MyEventHandler managed code project. The properties Deploy to Client and Deploy to Server are automatically set to Yes. For more information, see [Deploying Managed Code](deploying-managed-code.md).

## Adding the Code to the Event Handler

The following procedure explains how to add code to the event handler that you have just created in Visual Studio. This code writes a line to the Microsoft Dynamics AX InfoLog.

### To add the code

1.  In Application Explorer, expand the **Classes** node and locate the Global class. Add it to the project by dragging it onto the MyEventHandler project.

2.  Add the code to write to the event log in the **PostMyMethod** method. Your code should resemble the following.
    
    ``` csharp
    namespace MyEventHandler
    {
        public class MyPostEventHandler
        {
    
            // Do not change the name of the event handler method. If you rename the method, the event handler will not work.
            [Microsoft.Dynamics.AX.ManagedInterop.XppClassDefiningEventAttribute(@"\Classes\MyClass")]
            static public void PostMyMethod(XppPrePostArgs args)
            {
                // Write an entry to the X++ InfoLog.
                Global.info("MyPostEventHandler.PostMyMethod called");
            }
        }
    }
    ```

3.  In Solution Explorer, right-click the **MyEventHandler** project and then click **Build**.

4.  In Solution Explorer, right-click the **MyEventHandler** project and then click **Deploy**. By default, the assembly is deployed to both the client and the server. This is because the project properties Deploy to Client and Deploy to Server were set to Yes when you added the event handler in the previous procedure. When the MyClass.myMethod method is called and completes, the PostMyMethod managed code event handler method is then called and sends a message to the Microsoft Dynamics AX Infolog.
    

    > [!TIP]
    > <P>If you receive an error that the assembly cannot be deployed to the server, you may need to enable hot swapping of assemblies on the server. To do this, modify the server configuration and select the <STRONG>Allow hot swapping of assemblies when the server is running field</STRONG>. For more information, see <A href="https://msdn.microsoft.com/en-us/library/aa569618(v=ax.60)">Manage an AOS configuration</A> and <A href="https://msdn.microsoft.com/en-us/library/aa569635(v=ax.60)">Microsoft Dynamics AX 2012 Server Configuration (form)</A>.</P>



## Creating an X++ Job to Test the Event Handler

The following procedure explains how to create a job to test the event handler.

### To create the job

1.  Open the Microsoft Dynamics AX client. If you already have the client open, you must close it and open it again so that the assembly that contains the event handler is re-deployed.
    

    > [!NOTE]
    > <P>The managed code assembly is not actually deployed when you open the client. It is deployed when you make any call from the client to managed code. For more information, see <A href="deploying-managed-code.md">Deploying Managed Code</A>.</P>



2.  In the AOT, right-click the **Jobs** node and then click **New Job.**

3.  Replace the code with the following code that calls the MyClass.myMethod method.
    
        static void callMyClass(Args _args)
        {
        
            MyClass myClass;
            myClass = new MyClass();
        
            myClass.myMethod();
        
        }

4.  Press F7 to compile the class and F5 to run it. An Infolog appears that displays the string from the MyClass.myMethod method and the string from the managed event handler. This is how you can verify that both the method and the event handler were called.

## Next Steps

If you encounter any problems when you are creating managed code event handlers, you can debug them by using Visual Studio. For more information, see [Walkthrough: Debugging a Managed Code Event Handler](walkthrough-debugging-a-managed-code-event-handler.md).

Use the [XppPrePostArgs Class](https://msdn.microsoft.com/en-us/library/gg835235\(v=ax.60\)) class to access and modify parameters that are passed to the event method. If you have an event handler that fires before the method runs (a pre-event handler), you can use this class to access and modify parameters before they are passed to the method. If you have an event handler that fires after the method runs (a post-event handler), you can use this class to access and modify parameters after they are passed to the method. For more information, see [How to: Modify Parameter Values in a Pre-Method Event Handler](how-to-modify-parameter-values-in-a-pre-method-event-handler.md) and [How to: Modify the Return Value in an Post-Method Event Handler](how-to-modify-the-return-value-in-an-post-method-event-handler.md).

## See also

[Integration with X++ Objects from Visual Studio](integration-with-x-objects-from-visual-studio.md)

[Walkthrough: Debugging a Managed Code Event Handler](walkthrough-debugging-a-managed-code-event-handler.md)

[Walkthrough: Adding an X++ Object to a Visual Studio Project](walkthrough-adding-an-x-object-to-a-visual-studio-project.md)

[Deploying Managed Code](deploying-managed-code.md)

[.NET Interop from X++](net-interop-from-x.md)

[How to: Modify Parameter Values in a Pre-Method Event Handler](how-to-modify-parameter-values-in-a-pre-method-event-handler.md)

[How to: Modify the Return Value in an Post-Method Event Handler](how-to-modify-the-return-value-in-an-post-method-event-handler.md)

[Naming Conventions: Delegates and Event Handlers](naming-conventions-delegates-and-event-handlers.md)

