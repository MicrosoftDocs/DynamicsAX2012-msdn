---
title: Version Control System
TOCTitle: Version Control System
ms:assetid: 522708f8-80a0-4bfd-9634-b7cb868d1874
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa639568(v=AX.60)
ms:contentKeyID: 35268024
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Version Control System 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

MorphX, the Microsoft Dynamics AX Integrated Development Environment (IDE), can integrate various Version Control Systems (VCS). You can integrate:

  - Microsoft Visual Studio Team Foundation Server (TFS)

  - Microsoft Visual SourceSafe

  - MorphX VCS

  - Another third-party VCS


> [!NOTE]
> <P>We recommend that you use TFS or MorphX VCS for version control.</P>



## Version Control Considerations

If you use the VSS or TFS version control systems, you should consider the following before you develop code or write documentation:

  - Version control is file-based.

  - You must install Microsoft Visual Studio or Microsoft Visual Studio Team Explorer.

  - Each developer must have an Application Object Server (AOS) and database server.

MorphX VCS allows for out-of-the-box version control system integration. MorphX VCS is intended for one to ten developers who use a shared AOS. Instead of checking out objects and storing them in a repository, MorphX VCS signals to other users that a specific element is being worked on by another user. It provides change description functionality, change history functionality, and quality bar enforcement.


> [!WARNING]
> <P>Because versioning history is stored in the business database when you use MorphX VCS, you should back up the business database before you perform tasks that could lead to restoring the business database. Otherwise, versioning history may be lost.</P>



Microsoft Dynamics AX can integrate with VSS, TFS, and MorphX VCS, but you can extend the version control functionality to use other version control systems.

The following table compares the features available from the different version control options:

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p></th>
<th><p>MorphX</p></th>
<th><p>MorphX VCS</p></th>
<th><p>Visual SourceSafe</p></th>
<th><p>Team Foundation Server</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Concurrent development</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Isolated development</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Change description</p></td>
<td><p>No</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Change history</p></td>
<td><p>No</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Quality bar enforcement</p></td>
<td><p>No</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Branching</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="odd">
<td><p>Work item integration</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Yes</p></td>
</tr>
<tr class="even">
<td><p>Labeling support</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Yes</p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


## In This Section

The following topics contain information to help you set up, configure, and use a version control system:

[Version Control Setup for Microsoft Dynamics AX](version-control-setup-for-microsoft-dynamics-ax.md)

[Configuring Version Control in Microsoft Dynamics AX](configuring-version-control-in-microsoft-dynamics-ax.md)

[Version Control Operations in Microsoft Dynamics AX](version-control-operations-in-microsoft-dynamics-ax.md)

