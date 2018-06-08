---
title: Page Title Web Part
TOCTitle: Page Title
ms:assetid: 9baf3515-e6a2-4f46-a226-44c226f4f385
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc595967(v=AX.60)
ms:contentKeyID: 35245522
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Page Title Web Part 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Page title web part displays the title on the page. The following illustration shows a Page title web part for a page displayed in a modal dialog.

![Page Title](images/Cc595967.EP_PageTitle(AX.60).gif "Page Title")

**Page Title**

When the Page title web part is not connected to another web part on the page, it will display the value defined for the **PageTitle** property of the page definition in the AOT. Page definitions are found in the **Web** \> **Web Files** \> **Page Definitions** node of the AOT. Refer to [How to: Import Pages into the AOT](how-to-import-pages-into-the-aot.md) for information about how to add an Enterprise Portal page to the AOT.

When the Page title web part is connected to a User Control web part, it uses the value of the **Label** property of the managed content item for the User Control in the AOT and the current provider context to create a page title to display. The Managed content items are found in the **Web** \> **Web Content** \> **Managed** node of the AOT.

In the code for the User Control, you can manually set the value to be passed as the AxPageTitle object, and control whether the current context is included. The following code example shows how to set the page title and control whether the context is included.

``` csharp
protected void Page_Load(object sender, EventArgs e)
{
    ITitleProvider titleProvider = AxBaseWebPart.GetWebpart(this) as ITitleProvider;

    // Specify the title to pass as the AxPageTitle
    titleProvider.Caption = "Page title goes here";

    // Do not include the context in the title
    titleProvider.ShowContext = false;
}
```


> [!IMPORTANT]
> <P>Make sure that you have created the web part connection between the User Control web part and the Page title web part. Without this connection, the AxPageTitle will not be passed from the User Control to the Page title.</P>



## Page Types Used On

Most Enterprise Portal pages have a Page title web part.

## Microsoft Dynamics AX Properties

The Page title web part has no properties specific to Microsoft Dynamics AX.

## Connections

Can subscribe to any web part that publishes an AxPageTitle. User Controls, QuickLaunch, and List web parts can publish the AxPageTitle.

## Comments

New web part pages that you create in the Enterprise Portal document library for an Enterprise Portal site will already have the Page title web part. You do not need to add it to the page.

