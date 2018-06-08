---
title: 'How to: Connect User Controls with other User Controls'
TOCTitle: 'How to: Connect User Controls with other User Controls'
ms:assetid: dfcdcd13-81b7-4ad8-b4de-d3cca4649cc7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc622007(v=AX.60)
ms:contentKeyID: 35246160
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Connect User Controls with other User Controls 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A page in Enterprise Portal can contain multiple web parts that display related data. For instance, when a user selects a record in an AxGridView, a corresponding record could be displayed in an AxForm control. To make this work, web part communication must be set up between the two User Controls. One User Control will act at the publisher, while the other User Control will act as the subscriber. An AxContextList will be passed from the publishing web part to the subscribing web part.

For Web part communication to work properly, you must have extended data types set up for the key fields that will be used for the AxContextList. The extended data types must have table references defined that link the field to its corresponding table.

For example, the RoomNum field is an extended data type that has a relationship defined to the FCMRooms table. This relationship is required so that the RoomNum field can be used in the AxContextList. For more information, see [How to: Create an Extended Data Type](how-to-create-an-extended-data-type.md).

## Configuring Dynamics User Controls for Publishing

For a Dynamics User Control to be used as a publisher for Web part communication, the components in the User Control must be set up properly. The data fields for the key used to access data from the AxDataSource component must be specified so that the AxContextList will contain the appropriate values.

### To configure Dynamics User Controls for publishing

1.  In the Visual Studio project for the User Controls, locate the User Control that will be publishing the AxContextList. For example, an AxGridView component can publish the AxContextList that contains the key values for the item selected in the grid.

2.  Set the **DataKeyNames** property for this component to contain the key fields that uniquely identify the record being published. Click the lookup button for the **DataKeyNames** property to use the **Data Fields Collection Editor** window to select the fields.

3.  Save the changes for the User Control.

## Configuring Dynamics User Controls for Subscribing

For a Dynamics User Control to be used as a subscriber for Web part communication, the components in the User Control must be set up properly. The data fields for the key used to access data from the AxDataSource component must be specified so that the AxContextList will contain the appropriate values.

### To configure Dynamics User Controls for subscribing

1.  In the Visual Studio project for the User Controls, locate the User Control that will be subscribing to the AxContextList. For example, an AxForm component can subscribe to the AxContextList that contains the key values for the item selected in an AxGridView.

2.  Set the **DataKeyNames** property for this component to contain the key fields that uniquely identify the record being subscribed to. Click the lookup button for the **DataKeyNames** property to use the **Data Fields Collection Editor** window to select the fields.

3.  Set the **DataMember** property to indicate how the AxDataSource component for the subscribing User Control component will be set. Typically, this will be set to **\_Current**. This causes the context information passed by AxContextList to be used to indicate the record to display

4.  Save the changes for the User Control.

## Connecting the Web Parts

When the Dynamics User Control Web parts are added to the page, they can be connected for Web part communication. For more information about adding Web parts to a page, see [How to: Add Web Parts](how-to-add-web-parts.md).

### To connect Web parts

1.  In Enterprise Portal, display the page that contains the Dynamics User Control Web parts that you want to connect.

2.  In the **Site Actions** menu, click **Edit Page**.

3.  In the **Edit** menu for the Dynamics User Control Web part that will be publishing, click **Connections**. Click **Send AxContextListTo**, and then click the Dynamics User Control Web part that you want to connect to.
    
    \-or-
    
    In the **Edit** menu for the Dynamics User Control Web part that will be subscribing, click **Connections**. Click **Get AxContextListFrom**, and then click the Dynamics User Control Web part that you want to connect to.
    

    > [!IMPORTANT]
    > <P>If the connection is not available, verify that the <STRONG>Web part role</STRONG> property for the Dynamics User Control that is publishing is set to <STRONG>Provider</STRONG>. Be sure that the property for the Dynamics User Control that is subscribing is set to <STRONG>Consumer</STRONG>.</P>



4.  To save, click **Exit Edit Mode**.

5.  If you will be distributing the Web part modifications to other Enterprise Portal installations, import the updated page into the AOT. For more information, see [How to: Import Pages into the AOT](how-to-import-pages-into-the-aot.md).

