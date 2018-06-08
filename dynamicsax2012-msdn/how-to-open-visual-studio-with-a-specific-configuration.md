---
title: 'How to: Open Visual Studio with a Specific Configuration'
TOCTitle: 'How to: Open Visual Studio with a Specific Configuration'
ms:assetid: cd436d83-04d4-44f1-92a3-cf4366b332a9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889291(v=AX.60)
ms:contentKeyID: 35272184
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# How to: Open Visual Studio with a Specific Configuration 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can configure Visual Studio to open with a specific Microsoft Dynamics AX client configuration. This causes Application Explorer to point to the designated configuration. A configuration is a group of startup settings that are used by a client. For more information, see [Manage a client configuration](https://msdn.microsoft.com/en-us/library/aa569651\(v=ax.60\))

To open a specific configuration, you use the /AxConfig switch with a parameter of either a configuration name or the path and file name of a configuration file (.axc file). If your configuration name or configuration file name contains spaces, be sure to enclose the parameter in quotes. If no parameter is specified, then the default configuration is used.

If you are working with reports, the Visual Studio integration uses the active local client configuration to establish the connection. Examples that require a Reporting Services configuration include deploying a report or selecting a query as a data source. To point to the correct AOS in this scenario, create a copy of the configuration file in the Visual Studio integration folder.


> [!TIP]
> <P>If you point Visual Studio to an invalid configuration or a configuration that has been deleted and then try and open it, Visual Studio will open but the Application Explorer pane will display the message <STRONG>AOS Disconnected</STRONG>.</P>



This topic shows you how to configure Visual Studio to open with a client configuration from a shortcut or from the command line. It also describes how to set the configuration for Microsoft Dynamics AX reporting scenarios.

## Prerequisites

To complete this scenario you will need:

  - Microsoft Dynamics AX with Visual Studio Tools installed

  - Visual Studio 2010

  - At least one Microsoft Dynamics AX client configuration

### To Open Visual Studio with a Specific Configuration from a Shortcut

1.  On the client computer that is running Visual Studio, open the **Start** menu, right-click **Visual Studio 2010**, and select **Properties**.

2.  Update the **Target** field and add the /AxConfig switch with either the name of the client configuration or the name of the client configuration file as shown in the following examples:
    
    "C:\\Program Files\\Microsoft Visual Studio 9.0\\Common7\\IDE\\devenv.exe" /AxConfig ContosoDev
    
    or
    
    "C:\\Program Files\\Microsoft Visual Studio 9.0\\Common7\\IDE\\devenv.exe" /AxConfig z:\\Config\\ContosoDev.axc
    
    If you run the Visual Studio executable with a parameter of /?, then it will show you all the available switches you can use.
    

    > [!NOTE]
    > <P>When pointing to a configuration file, you can use a Universal Naming Convention (UNC) file location such as \\Server\Configurations\ContosoDev.axc.</P>



3.  Click **OK**. When you click the Visual Studio shortcut, it opens and Application Explorer points to the specified client configuration. The name of the configuration appears at the top in the root node of Application Explorer.

### To Open Visual Studio with a Specific Configuration from the Command Line

1.  You can open Visual Studio with a client configuration from the command line. To do so, click **Start** \> **Run**, type cmd and then click **OK**.

2.  Navigate to the directory that contains the Visual Studio IDE executable, for example, C:\\Program Files (x86)\\Microsoft Visual Studio 10.0\\Common7\\IDE. Then type one of the commands shown in the previous procedure (without the quotes), for example, devenv.exe /AxConfig ContosoDev.

### To Create a Specific Configuration for Reports

  - To create a configuration for Reporting Services, run the Microsoft Dynamics AX configuration utility as an administrator, and then click **Manage** \> **Save configuration as file**, and give the configuration a name like **Microsoft.Dynamics.AX.ReportConfiguration.axc**. The file must be saved in the **PrivateAssemblies** folder in the Visual Studio IDE installation directory, like the following:
    
    C:\\Program Files (x86)\\Microsoft Visual Studio 10.0\\Common7\\IDE\\PrivateAssemblies.

## See also

[Manage a client configuration](https://msdn.microsoft.com/en-us/library/aa569651\(v=ax.60\))

[Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md)

