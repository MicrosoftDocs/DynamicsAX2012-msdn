---
title: 'How to: Debug User Controls'
TOCTitle: 'How to: Debug User Controls'
ms:assetid: 1e4b0e24-8e9e-4626-9202-2c25fba4a3ff
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc567649(v=AX.60)
ms:contentKeyID: 28119407
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Debug User Controls [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use Visual Studio to debug the code used in User Controls. You can debug when the User Control is being run in the ASP.NET Development Server environment or in Enterprise Portal.

## Debugging in the ASP.NET Development Server Environment

To debug a User Control in the ASP.NET Development Server environment, you must create a Dynamics AX Webpart Page that will run the User Control. For more information, see [How to: Test User Controls in Visual Studio](how-to-test-user-controls-in-visual-studio.md).

### To debug in the ASP.NET Development Server environment

1.  Start Visual Studio.

2.  Open the EP Web Application project that contains the User Control that you want to debug.

3.  View the code for the User Control. Do this by right-clicking the User Control in **Solution Explorer**, and then clicking **View Code**.

4.  Add breakpoints to the appropriate locations in the code.

5.  In the **Debug** menu, click **Start Debugging**.

6.  In the web browser window that is displayed, click the file name for the Dynamics AX Webpart page (.aspx) that contains the User Control that you want to debug. Visual Studio should stop execution at the designated breakpoints.

## Debugging in Enterprise Portal

To debug a User Control that is running in Enterprise Portal, you must enable debugging for the Enterprise Portal web site, and then configure your EP Web Application project for debugging.

### To enable debugging for the Enterprise Portal web site

1.  On the system that is running Enterprise Portal, locate the web.config file for the Enterprise Portal site. Typically, this found in C:\\inetpub\\wwwroot\\wss\\VirtualDirectories\\80\\. If you are running Enterprise Portal on a port other than 80, the web.config file will be found in a folder with that number.

2.  Use a text editor such as Notepad to edit the web.config file.

3.  Search for the node that is named compilation. Set the debug attribute for this node to true.
    
        <compilation batch="false" debug="true">
    

    > [!IMPORTANT]
    > <P>We do not recommend that you enable debugging in production environments for Enterprise Portal.</P>



4.  Save the changes to the web.config file.

### To debug in Enterprise Portal

1.  Start Visual Studio. If User Account Control (UAC) is active, be sure you start Visual Studio with administrative privileges.

2.  Start Enterprise Portal.

3.  Open the EP Web Application project that you want to use for debugging.

4.  In the **Debug** menu in Visual Studio, choose **Options and Settings**. Expand the **Debugging** group and select **General**. Be sure that **Require source files to exactly match the original version** is not marked. Click **OK**.

5.  Add the User Control to the EP Web Application project.

6.  If the User Control uses any proxies to access X++ code, add the needed proxy projects to the solution in Visual Studio. To add a proxy project, click the **Project** menu, choose **Add EP Proxy Project**. Select the proxy project and click **OK**. The **EPApplicationProxies** project is the most frequently used proxy project.

7.  Attach the Visual Studio debugger to the process for Enterprise Portal. In the **Debug** menu, click **Attach to Process**.

8.  Click **Select** to specify the type of code you want to attach to. Mark **Managed (v2.0, v1.1, v1.0)**, and then click **OK**.

9.  Mark the **Show processes from all users** and **Show processes in all sessions** to be sure that all processes are being displayed.

10. In the **Available Processes** list, select the **w3wp.exe** process that is being used for Enterprise Portal. If there are multiple processes with that name, the values in the **Type** and **User Name** columns may help you determine which is the process being used for Enterprise Portal. If you cannot determine which process is being used, select all of the **w3wp.exe** processes.

11. Click **Attach** to attach the Visual Studio debugger to the selected processes.

12. View the code for the User Control. Do this by right-clicking the User Control in **Solution Explorer**, and then clicking **View Code**.

13. Add breakpoints to the appropriate locations in the code.

14. In Enterprise Portal, navigate to the page that contains the User Control that you want to debug. When the breakpoints you set are encountered, the Visual Studio debugger should stop execution at the designated breakpoints.

