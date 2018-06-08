---
title: 'How to: Create New SharePoint Themes'
TOCTitle: 'How to: Create New SharePoint Themes'
ms:assetid: c9d72fc6-90db-49c8-944c-db788f0848b0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa867986(v=AX.60)
ms:contentKeyID: 35246138
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Create New SharePoint Themes 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

SharePoint provides several themes that you can apply to Enterprise Portal sites. If you use SharePoint Server, you can customize any of the existing themes. If you use either SharePoint Foundation or SharePoint Server, you can create your own SharePoint theme.

## Customizing an Existing Theme

If you use Enterprise Portal with SharePoint Server, follow these steps to customize an existing theme.


> [!IMPORTANT]
> <P>This procedure applies only if you use Enterprise Portal with SharePoint Server.</P>



### To customize an existing theme

1.  In Enterprise Portal, use the top-level navigation to open the home page for the module site for which you want to customize a theme.

2.  On the **Site Actions** menu, click **Site Settings**.

3.  In the **Look and Feel** group, click **Site theme**.

4.  Select one of the existing themes that you want to modify.

5.  In the **Customize Theme** group, make the changes that you want to the colors and fonts for the theme.

6.  Click **Preview** to preview the customized theme.

7.  Click **Apply** to apply the customized theme to the site.

## Creating a New Theme

A SharePoint theme is stored in a .thmx file. Several tools are available to create .thmx files. The following procedure uses Microsoft Word 2010 to create a .thmx file that can be applied to an Enterprise Portal site.


> [!IMPORTANT]
> <P>This procedure can be used for both SharePoint Server and SharePoint Foundation.</P>



### To create a new theme

1.  Start Microsoft Word 2010.

2.  On the ribbon, click the **Page Layout** tab.

3.  In the **Themes** group, display the **Colors** menu. Select **Create New Theme Colors**. Select the colors you want to use for the new theme. Provide a name, and then click **Save**.

4.  In the **Themes** group, display the **Fonts** menu. Select **Create New Theme Fonts**. Select the fonts that you want to use for the new theme. Provide a name, and then click **Save**.

5.  In the **Themes** group, display the **Themes** menu. Select **Save Current Theme**.

6.  In the **Save Current Theme** dialog box, provide a name for the new theme. Choose a convenient location for the .thmx file, such as the Desktop, and then click **Save**.

After the .thmx file has been created, you can import it into the SharePoint installation.

### To import a theme

1.  In Enterprise Portal, browse to the main Enterprise Portal site.

2.  On the **Site Actions** menu, click **Site Settings**.

3.  In the **Galleries** group, click **Themes**.

4.  On the ribbon, display the **Documents** tab.

5.  In the **New** group, click **Upload Document**.

6.  Click **Browse**. Select the .thmx file that you created, and then click **Open**.

7.  Click **OK** to upload the new theme.

8.  Verify the name for the theme. You can also provide a description of the new theme. Click **Save**.

To apply the new theme to an Enterprise Portal site, use the procedure that is described in [How to: Apply a SharePoint Theme](how-to-apply-a-sharepoint-theme.md). The new theme you created will appear in the list together with the other SharePoint themes.

