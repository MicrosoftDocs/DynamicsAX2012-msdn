---
title: Troubleshooting Application Explorer
TOCTitle: Troubleshooting Application Explorer
ms:assetid: 9d222fc0-4f61-4214-9648-0bda2082c48d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee910017(v=AX.60)
ms:contentKeyID: 28119552
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# Troubleshooting Application Explorer 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes common problems that can occur in Application Explorer when you create or customize a Microsoft Dynamics AX business application in Visual Studio.

## Cannot Establish a Connection to the AOS

To open Application Explorer, you must have a connection to the Application Object Server (AOS). If the AOS is disconnected or stops running after Application Explorer is opened, an AOS connection error message displays when the next command executes. To continue, restart or restore the connection to the AOS, and then repeat the failed command.

## Invalid or Missing Client Configuration

The model store database that is defined in the client configuration is used by Application Explorer. If there is no client configuration, or the client configuration does not define a valid AOS, Application Explorer will display an error message. To use Application Explorer, create or update the client configuration.

## AOT Changes Not Reflected

If you make changes in the Application Object Tree (AOT) in MorphX when you have Visual Studio open, those changes may not be immediately reflected in Application Explorer. To refresh Application Explorer, right-click the AOT element and then click **Refresh**.

## See also

[Application Explorer](application-explorer.md)

[Keyboard Shortcuts in Application Explorer](keyboard-shortcuts-in-application-explorer.md)

