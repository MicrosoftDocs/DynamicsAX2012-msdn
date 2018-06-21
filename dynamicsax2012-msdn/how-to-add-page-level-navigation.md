---
title: 'How to: Add Page-level Navigation'
TOCTitle: 'How to: Add Page-level Navigation'
ms:assetid: 166157a3-561c-49b8-a027-b0ca8cded4ad
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc549980(v=AX.60)
ms:contentKeyID: 35245008
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Add Page-level Navigation [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To add page-level navigation to a page, you will add a web part that indicates the web menu content to display.

## Adding page-level navigation

### To add page-level navigation

1.  In Enterprise Portal, open the page for which you want to add page-level navigation.

2.  Choose **Edit** from the **Site Actions** menu.

3.  In the leftmost column of the page, click **Add a Web Part**.

4.  Select the appropriate web part for the navigation and click **Add**. The [QuickLaunch Web Part](quicklaunch-web-part.md) and [Left Navigation Web Part](left-navigation-web-part.md) web parts are used for page-level navigation. Refer to the details of each web part to determine which is appropriate for the page being created.

5.  The Left Navigation web part must have the **WebMenuName** property set to indicate which Web Menu resource the web part will display. To set the properties for the web part, choose **Modify Shared Web Part** from the **Edit** menu.

6.  Specify the **WebMenuName** property.

7.  Click **OK** to save the changes to the new web part.

8.  Click **Exit Edit Mode** to save the changes to the page.

9.  If you will be distributing the page modifications to other Enterprise Portal installations, import the updated page into the AOT. For more information, see [How to: Import Pages into the AOT](how-to-import-pages-into-the-aot.md).

