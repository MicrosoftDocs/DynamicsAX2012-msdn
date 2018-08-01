---
title: 'How to: Test User Controls in Visual Studio'
TOCTitle: 'How to: Test User Controls in Visual Studio'
ms:assetid: a780f71c-bc60-4a6e-8923-98e342c10fd2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc616458(v=AX.60)
ms:contentKeyID: 28119468
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Test User Controls in Visual Studio [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When developing simple User Controls for Enterprise Portal, you may find it helpful to test and debug the controls in the ASP.NET Development Server environment. This test environment can be accessed directly from Visual Studio.


> [!WARNING]
> <P>While testing simple User Controls directly from Visual Studio can make development faster, you will still want to use the actual Enterprise Portal environment to thoroughly test User Controls that you create or modify.</P>



To test User Controls in the ASP.NET Development Server environment, you must do the following:

  - Open the Default.aspx page that is part of your EP Web Application project. This is an ASP.NET page that can host web parts needed for testing User Controls. The Default.aspx page is automatically included in any EP Web Application project you create.

  - Configure the web parts on the Default.aspx page.

  - Add any EP Proxy Projects that are required for your EP Web Application project.

  - Run the Default.aspx page.

## Opening the Default.aspx Page

### To open the Default.aspx page

1.  Start Visual Studio.

2.  Open the EP Web Application project for which you are creating a User Control.

3.  In **Solution Explorer**, open the Default.aspx page.

4.  Display the Design view for the page.

## Configuring Web Parts on the Default.aspx Page

The Default.aspx page will already contain several components. The ScriptManager and WebPartManager components provide capabilities needed for the page to display web parts. The page will also contain an AxInfolog and an AxUserControlWebPart. These components display an Infolog web part and a User Control web part, just as a page in Enterprise Portal would. You can add more User Control web parts to this page so that it will operate in a similar manner to a page in Enterprise Portal.

### To configure web parts on the Default.aspx page

1.  Specify the User Control to be displayed on the web page. Select the AxUserControlWebPart on the page, and set the **Managed Web Content Item** property to specify the User Control to be displayed on the page. The AxUserControlWebPart is the last item in the Body group on the page.
    

    > [!IMPORTANT]
    > <P>The User Control must have already been added to the current project.</P>



2.  If several User Controls will be used together on the page, add more User Control web parts. To add more web parts, you must manually add them to the markup for the page. See [AxUserControlWebPart](axusercontrolwebpart.md) for more information about how to add an AxUserControlWebPart to the markup.

## Adding EP Proxy Projects

If any one of the User Controls on the Default.aspx page uses proxies to access X++ code, the EP Proxy Project that defines the proxies must be added to the EP Web Application project.

### To add an EP proxy project

1.  In the **Project** menu, choose **Add EP Proxy Project**. A dialog box will be displayed that lists all of the proxy projects that have been added to the AOT. The **EPApplicationProxies** project is the most frequently used proxy project. It contains definitions for several enums, classes, and tables that are frequently used in code for User Controls.

2.  Select the proxy project that is accessed by your User Control, and then click **OK**. The proxy project will be added to the solution, and a reference to the proxy project will be created.

If a proxy is needed but has not been added to your EP Web Application project, the EP Web Application project will have build errors.

## Running the Default.aspx Page

After the Default.aspx page has been designed and configured, it can be run in the ASP.NET Development Server environment.

### To run the Default.aspx page

1.  In the **Build** menu, click **Build Solution**. The EP Web Application project should build without errors. If errors are found, correct them and build again.

2.  Be sure the Default.aspx page is open and active in Visual Studio.

3.  In the **Debug** menu, click **Start Debugging**. After several moments, a web browser will appear and display the content of the Default.aspx page.

4.  Test the controls on the page.

5.  When you have finished, close the web browser window to stop debugging and return to Visual Studio.

