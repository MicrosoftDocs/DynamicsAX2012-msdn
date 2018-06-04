---
title: 'How to: Connect Microsoft Dynamics AX to a TFS Proxy'
TOCTitle: 'How to: Connect Microsoft Dynamics AX to a TFS Proxy'
ms:assetid: 925a2ec7-93bd-4aef-8f72-da4a6d9a2ad9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh337200(v=AX.60)
ms:contentKeyID: 36806624
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Connect Microsoft Dynamics AX to a TFS Proxy 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can configure Team Foundation (TFS) version control to use a proxy server, which caches copies of version control files in the location of a distributed team. Using a proxy server can significantly reduce bandwidth requirements for remote developers.

## Accessing a TFS Proxy from a Microsoft Dynamics AX Client

You can access a TFS proxy from a Microsoft Dynamics AX client by updating the registry through Visual Studio or by setting an environment variable.

### To update the registry through Visual Studio

1.  Follow the procedure at [Configure Team Foundation Version Control to use Proxy Server](http://go.microsoft.com/fwlink/?linkid=223434).

2.  Connect Microsoft Dynamics AX by using the same parameters you would for a physical server. For more information, see [How to: Set Up Local Version Control Parameters (Developer)](how-to-set-up-local-version-control-parameters-developer.md).

### To set an environment variable

1.  Open the System Properties window. For example, in Windows Server 2008, click **Control Panel** \> **System and Security** \> **System** \> **Advanced system settings**.

2.  Click **Environment Variables**.

3.  Click **New…** to create a new system variable.

4.  In **Variable name**, type TFSPROXY.

5.  In **Variable value**, type the URL of the proxy.

6.  Connect Microsoft Dynamics AX by using the same parameters you would for a physical server. For more information, see [How to: Set Up Local Version Control Parameters (Developer)](how-to-set-up-local-version-control-parameters-developer.md).

## See also

[Configure Team Foundation Version Control to use Proxy Server](http://go.microsoft.com/fwlink/?linkid=223434)

[How to: Install Prerequisites on the Server that Runs the Team Foundation Server Version Control System](how-to-install-prerequisites-on-the-server-that-runs-the-team-foundation-server-version-control-system.md)

[How to: Set up the Server that Runs the Team Foundation Server Version Control System](how-to-set-up-the-server-that-runs-the-team-foundation-server-version-control-system.md)

[How to: Set up Developer Computers for Version Control Using Team Foundation Server](how-to-set-up-developer-computers-for-version-control-using-team-foundation-server.md)

[Configuring Version Control in Microsoft Dynamics AX](configuring-version-control-in-microsoft-dynamics-ax.md)

