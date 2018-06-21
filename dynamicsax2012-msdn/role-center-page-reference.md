---
title: Role Center Page Reference
TOCTitle: Role Center Page
ms:assetid: 7a58bb8a-72e4-402e-bb1b-375eae9f6d60
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc558235(v=AX.60)
ms:contentKeyID: 35245415
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Role Center Page Reference [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The role center page is displayed as the home page for the Home site in Enterprise Portal. It is the first page that users see when they access Enterprise Portal. It is also displayed in the Microsoft Dynamics AX client.

Enterprise Portal contains role center pages for the various roles that users can have in Microsoft Dynamics AX. If a user is not assigned to a specific role, the default role center page is displayed.

## Page Content

A role center page typically contains the items in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Item</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cues</p></td>
<td><p>The <a href="cues-web-part.md">Cues Web Part</a> displays a pictorial representation of some activity for a business, such as the number of open sales orders.</p></td>
</tr>
<tr class="even">
<td><p>Quick Links</p></td>
<td><p>The <a href="quick-links-web-part.md">Quick Links Web Part</a> displays a collection of links that the Enterprise Portal administrator or user can modify. The links provide quick access to other resources, such as locations in Enterprise Portal or external web sites.</p></td>
</tr>
<tr class="odd">
<td><p>Work Lists</p></td>
<td><p>The <a href="unified-worklist-web-part.md">Unified Worklist Web Part</a> displays the list of activities, alerts, workflow approvals, and workflow tasks for the user.</p></td>
</tr>
<tr class="even">
<td><p>Measures and KPIs</p></td>
<td><p>The <a href="business-overview-web-part.md">Business Overview Web Part</a> is used to display measures and Key Performance Indicators (KPIs).</p></td>
</tr>
<tr class="odd">
<td><p>Reports</p></td>
<td><p>The <a href="ssrs-report-web-part.md">SSRS Report Web Part</a> displays Microsoft SQL Server Reporting Services reports for Microsoft Dynamics AX.</p></td>
</tr>
<tr class="even">
<td><p>Connect</p></td>
<td><p>The <a href="connect-web-part.md">Connect Web Part</a> displays links to community information for Microsoft Dynamics AX.</p></td>
</tr>
</tbody>
</table>


For more information about designing role center pages, see [Enterprise Portal Role Center User Experience Guidelines](enterprise-portal-role-center-user-experience-guidelines.md).

## Editing a Role Center Page

When a role center page is displayed in Enterprise Portal, it can be edited just like any other page. However, only the role center page associated with the current user's role is actually displayed. If you want to modify other role center pages, you must locate them directly in SharePoint.

You can see a list of the role center pages by viewing the forms that have been added to the main Enterprise Portal site. The following URL will display this list.

http://\<server\>/sites/DynamicsAx/Enterprise%20Portal/Forms/AllItems.aspx

The role center page names begin with "RoleCenter". The exception is the EPDefaultRoleCenter page, which is the role center displayed for users who are not assigned to a specific role. Click the page name to modify the page.

## Creating a Role Center Page

You can create a role center page for Microsoft Dynamics AX.

### To create a role center page

1.  In Enterprise Portal, create a page that will be used as the role center page. This page should be added in the Enterprise Portal library of the Home site for the Enterprise Portal installation. For more information, see [How to: Create Pages](how-to-create-pages.md).

2.  Create a URL web menu item that points to the new role center page. This web menu item is used when navigating to the page. For instance, a web menu item name EPSampleRoleCenter would point to the RoleCenterSample.aspx page. For more information about how to create URL web menu items, see [How to: Add Pages to Navigation](how-to-add-pages-to-navigation.md).

3.  Set the **Label** property for the new URL web menu item to Role Center.

4.  Set the **HomePage** property for the new URL web menu item to Yes. This specifies that the page is a role center. It will appear in the **User profiles** window in Microsoft Dynamics AX with the other role center pages.

## Creating a User Profile

You can create a user profile and corresponding role center page for Microsoft Dynamics AX.

### To create a user profile

1.  Using the previous procedure, create the role center page that will be used for the user profile.

2.  In Microsoft Dynamics AX, display the **Administration** navigation pane.

3.  In the **Common** group, click **Users** \> **User profiles** to open the **User profiles** form.

4.  Click **New** to create a new user profile.

5.  Supply the **Profile ID** and **Description** for the user profile.

6.  Select the role center page to use for the user profile.

7.  Save the new entry.

8.  If the new user profile is to be used with other Microsoft Dynamics AX installations, you must add it to the AOT. From the AOT, the user profile can be packaged for distribution to other Microsoft Dynamics AX installations. To add the user profile to the AOT, select it in the list. Click **Export**, and then click **Export to AOT**.
    

    > [!TIP]
    > <P>The <STRONG>Export</STRONG> menu may be located in the menu overflow area for the form.</P>



9.  In the AOT, expand the **Resources** node. The new user profile will be listed with the other user profiles. Its name will begin with Profile\_.

