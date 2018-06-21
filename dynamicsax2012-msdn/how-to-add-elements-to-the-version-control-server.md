---
title: 'How to: Add Elements to the Version Control Server'
TOCTitle: 'How to: Add Elements to the Version Control Server'
ms:assetid: a443cd19-e0f3-481d-8933-22b4da200eef
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa548641(v=AX.60)
ms:contentKeyID: 35268148
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Add Elements to the Version Control Server [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

After you set up the server that runs the Version Control System (VCS), you must add models that contain elements from your master copy of Microsoft Dynamics AX to the VCS server.

## Create a Local Repository Folder

Create a repository folder on your computer. When you add the Application Object Tree (AOT) elements to the server, a copy of each object is also added to your repository folder.

1.  Open Windows Explorer.

2.  Create a new folder to use as your local repository folder, such as C:\\AX\_dev\\Root.


> [!NOTE]
> <P>You must specify your local repository folder in the <STRONG>Version control parameters</STRONG> form. For more information, see <A href="how-to-set-up-local-version-control-parameters-developer.md">How to: Set Up Local Version Control Parameters (Developer)</A></P>



## Add Elements to the Repository

1.  Click **Version control** \> **Add model to version control**.

2.  In **Check-in description**, describe the check-in.

3.  In **Model ID**, select the model you want to add to the version control system.

4.  In **Model repository folder**, specify the location of the model folder in your local repository. For example, C:\\AX\_dev\\Root\\PrimaryAXApplication\\ModelA.

5.  Click **OK**.
    

    > [!NOTE]
    > <P>This process can take a while, depending on the computer and network speed.</P>


