---
title: Troubleshooting Charts
TOCTitle: Troubleshooting Charts
ms:assetid: 84b1c690-8a30-44f3-b1b2-6aa4f30dc88b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677314(v=AX.60)
ms:contentKeyID: 49384085
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Troubleshooting Charts 


_**Applies To:** Microsoft Dynamics AX 2012 R2_

The following solutions can be helpful when you encounter problems creating Chart Controls in Enterprise Portal. For Enterprise Portal related issues, see [Troubleshooting: Enterprise Portal Development](troubleshooting-enterprise-portal-development.md).

## Debugging Chart Controls

You can debug Chart Controls for Enterprise Portal by using the Visual Studio debugger. When you start debugging, Visual Studio deploys the project files to the SharePoint server and then opens an instance of the SharePoint site in the web browser. For information about how to turn about how to debug, see [Troubleshooting: Enterprise Portal Development](troubleshooting-enterprise-portal-development.md).

The following section explains how to debug Chart Controls in Visual Studio.

### To Debug a Chart Control

1.  In Solution Explorer, right-click Default.aspx and then click **Open**.

2.  Update the dynamics:AxUserControlWebPart tag so that it contains the Chart Control name to debug such as the following:
    
        <dynamics:AxUserControlWebPart ID="AxUserControlWebPart1" runat="server" ManagedContentItem="<ChartControlName>" />

3.  Press Ctrl+S to save changes to the Default.aspx file.

4.  Press F5 to run the Chart Control in debug mode.

## SharePoint Sandbox Error

When you debug a Chart Control, you may receive the following error regarding the SharePoint sandbox.

Could not load file or assembly 'Microsoft.Sharepoint.Sandbox, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c' or one of its dependencies.

**Description:** An unhandled exception occurred during the execution of the current web request. Please review the stack trace for more information about the error and where it originated in the code.

**Exception Details:** System.BadImageFormatException: Could not load file or assembly 'Microsoft.Sharepoint.Sandbox, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c' or one of its dependencies. An attempt was made to load a program with an incorrect format.

The following section explains how to resolve the error by deleting the Microsoft.SharePoint.Sandbox.dll in the Bin folder.

### To Resolve the SharePoint Sandbox Error

1.  Press F5 to run the Chart Control in debug mode. In Internet Explorer, you receive the SharePoint sandbox error. Do not close Internet Explorer.

2.  In Solution Explorer, click the **Show All Files** icon.

3.  Right click the **Bin** folder, and then click **Open Folder in Windows Explorer**.

4.  Right-click the Microsoft.Sharepoint.Sandbox.dll file and then click **Delete**. Click **Yes** to confirm to delete the file.

5.  In Internet Explorer, with the error displayed, press F5 to refresh the Chart Control.

## See also

[Troubleshooting: Enterprise Portal Development](troubleshooting-enterprise-portal-development.md)

