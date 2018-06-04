---
title: 'How to: Set up the Server that Runs the Visual SourceSafe Version Control System'
TOCTitle: 'How to: Set up the Server that Runs the Visual SourceSafe Version Control System'
ms:assetid: b2c9523c-8b84-4a4e-ab75-44222e6bb7e1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa548660(v=AX.60)
ms:contentKeyID: 35268160
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Set up the Server that Runs the Visual SourceSafe Version Control System 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to set up Microsoft Visual SourceSafe (VSS) as a version control system for Microsoft Dynamics AX.

To set up the server you must:

  - Create a new VSS database on the version control server.

  - Create a project.

  - Share the VSS database folder.

  - Restrict developer access to the system settings.
    

    > [!NOTE]
    > <P>We recommend that you restrict access to the VCSdev.xml file to prevent developers from modifying global version control settings.</P>



### To create a new VSS database on the version control server

1.  Open **Microsoft Visual SourceSafe Administration**.

2.  Click **File** \> **New Database**, and then click **Next**.

3.  In the **Location** text box, type the path and folder name of the database, and then click **Next**.

4.  Type the name of the new VSS database, and then click **Next**.

5.  Select the **Lock-Modify-Unlock Model** check box to use the pessimistic concurrency model, or select the **Copy-Modify-Merge Model** check box to allow for concurrent development, and then click **Next**.

6.  Click **Finish**.

### To create a project

1.  Open VSS. In the VSS database, right-click the root node (**$/**), and then click **Create project**.

2.  Type a name for the project that will hold the Microsoft Dynamics AX objects.

### To share the VSS database folder

1.  Right-click the VSS database folder, and then click **Sharing and Security**.

2.  Click **Share this folder**.

3.  Click the **Permissions** button.

4.  In the **Group or User names** pane, select a user group, a user, or everyone.

5.  Select the **Allow Full Control** check box, and then click **OK** two times.

### To restrict developer access to the system settings

1.  Open **Microsoft Visual SourceSafe Administration**.

2.  Click **Tools** \> **Options**.

3.  On the **Project rights** tab, select **Enable Rights and Assignments commands**, and then click **OK**.

4.  Click **Tools** \> **Rights by project**.

5.  Expand the project nodes, and then select the **Definitions** node.

6.  Select all of the developers in the users list, and clear the **Check Out/Check In** check box.
    

    > [!NOTE]
    > <P>This enables read-only access to all developers, and the administrator keeps all rights.</P>


