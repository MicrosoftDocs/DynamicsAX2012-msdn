---
title: 'How to: Debug X++ Code on EP Pages'
TOCTitle: 'How to: Debug X++ Code on EP Pages'
ms:assetid: 4cf7b972-0dad-479e-904c-5b60a000c836
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa629010(v=AX.60)
ms:contentKeyID: 35245320
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Debug X++ Code on EP Pages [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

X++ code can be used in various resources that are accessed by a page, such as tables, data sets, and classes. You can debug X++ code for elements that are accessed by pages by using the debugger for Microsoft Dynamics AX. You can debug Enterprise Portal code only on the system that is running Internet Information Services (IIS).

## Setting Up X++ Debugging for Pages

### To set up X++ debugging for pages

1.  Log into the server that is running the AOS.

2.  Open the Microsoft Dynamics AX Server Configuration utility with administrative privileges (**Start** \> **Administrative Tools** \> **Microsoft Dynamics AX 2012 Server Configuration**). To run the utility with administrative privileges, you must right-click its icon in the **Start** menu and choose **Run as administrator**.

3.  Create a new configuration that allows debugging.
    
    1.  Click **Manage** and then click **Create configuration**. In the Create Configuration window, name the new configuration, such as "DAX Debugging". Click **OK**.
    
    2.  On the **Application Object Server** tab, select **Enable breakpoints to debug code X++ code running on this server**. Click **Apply**. If you receive a message about the AOS, indicate that it should be restarted.

4.  Click **OK** to close the configuration window.

5.  Log in to the server that is running IIS and Enterprise Portal. If the system is remote, you can do this using a Remote Desktop Connection. From the **Start** menu, click Run. Type the following in the Open box and then click OK:
    
    mstsc /console
    
    This opens a console session in Remote Desktop.

6.  Enable desktop interaction for the World Wide Web Publish Service.
    
    1.  Open the Services window for the system (**Start** \> **Administrative Tools** \> **Services**).
    
    2.  Right-click the **World Wide Web Publishing Service**, and then click **Properties**.
    
    3.  Click the **Log On** tab.
    
    4.  Select **Allow service to interact with desktop**.
    
    5.  Click **OK** to close the properties window.

7.  Open the web.config file located in \\Inetpub\\wwwroot\\wss\\VirtualDirectories\\\<Port\>\\, where \<Port\> is the port number of the site where Enterprise Portal is installed. Modify the file by doing the following:
    
    1.  Locate the compilation element, and then set the debug attribute to true. This reduces the chance of the Web session having a time-out error when it is stopped at a breakpoint.
    
    2.  Save the changes.

8.  Reset IIS by typing the iisreset command at the command-line window that has been started with administrative privileges.

9.  Open the Microsoft Dynamics AX Configuration utility with administrative privileges (**Start** \> **Administrative Tools** \> **Microsoft Dynamics AX 2012 Configuration**). To run the utility with administrative privileges, you must right-click its icon in the **Start** menu and choose **Run as administrator**.

10. Set the **Configuration Target** drop-down menu to Business Connector (non-interactive use only).

11. Create a new configuration that allows debugging.
    
    1.  Click **Manage** and then click **Create configuration**. In the Create Configuration window, name the new configuration, such as "DAX Debugging". Click **OK**.
    
    2.  On the **Developer** tab, select **Enable user breakpoints to debug code running in the Business Connector**. Click **Apply**.

12. Click **OK** to close the configuration window.

13. Open the Microsoft Dynamics AX client with administrative privileges. To do this, you must right-click on the icon for Microsoft Dynamics AX and then choose **Run as administrator**.

14. Open the Development Workspace.

15. On the **Tools** menu, click **Options** to display the Options window.

16. Click the **Development** link. In the **Debug** area, select **When Breakpoint** from the **Debug mode** list box. This enables debugging mode on the client.

17. Close the Options window.

## Debugging X++ code from a Web Page

### To debug X++ code from a Web page

1.  Log in to the server that is running Internet Information Services (IIS) and Enterprise Portal. If the system is remote, you can do this using a Remote Desktop Connection. From the **Start** menu, click Run. Type the following in the Open box and then click OK:
    
    mstsc /console
    
    This opens a console session in Remote Desktop, and is necessary if you want to debug on a remote system.
    

    > [!IMPORTANT]
    > <P>If you are debugging on a remote system, you must use console mode when connecting. Otherwise, debugging will not work.</P>



2.  Open the Microsoft Dynamics AX client with administrative privileges. To do this, you must right-click on the icon for Microsoft Dynamics AX and then choose **Run as administrator**.

3.  Be sure that you are logged on as a user who is also the following:
    
      - The user who started the session of Microsoft Dynamics AX
    
      - The user who will set breakpoints in X++ code
    
      - A member of the Microsoft Dynamics AX Debugging Users local group on Windows

4.  Open the Development Workspace.

5.  In the AOT, locate the element that you want to debug. Typically, you will debug data sets, tables, or classes.

6.  Set breakpoints in the X++ code by using the **Code Editor**.

7.  Open the debugger by clicking **Tools**, and then clicking **Debugger**. The Debugger must be open before you can run code that contains breakpoints.

8.  Open the Web page that accesses the element that you want to debug. As the page is rendered, the Debugger should stop at the breakpoints that you set.


> [!NOTE]
> <P>If the debugger does not stop at breakpoints, you may have to restart the system that is running Microsoft Dynamics AX. After the restart, try debugging again. Also make sure that you are running the Debugger with administrative privileges.</P>
> <P>You can also add the breakpoint statement to your X++ code at the location where you want execution to stop. The X++ debugger should stop when it encounters this keyword.</P>
> <P>If you are debugging the list page interaction class for a list page in Enterprise Portal, be sure that the AOS service is running as the same domain user that is being used for the Business Connector Proxy.</P>


