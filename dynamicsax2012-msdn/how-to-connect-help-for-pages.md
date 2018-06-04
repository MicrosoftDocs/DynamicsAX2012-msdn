---
title: 'How to: Connect Help for Pages'
TOCTitle: 'How to: Connect Help for Pages'
ms:assetid: 0f0184f5-f756-42d3-b637-88b89e4a7c0c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc519590(v=AX.60)
ms:contentKeyID: 35244899
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Connect Help for Pages 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Online Help is provided for Enterprise Portal. The online help contains generic help topics for each standard page type. When you create pages, you should configure the new pages to display the generic help topic for that type of page. The following table lists the page types and the corresponding WSSHelpTopic property value that specifies the generic help topic for that page type.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Page type</p></th>
<th><p>WSSHelpTopic value</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Role Center page</p></td>
<td><p>MSEP_EPRoleCenterPage</p></td>
</tr>
<tr class="even">
<td><p>Site Home page</p></td>
<td><p>MSEP_EPSiteHomePage</p></td>
</tr>
<tr class="odd">
<td><p>List page</p></td>
<td><p>MSEP_EPListPage</p></td>
</tr>
<tr class="even">
<td><p>Entity Overview page</p></td>
<td><p>MSEP_EPEntityOverviewPage</p></td>
</tr>
<tr class="odd">
<td><p>Task page</p></td>
<td><p>MSEP_EPTaskPage</p></td>
</tr>
</tbody>
</table>


If you create your own help collection for SharePoint, use the key values that correspond to topics in your help collection when you specify the help topic to display for a page.

## Connecting a Help Topic for a Page

### To connect a help topic for a page

1.  Be sure the page has been imported into the AOT. For details about doing this, see [How to: Import Pages into the AOT](how-to-import-pages-into-the-aot.md).

2.  In the AOT, expand the **Web** node, and then expand the **Web Files** node.

3.  Expand **Page Definitions** node.

4.  Right-click the page for which you want to specify a help topic, and then click **Properties**.

5.  Set the **WSSHelpTopic** property based on the values in the previous table. For example, if you create a list page, set the WSSHelpTopic property to MSEP\_EPListPage.

6.  Save the changes in the AOT.

