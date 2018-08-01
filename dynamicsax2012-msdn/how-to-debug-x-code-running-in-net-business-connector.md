---
title: 'How to: Debug X++ Code Running in .NET Business Connector'
TOCTitle: 'How to: Debug X++ Code Running in .NET Business Connector'
ms:assetid: 631a0284-9b03-407f-9c4c-a31d7b048981
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb190066(v=AX.60)
ms:contentKeyID: 35244608
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Debug X++ Code Running in .NET Business Connector [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX development environment enables you to create a .NET-connected application and integrate with Microsoft Dynamics AX. By using .NET Business Connector, you can call X++ methods and access data from a .NET-connected application.

Microsoft Dynamics AX requires that you set breakpoints through the client and the debugger. You need to enable setting break points in the client configuration, and then enable debugging in the .NET Business Connector configuration. For more information about debugger, see [Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md).

There are two modes to debug .NET Business Connector code; interactive and non-interactive. An example of using the interactive mode is integrating Microsoft Excel with Microsoft Dynamics AX. For more information, see [How to: Enable the Debugger](how-to-enable-the-debugger.md). An example of using the non-interactive mode is integrating with Enterprise Portal. The following steps provide information to debug X++ code from the .NET-connected application using the non-interactive mode.

## Prerequisites

To complete following procedures, you will need:

  - Microsoft Dynamics AX installed with a developer license file

  - Client, server and .NET Business Connector on the same computer

  - The Microsoft Dynamics AX developer is in the Windows admin group

## Procedures

### ![Bb190066.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb190066.collapse_all(en-us,AX.60).gif")Setting the Configuration Settings to Enable Debug

In this section, you will set the configuration settings to enable your X++ code to be debugged from a .NET-connected application. The settings are in the Microsoft Dynamics AX Configuration and Server Configuration windows.

### To set the configuration settings

1.  From the **Start** menu, point to **Administrative Tools** and then click **Microsoft Dynamics AX Configuration**.

2.  Click the **Manage** button and then click **Create configuration**.

3.  Give the **Configuration** a name like DebugClientOption and click **OK**.

4.  Click the **Developer** tab, select **Enable user breakpoints to debug code in the Business Connector** or select **Enable global breakpoints to debug code running in the Business Connector or client**.
    

    > [!NOTE]
    > <P>Breakpoints are user specific. If you set a breakpoint, only the intended session will break for that breakpoint even if other users execute that code while the breakpoint exists. A global breakpoint will break on any breakpoint for any session running on the machine.</P>



5.  Click the **Configuration Target:** dropdown and select **Business Connector (non-interactive use only)**.

6.  Click the **Manage** button and then click **Create configuration…**

7.  Give the **Configuration** a name like DebugNonIntOption and click **OK**.

8.  On the **Developer** tab, select **Enable user breakpoints to debug code running in the Business Connector** or select **Enable global breakpoints to debug code running in the Business Connector or client**.

9.  Click **OK** to apply changes and close window.

The following steps are only required if you want to debug X++ code that runs on the AOS server, if your code is client only code, for example Business Connector or desktop client, then the following steps are not required. This can be critical in production scenarios because applying the configuration changes require re-starting the server.

### To set the configuration settings for code that runs on the AOS server

1.  From the **Start** menu, point to **Administrative Tools** and then click **Microsoft Dynamics AX Server Configuration**.

2.  Click the **Manage** button and then click **Create configuration**.

3.  Give the **Configuration** a name like DebugServerOption and click **OK**.

4.  On the **Application Object Server** tab, select **Enable breakpoints to debug X++ code running on this server**.

5.  Click **OK** to apply changes and close window. You will be prompted to restart the service.

### ![Bb190066.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb190066.collapse_all(en-us,AX.60).gif")Enabling Debug in Microsoft Dynamics AX

The next step is to enable debug in the Microsoft Dynamics AX application.

### To enable debug in Microsoft Dynamics AX

1.  From the **System administration** navigation pane, click **Common** \> **Users**.

2.  Click the user that you want to debug, on the Action Pane, click **Options**.

3.  In the **Options** window, click the **Development** link. In the **Debug** section, for the **Debug mode** field, click **When Breakpoint**.

4.  Click **Apply** and close the **Option** and **User** windows.

### ![Bb190066.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb190066.collapse_all(en-us,AX.60).gif")Setting Breakpoints in Microsoft Dynamics AX

The following section describes how to set breakpoints in your X++ code.

### To set breakpoints in Microsoft Dynamics AX

1.  In the Application Object Tree (AOT), locate the method that you want to debug, right-click the method and click **Edit**.

2.  Use F9 to include a breakpoint in your X++ code. For more information about breakpoints, see [Using Breakpoints](using-breakpoints.md).

### ![Bb190066.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb190066.collapse_all(en-us,AX.60).gif")Invoking the Breakpoints in X++

Now that you have the configuration settings applied and Microsoft Dynamics AX enabled to break when you debug, the final step is to run the .NET-connected application. In this section you will run the application that will cause the breakpoint to occur.

### To run the application

1.  Start the .NET-connected application that uses the Microsoft.Dynamics.BusinessConnectorNet assembly. This will load the breakpoints for the current user.

2.  Click **Tools** \> **Debugger**.

3.  Run the application that will cause the breakpoints to occur. When a breakpoint is encountered, Microsoft Dynamics AX will connect to an existing debugger process and displays the output in the Microsoft Dynamics AX Debugger window. For more information about how to use the Debugger, see [Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md).

### ![Bb190066.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb190066.collapse_all(en-us,AX.60).gif")Disabling the Debug Settings

When you are finished debugging the X++ code you must disable the debug settings. The following section describes the steps to remove the breakpoints and reset the configuration settings.

### To disable the debug settings

1.  In the AOT, locate the method that you set breakpoints in, right-click the method and click **Edit**.

2.  Use F9 to remove a breakpoint, or use Ctrl+F9 to disable the breakpoint.

3.  Click **Tools** \> **Options**.

4.  In the **Options** window, click the **Development** link. In the **Debug** section, for the **Debug mode** field, click **No**.

5.  Click **Apply** and close the **Option** and **User** windows.

6.  Set the configuration settings back to the previous configurations. From the **Start** menu, point to **Administrative Tools** and then click **Microsoft Dynamics AX Configuration**.

7.  Click the **Configuration** drop down menu and click the previous or Original configuration.

8.  In the **Application Object Server Instance** dropdown, select **Local client**.

9.  Click the **Configuration** drop down menu and click the previous or Original configuration.

10. Click **OK** to apply changes and close window.

11. From the **Start** menu, point to **Administrative Tools** and then click **Microsoft Dynamics AX Server Configuration**.

12. Click the **Configuration** drop down menu and click the previous or Original configuration.

13. Click **OK** to apply changes and close window.

## See also

[Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md)

[.NET Business Connector Overview](net-business-connector-overview.md)

[Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

