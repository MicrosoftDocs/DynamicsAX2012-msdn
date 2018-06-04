---
title: 'How to: Connect Page Titles and User Controls'
TOCTitle: 'How to: Connect Page Titles and User Controls'
ms:assetid: f6ed66a6-a5cc-4da0-b988-0d1441f99607
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc624163(v=AX.60)
ms:contentKeyID: 35246172
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Connect Page Titles and User Controls 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Most pages in Enterprise Portal contain a [Page Title Web Part](page-title-web-part.md), used to display the name of the page. This web part can retrieve the name to display from the page definition in the AOT. If the Page title web part is connected to a User control web part, it can retrieve the AxPageTitle information that indicates what text it should display. For more information about the information published with the AxPageTitle, see [Page Title Web Part](page-title-web-part.md).

## Connecting the Web Parts

### To connect the Web parts

1.  In Enterprise Portal, display the page that contains the Page title and User control web parts that you want to connect.

2.  In the **Site Actions** menu, click **Edit Page**.

3.  In the web part menu for the User control web part that will be publishing, click **Connections**. Click **Send AxPageTitleTo**, and then click the Page title web part that you want to connect to.
    
    \-or-
    
    In the web part menu for the Page title web part that will be subscribing, click **Connections**. Click **Get AxPageTitleFrom**, and then click the User control web part that you want to connect to.

4.  To save changes, click **Stop Editing**.

5.  If you will be distributing the web part modifications to other Enterprise Portal installations, import the updated page into the AOT. For more information, see [How to: Import Pages into the AOT](how-to-import-pages-into-the-aot.md).

