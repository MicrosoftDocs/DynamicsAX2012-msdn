---
title: 'How to: Set Up Local Version Control Parameters (Developer)'
TOCTitle: 'How to: Set Up Local Version Control Parameters (Developer)'
ms:assetid: 67d48366-d6bf-453c-800a-2fd127e40ed8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa641378(v=AX.60)
ms:contentKeyID: 35268056
ms.date: 11/07/2012
mtps_version: v=AX.60
f1_keywords:
- Forms.SysVersionControlParametersDev
---

# How to: Set Up Local Version Control Parameters (Developer) 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can enable a Version Control System (VCS) in Microsoft Dynamics AX by using the **Version control parameters** form. You can use MorphX VCS, Team Foundation Server (TFS), Microsoft Visual SourceSafe (VSS), or you can [integrate another version control system](http://go.microsoft.com/fwlink/?linkid=226018).

Each developer must perform the following tasks to set up their development environment to use VSS or TFS for version control:

  - Create a local repository folder. For more information, see [How to: Create a Repository](how-to-create-a-repository.md)

  - Enable version control.

  - Synchronize the local repository with the version control server. For more information, see [How to: Synchronize Your Local Repository with the Version Control System](how-to-synchronize-your-local-repository-with-the-version-control-system.md)

Developers who use MorphX VCS for version control share an AOS. Therefore, you do not need to create or synchronize a local repository if you use MorphX VCS.

## Enable Version Control Locally (Developer)

The fields in the **Version control parameters** form depend on which VCS you use. Refer to the procedure that pertains to the VCS that you use.

## Procedures

### Enable MorphX Version Control

### To enable MorphX version control

1.  Click **Version control** \> **Version Control Parameters**.

2.  In **Version control status**, select **Enable**.

3.  In **Version control system**, select **MorphX VCS**.

4.  Choose environment settings.

### Enable Team Foundation Server Version Control

### To enable Team Foundation Server version control

1.  Click **Version control** \> **Version Control Parameters**.

2.  In **Version control status**, select **Enable**.

3.  In **Version control system**, select **Team Foundation Server**

4.  In **Repository folder**, type the path of the repository folder.

5.  Choose environment settings.

6.  Click the **Team Foundation Server** link.

7.  In the **Team Foundation Server URL** field, type the URL of the server that has the TFS team project.

8.  In the **Team Foundation project name** field, type the name of the TFS project.

9.  In the **Branch folder** field, enter the location of the branch folder. For more information about the folder structure to use, see [How to: Create a Repository](how-to-create-a-repository.md). For more information about branching, see [How to: Configure Branching for Version Control](how-to-configure-branching-for-version-control.md).

10. In the **Application root folder** field, enter the location of the application root folder. For more information about the folder structure to use, see [How to: Create a Repository](how-to-create-a-repository.md).

### Enable Microsoft Visual SourceSafe Version Control

### To enable Microsoft Visual SourceSafe version control

1.  Click **Version control** \> **Version Control Parameters**.

2.  In **Version control status**, select **Enable**.

3.  In **Version control system**, select **Visual SourceSafe**.

4.  In **Repository folder**, type the path of the repository folder.

5.  Choose environment settings.

6.  Click the **Visual SourceSafe** tab.

7.  In the **Visual SourceSafe root project** field, type the name of the project in VSS.
    

    > [!NOTE]
    > <P>Remember to include the root name, such as $/AxVersionControl.</P>



8.  In the **Visual SourceSafe database .ini file** field, type the path and file name for the SourceSafe.ini file in the SourceSafe database folder.

## See also

[Version Control System](version-control-system.md)

[How to: Synchronize Your Local Repository with the Version Control System](how-to-synchronize-your-local-repository-with-the-version-control-system.md)

