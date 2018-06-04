---
title: 'How to: Find Objects and Roles Related to Security Constructs'
TOCTitle: 'How to: Find Objects and Roles Related to Security Constructs'
ms:assetid: e90661f0-5ac0-4115-bf7c-96ee29d3ee96
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh745340(v=AX.60)
ms:contentKeyID: 42607690
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Find Objects and Roles Related to Security Constructs 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In the AOT, shortcut menus are available on some Application Object Tree (AOT) nodes to find security objects and roles that are related to a particular node. For the example of duties, the following list describes the typical menu actions:

1.  In the AOT, expand **Security** \> **Duties**.

2.  Right-click any one duty node, and then click **Add-Ins** \> **Security tools**.

3.  At the last level of the shortcut menu, click either **View related security objects** or **View related security roles**.

4.  Examine the rows in the grid control on the form that is displayed.

## Menu Options per Security Item Type

The following table lists the menu options that are available for each type of AOT node.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>AOT path</p></th>
<th><p>Artifact name</p></th>
<th><p><em>menu:</em> View related security objects</p></th>
<th><p><em>menu:</em> View related security roles</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Data Dictionary &gt; Tables</p></td>
<td><p>Tables</p></td>
<td><p>Not available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="even">
<td><p>Data Dictionary &gt; Views</p></td>
<td><p>Views</p></td>
<td><p>Not available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="odd">
<td><p>Security &gt; Code Permissions</p></td>
<td><p>Code permissions</p></td>
<td><p>Not available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="even">
<td><p>Security &gt; Duties</p></td>
<td><p>Duties</p></td>
<td><p>Available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="odd">
<td><p>Security &gt; Privileges</p></td>
<td><p>Privileges</p></td>
<td><p>Available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="even">
<td><p>Security &gt; Roles</p></td>
<td><p>Roles (and nested or sub-roles)</p></td>
<td><p>Available.</p></td>
<td><p>Not available.</p></td>
</tr>
<tr class="odd">
<td><p>Forms</p></td>
<td><p>Forms</p></td>
<td><p>Not available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="even">
<td><p>Menu Items &gt; Display, Output, Action</p></td>
<td><p>Menu items</p></td>
<td><p>Available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="odd">
<td><p>Parts &gt; Info Parts</p></td>
<td><p>Info parts</p></td>
<td><p>Not available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="even">
<td><p>Services &gt; serviceName &gt; Operations</p></td>
<td><p>Operations</p></td>
<td><p>Available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="odd">
<td><p>SSRS &gt; Reports &gt; reportName &gt; Designs</p></td>
<td><p>Designs (for reports)</p></td>
<td><p>Not available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="even">
<td><p>Web &gt; Web Menus</p></td>
<td><p>Web menus (URLs, actions)</p></td>
<td><p>Available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="odd">
<td><p>Web &gt; Web Content &gt; Managed</p></td>
<td><p>Web content (managed)</p></td>
<td><p>Available.</p></td>
<td><p>Available.</p></td>
</tr>
<tr class="even">
<td><p>Web &gt; Web Files &gt; Controls</p></td>
<td><p>Web controls</p></td>
<td><p>Not available.</p></td>
<td><p>Available.</p></td>
</tr>
</tbody>
</table>


## Example Displays of the Form

This section provides examples of the form that displays for each shortcut menu option choice. The title of the form varies, but under **AOT** \> **Forms** its name is **SysSecObjectsInRoles**.


> [!NOTE]
> <P>The form images in this section are from an installation of Microsoft Dynamics AX 2012.</P>



### ![Hh745340.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh745340.collapse_all(en-us,AX.60).gif")Form: Related Objects

The following image is an example of the form that is displayed when you click the shortcut menu option **View related security objects** for a node under **AOT** \> **Security** \> **Roles**.

![Form to view related security objects](images/Hh745340.ViewRelatedSecurityObjects(en-us,AX.60).png "Form to view related security objects")

  
The following form is displayed when you click the **View effective access** link on the preceding form.

![View effective access](images/Hh745340.ViewEffectiveAccess(en-us,AX.60).png "View effective access")

   

### ![Hh745340.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh745340.collapse_all(en-us,AX.60).gif")Form: Related Roles

The following image is an example of the form that is displayed when you click the shortcut menu option **View related security roles** for a node under **AOT** \> **Security** \> **Duties**.

![Form to view related security roles](images/Hh745340.ViewRelatedSecurityRoles(en-us,AX.60).png "Form to view related security roles")

## See also

[Security Node Entities in the AOT](security-node-entities-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

