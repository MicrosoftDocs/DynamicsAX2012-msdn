---
title: 'How to: Connect User Controls to Action Panes or Toolbars'
TOCTitle: 'How to: Connect User Controls to Action Panes or Toolbars'
ms:assetid: 3a2b6efe-74ad-4b0b-aef7-6e2edabf6ca6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc596894(v=AX.60)
ms:contentKeyID: 35245201
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Connect User Controls to Action Panes or Toolbars 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Some pages in Enterprise Portal contain an [Action Pane Web Part](action-pane-web-part.md) or [Toolbar Web Part](toolbar-web-part.md) that is used to perform actions on an item that the user has selected or displayed in a [User Control Web Part](user-control-web-part.md) web part. The web parts use web part communication to pass an AxContextList. The AxContextList contains the information about the item currently selected or displayed in the User Control web part. The context information is passed to the Action Pane web part or Toolbar web part to indicate what data should be displayed or acted on. The Action Pane web part or Toolbar web part passes the context information to the page that is opened when the user chooses a command from the action pane or toolbar.

When you use an extended data type as a key for your table, the key fields will be used for the AxContextList. The extended data types must have table references defined that link the field to its corresponding table.

For example, the WorkOrderNum field is an extended data type that has a relationship defined to the FCMWorkOrders table. This relationship is required so that the WorkOrderNum field can be used in the AxContextList. For more information, see [How to: Create an Extended Data Type](how-to-create-an-extended-data-type.md).

## Configuring User Controls for Publishing

For a User Control to be used with web part communication, the components in the User Control must be set up properly. The data fields for the key used to access data from the AxDataSource component must be specified so that the AxContextList will contain the appropriate values.

### To configure User Controls for publishing

1.  In the Visual Studio project for the User Controls, locate the User Control that will be publishing the AxContextList. For example, an AxGridView component can publish the AxContextList that contains the key values for the item selected in the grid.

2.  Set the **DataKeyNames** property for this component to contain the key fields that uniquely identify the record being published. Click the lookup button for the **DataKeyNames** property to use the **Data Fields Collection Editor** window to select the fields.

3.  Save the changes for the User Control.

## Connecting the Web Parts

When the User Control, Action Pane, and Toolbar web parts are added to the page, they can be connected for web part communication. For more information about adding web parts to a page, see [How to: Add Web Parts](how-to-add-web-parts.md).

### To connect web parts

1.  In Enterprise Portal, display the page that contains the User Control, Action Pane, and Toolbar web parts that you want to connect.

2.  In the **Site Actions** menu, click **Edit Page**.

3.  In the **Edit** menu for the User Control web part, click **Connections**. Click **Send AxContextListTo**, and then click the Action Pane web part or Toolbar web part that you want to connect to.
    
    \-or-
    
    In the **Edit** menu for the Action Pane web part or Toolbar web part, click **Connections**. Click **Get AxContextListFrom**, and then click the User Control web part that you want to connect to.
    

    > [!IMPORTANT]
    > <P>If the connection is not available, verify the <STRONG>Web part role</STRONG> property for the User Control is set to <STRONG>Provider</STRONG>.</P>



4.  To save changes, click **Stop Editing**.

5.  If you will be distributing the web part modifications to other Enterprise Portal installations, import the updated page into the AOT. For more information, see [How to: Import Pages into the AOT](how-to-import-pages-into-the-aot.md).

## Configuring User Control for Subscribing

A User Control can be configured to respond to an AxContextList that is passed to the page being opened by choosing an item in the Action Pane or the Toolbar.

### To configure User Controls for subscribing

1.  In the Visual Studio project for the User Controls, locate the User Control that will be subscribing to the AxContextList. For example, an AxForm component can use the AxContextList that is passed to the new page when the user chooses an Action Pane or Toolbar item.

2.  Set the **DataKeyNames** property for this component to contain the key fields that are being passed in from the AxContextList. Click the lookup button for the **DataKeyNames** property to use the **Data Fields Collection Editor** window to select the fields. The fields you select for the key must be the same set of fields that is passed from the publishing web part. These key fields will be used by the AxDataSource component to access data.

3.  Save the changes for the User Control.

When you add the User Control web part to the page that will respond to the AxContextList, be sure the **Web part role** property is set to Provider. This may not seem logical, since the web part is consuming the AxContextList that was passed to the page. Remember that the **Web part role** property specifies what role the web part has for communication on the page. By setting the property to Provider, the web part will receive the AxContextList passed to the page, and then make it available to other web parts on the page.

## Viewing the Values the AxContextList

When an Action Pane web part or a Toolbar web part is used to pass an AxContextList to another page, the values are passed as parameters of the URL that opens the new page. For security reasons, these parameters are encrypted to prevent users from seeing the values that were passed.

When setting up web part communication for an Action Pane web part or a Toolbar web part, it can be helpful to see the values that are passed to the new page being opened. To do this, you must turn off the encryption for the Enterprise Portal site.


> [!WARNING]
> <P>Turn off encryption only when troubleshooting web part communication. Do not turn off encryption in a production Enterprise Portal installation.</P>



### To view the values for the AxContextList

1.  In the Microsoft Dynamics AX client, display the **System Administration** area page. In the **Setup** group, expand **Enterprise Portal**. Click **Web sites**.

2.  In the **Administration of Web sites** window, display the **General** tab.

3.  Make sure that **Enable encryption** checkbox is cleared. Click **Close**.

4.  If necessary, reset IIS for the change to take effect.

The following is a portion of the URL that displays the Work Order Details page when an item is chosen from a Toolbar web part. Notice that the values are encrypted.

…/WorkOrderDetails.aspx?mode=0\&WMI=WorkOrderDetails\&WTID=50002\&WKEY=\[65534:5637144581\]\&WCMP=CEU\&WHPV=7CBDD5030AC436E13FFB4FF4D8094F26AE1E98DA1C4D74AF00762508C3C6411A\&IsDlg=1

The following is a portion of this same URL when encryption is turned off for the site. Notice that the key values passed through the AxContextList can be seen in the URL.

…/WorkOrderDetails.aspx?mode=0\&WMI=WorkOrderDetails\&WTID=50002\&WKEY=\[65534:5637144581\]\&WCMP=CEU\&IsDlg=1

