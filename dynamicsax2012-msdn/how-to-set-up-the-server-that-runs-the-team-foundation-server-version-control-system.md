---
title: 'How to: Set up the Server that Runs the Team Foundation Server Version Control System'
TOCTitle: 'How to: Set up the Server that Runs the Team Foundation Server Version Control System'
ms:assetid: 1b9e7a41-3461-47ba-a04e-7a568e95db84
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886621(v=AX.60)
ms:contentKeyID: 35267985
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Set up the Server that Runs the Team Foundation Server Version Control System [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic deals with how to set up Team Foundation Server (TFS) as a version control system for Microsoft Dynamics AX.

To set up the server you will need to:

  - Connect Team Explorer to TFS.

  - Create a team project.

  - Add all of the developers to the team project as members.

  - Restrict developer access to the system settings.
    

    > [!NOTE]
    > <P>We recommend that you restrict access to the VCSdev.xml file to prevent developers from modifying global version control settings.</P>



### To connect Team Explorer to TFS

1.  In Team Explorer, click **Tools** \> **Connect to Team Foundation Server**.

2.  Type the name of the Team Foundation Server if it does not appear, and then click **OK**.

### To create a team project

1.  Click **File** \> **New Team Project**.

2.  Follow the instructions in the **New Team Project Wizard** to create a project.

### To add all of the developers to the team project as members

1.  Click **View** \> **Team Explorer** to display Team Explorer.

2.  Right-click the team project, point to **Team Project Settings**, and then click **Group Membership**.

3.  Add the developers.

### To restrict developer access to the system settings

1.  Click **View** \> **Source Control Explorer**.

2.  Expand the team project, and then double-click **Definition**.

3.  Right-click **VCSdef.xml**, and then click **Properties**.

4.  Click the **Security** tab.

5.  Set the permissions of the group that contains the developers so that developers cannot modify the VCSdef.xml file.

## See also

[How to: Configure Branching for Version Control](how-to-configure-branching-for-version-control.md)

[Team Foundation Administrator help](http://go.microsoft.com/fwlink/?linkid=117754)

[Team Foundation source control](http://go.microsoft.com/fwlink/?linkid=113138%26clcid=0x409)

