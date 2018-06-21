---
title: 'How to: Create an EP Web Application Project'
TOCTitle: 'How to: Create an EP Web Application Project'
ms:assetid: 221b6730-1b64-498b-8431-90f41136f104
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc567897(v=AX.60)
ms:contentKeyID: 28119409
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Create an EP Web Application Project [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

User Controls for Enterprise Portal are created or edited in an EP Web Application project in Visual Studio. Typically, you will create one project for each set of User Controls used on a page in Enterprise Portal.

## Creating an EP Web Application Project

### To create an EP Web Application Project

1.  Start Visual Studio. If User Account Control (UAC) is active, be sure you start Visual Studio with administrative privileges.

2.  In the **File** menu, click **New**, and then click **Project**.

3.  In the **New Project** window, select **.NET Framework 3.5** as the framework version to use.
    

    > [!IMPORTANT]
    > <P>For this release of Microsoft Dynamics AX, the EP Web Application project must target the .NET Framework 3.5 to work properly.</P>



4.  In the **Installed Templates** list, select **Microsoft Dynamics AX**. If you do not see this project template, make sure that you have the Visual Studio Tools for Microsoft Dynamics AX installed. For more information, see [How to: Set Up Visual Studio for Enterprise Portal Development](how-to-set-up-visual-studio-for-enterprise-portal-development.md).

5.  Choose the EP Web Application template.

6.  Specify the name of the project and the location of the folder where you want to store the files for the project.

7.  Click **OK** to create the project.

Most EP Web Application projects will need to reference one of the predefined application proxies to build correctly. See [How to: Use a Predefined Proxy for a Web Application Project](how-to-use-a-predefined-proxy-for-a-web-application-project.md) for more information.

