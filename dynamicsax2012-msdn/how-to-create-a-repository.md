---
title: 'How to: Create a Repository'
TOCTitle: 'How to: Create a Repository'
ms:assetid: a5ca1710-8ee0-4667-917b-1a0d6125e1f1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa851066(v=AX.60)
ms:contentKeyID: 35268155
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Create a Repository [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A repository folder stores copies of all Microsoft Dynamics AX development objects when you use a version control system (VCS) that supports isolated development. Examples of such version control systems are Team Foundation Server (TFS) and Microsoft Visual SourceSafe (VSS).

## Creating a Repository Folder

The computers of administrators and developers each have a folder in the local file system that acts as a repository folder. For a developer computer, the repository folder receives a local copy to edit when you check out items.

We recommend that you do not share the same repository between the Microsoft Dynamics AX client and the version control client. You can install Team Explorer or the VSS client on developer computers. If one of these clients that runs against the version control server shares a repository folder with a Microsoft Dynamics AX client, a conflict may occur. If a change is checked in by using the Team Explorer instance or the VSS client, the Microsoft Dynamics AX client will not reflect those changes when you synchronize the Microsoft Dynamics AX client unless you select **Force** when you synchronize.

One example of a repository structure for TFS version control is as follows:

$/\<ProjectName\>/Branches/Main/PrimaryAXApplication/ModelA/Classes

The following table describes the elements in the example repository structure.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Element</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;ProjectName&gt;</p></td>
<td><p>The project root. Specify this value in the <strong>Version control parameters</strong> form.</p></td>
</tr>
<tr class="even">
<td><p>Branches/Main</p></td>
<td><p>A branch folder. Specify this value in the <strong>Version control parameters</strong> form.</p>
<p>Branching is optional, but recommended. You can use branching if you use TFS for version control. You should have a main branch and additional branches for development or incremental releases. For more information about branching, see <a href="how-to-configure-branching-for-version-control.md">How to: Configure Branching for Version Control</a></p>
<p>Each branch can have an application folder for Microsoft Dynamics AX. Each branch can have another folder for elements that are not in Microsoft Dynamics AX. For example, you could have a folder for C++ library elements from Visual Studio that you want to add to version control.</p></td>
</tr>
<tr class="odd">
<td><p>PrimaryAXApplication</p></td>
<td><p>The application folder; optional. Specify this value in the <a href="how-to-set-up-local-version-control-parameters-developer.md">Version control parameters</a> form.</p>
<p>The application folder contains a definition file and <a href="working-with-models-in-aot.md">models</a>. A definition file defines global settings for version control users and the list of models that are under version control.</p></td>
</tr>
<tr class="even">
<td><p>ModelA</p></td>
<td><p>The model folder. Specify this value in the <a href="how-to-configure-global-version-control-system-settings-administrator.md">System settings</a> form.</p>
<p>A model folder contains application objects, label files, and the model manifest XML file.</p>

> [!NOTE]
> <P>Use a single level for your model folder. For example, use ModelA instead of Models\ModelA. Otherwise, you might get an error when you use the Pending objects form.</P>


</td>
</tr>
<tr class="odd">
<td><p>Classes</p></td>
<td><p>The AOT path.</p></td>
</tr>
</tbody>
</table>


The actual repository folder could be similar to the following:

C:\\AX\_dev\\Root\\PrimaryAXApplication\\ModelA\\Classes

This example uses branching. You can use branching if you use TFS for version control. For more information about branching, see [How to: Configure Branching for Version Control](how-to-configure-branching-for-version-control.md).


> [!NOTE]
> <P>Notice that the branch is not included in the repository folder structure in the client. The workspace mapping determines the substructure that the Microsoft Dynamics AX client connects to. This example does not show the use of additional subfolders. You can use additional subfolders, but additional subfolders have been deprecated. You cannot use additional subfolders and models at the same time.</P>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Element</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>C:\AX_dev\Root</p></td>
<td><p>The repository folder. Specify this value in the <strong>Version control parameters</strong> form.</p></td>
</tr>
<tr class="even">
<td><p>PrimaryAXApplication</p></td>
<td><p>The application folder. The application folder is optional unless you add elements to version control that are not in Microsoft Dynamics AX.</p></td>
</tr>
<tr class="odd">
<td><p>ModelA</p></td>
<td><p>The model folder.</p></td>
</tr>
<tr class="even">
<td><p>Classes</p></td>
<td><p>The AOT path.</p></td>
</tr>
</tbody>
</table>


### To create a repository folder

1.  Open Windows Explorer.

2.  Create a new folder to use as the local repository folder. A minimal example of the folder structure for a main branch that contains one model called ModelA is C:\\MyEnlistments\\Main\\ModelA.


> [!NOTE]
> <P>The structure of your repository depends on your development process and the VCS you use. For example, if you use TFS for version control, you can use branching. If you use VSS for version control, you can use additional subfolders. If you use MorphX VCS, your repository structure might be simpler.</P>



## See also

[Version Control System](version-control-system.md)

[How to: Synchronize Your Local Repository with the Version Control System](how-to-synchronize-your-local-repository-with-the-version-control-system.md)

