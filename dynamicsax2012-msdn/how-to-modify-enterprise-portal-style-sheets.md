---
title: 'How to: Modify Enterprise Portal Style Sheets'
TOCTitle: 'How to: Modify Enterprise Portal Style Sheets'
ms:assetid: d36381c9-a9e1-405a-9cca-ddecdf36e023
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa872388(v=AX.60)
ms:contentKeyID: 35246146
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Modify Enterprise Portal Style Sheets 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Two sets of cascading style sheets are used to format specific elements that appear in Enterprise Portal and in the Role Center pages for the Microsoft Dynamics AX client. The base versions of these cascading style sheets are found in the **Web** \> **Web Files** \> **Static Files** node of the AOT. During Enterprise Portal installation, the cascading style sheets are deployed from the AOT to the Enterprise Portal server. The following table lists the cascading style sheets that are used to format elements in Enterprise Portal:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Cascading style sheet</p></th>
<th><p>Name in AOT</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AXEP.css</p></td>
<td><p>AXEPv3</p></td>
<td><p>Defines the formatting for all Enterprise Portal components. This is the main cascading style sheet for Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>AXEP_RTL.css</p></td>
<td><p>AXEP_RTL</p></td>
<td><p>Contains the formatting for the items used in right-to-left languages.</p></td>
</tr>
</tbody>
</table>


These style sheets are deployed to the Enterprise Portal installation, and are typically found in the following location:

C:\\Program Files\\Common Files\\Microsoft Shared\\Web Server Extensions\\14\\TEMPLATE\\LAYOUTS\\1033\\STYLES\\Themable

The following table lists the cascading style sheets that are used to format elements for Role Center pages that appear in the Microsoft Dynamics AX client:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Cascading style sheet</p></th>
<th><p>Name in AOT</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AXEP_CRC.css</p></td>
<td><p>AXEP_CRC</p></td>
<td><p>Contains the formatting for the components that appear in the Role Center page in the Microsoft Dynamics AX client.</p></td>
</tr>
<tr class="even">
<td><p>AXEP_CRC_RTL.css</p></td>
<td><p>AXEP_CRC_RTL</p></td>
<td><p>Contains the formatting for the items on the Role Center page in the Microsoft Dynamics AX client that are used in right-to-left languages.</p></td>
</tr>
<tr class="odd">
<td><p>AXEP_WebPart_Padding.css</p></td>
<td><p>AXEP_WebPart_Padding</p></td>
<td><p>Defines the padding for web parts that are displayed on the Role Center page in the Microsoft Dynamics AX client.</p></td>
</tr>
</tbody>
</table>


These style sheets are deployed to the Enterprise Portal installation, and are typically found following location:

C:\\Program Files\\Common Files\\Microsoft Shared\\Web Server Extensions\\14\\TEMPLATE\\LAYOUTS\\EP\\Stylesheets

## Modifying the Enterprise Portal Style Sheets

### To modify the Enterprise Portal style sheets

1.  In the AOT, expand the **Web** \> **Web Files** \> **Static Files** node.

2.  Locate the cascading style sheet that you want to modify (use the names in the previous tables to decide which to modify).

3.  Right-click the cascading style sheet entry, and then click **View Code**.

4.  Make changes to the cascading style sheet.

5.  Close the editor and save the changes.

6.  Right-click the **Static Files** node in the AOT and then click **Deploy**. This will copy the updated style sheet to the Enterprise Portal server.

## Editing the Cascading Style Sheet

Some experimentation is required to find which items in the style sheet you must edit to get the result that you want in Enterprise Portal. For instance, the .dynGridViewSelectedRowTr element controls the appearance of the selected row in an AxGridView component. Use the element names and comments in the cascading style sheet file to find the items that you want to change.

The cascading style sheets contain directives, which appear as comments. When a SharePoint theme is used for an Enterprise Portal site, these directives tell SharePoint how to apply theme colors to the various Enterprise Portal elements. For example, the following code from the AXEP.css file defines the appearance of the selected row in the AxGridView for Enterprise Portal:

    .dynGridViewSelectedRowTr
    {
       margin:0px;
       border:0px;
       /* [ReplaceColor(themeColor:"Dark2",themeTint:"0.35")] */
       border-top:1px solid #68B3FC !important;
       /* [ReplaceColor(themeColor:"Dark2",themeTint:"0.35")] */
       border-bottom:1px solid #68B3FC !important;
       /* [ReplaceColor(themeColor:"Light2")] */
       background-color:#BCE0FE !important;
    }

The CSS code is standard. It specifies characteristics such as the border thickness and the background color. Notice the directives (CSS comments) that appear immediately before several lines in the code. For instance, the following two lines of CSS code define the top border characteristics of the selected row in the AxGridView:

    /* [ReplaceColor(themeColor:"Dark2",themeTint:"0.35")] */
    border-top:1px solid #68B3FC !important;

When the theme that is applied to the SharePoint site is **Default (no theme)**, the directive is ignored. The colors that are defined directly in the CSS file are used. In this example, the top border color for the selected row will be \#68B3FC (a medium blue). When a theme has been specified for the SharePoint site, the directive will be applied. This directive indicates that the top border color for the selected row will be the **Dark2** color from the theme, with a 35% white tint applied. Other characteristics that are defined by the cascading style sheet, such as the border thickness, are always applied, regardless of whether a theme has been specified.


> [!NOTE]
> <P>You should have little reason to change the SharePoint directives that you find in the cascading style sheet files. The directives that are added to the files are designed to give Enterprise Portal the best possible appearance for any SharePoint theme that you choose.</P>


