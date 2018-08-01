---
title: Using Menu Items
TOCTitle: Using Menu Items
ms:assetid: f25a9822-c5c5-4bee-b24e-02447eb2c020
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh830904(v=AX.60)
ms:contentKeyID: 45260824
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Using Menu Items [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In the AOT, you can define two types of web menu items: URL and action. Use the AxUrlMenuItem and AxActionMenuItem objects to access web menu items in code for a User Control.

## AxUrlMenuItem

The AxUrlMenuItem is typically used to display a specific page as defined in the **Web** \> **Web Menu Items** \> **URLs** node of the AOT. For example, the following code is attached to a button in a User Control. When the user clicks the button, the code retrieves the URL web menu item that points to the WorkOrdersList page. It then displays that page in Enterprise Portal.

``` csharp
protected void ShowList_Click(object sender, EventArgs e)
{
    // Retrieve the URL Web Menu Item for the Work Orders List.
    AxUrlMenuItem menuItem = new AxUrlMenuItem("WorkOrdersList");
    
    // Display the page that the URL Web Menu Item points to.
    Response.Redirect(menuItem.Url.ToString());
}
```

If necessary, you can set the MenuItemContext property for the AxUrlMenuItem to define the context that is passed with the menu item. For example, the following code creates an AxTableDataKey object that points to the first row that is marked in an AxGridView for a User Control. The key information is used to create an AxTableContext object, which supplies the context for the AxUrlMenuItem. When the user clicks the button, the Work Order Details page is opened, displaying the record that is specified by the context.

``` csharp
protected void ViewSelectedRow_Click(object sender, EventArgs e)
{
    // Create the URL Web Menu Item for the Work Order Details page.
    AxUrlMenuItem menuItem = new AxUrlMenuItem("WorkOrderDetails");

    // Get the number of the FCMRooms table.
    // The metadata objects are accessed from the Microsoft.Dynamics.AX.Framework.Services.Client namespace.
    int FCMRoomTableNum;
    FCMRoomTableNum = TableMetadata.TableNum("FCMRooms");

    // Get the key value from the current row of the grid.
    string keyvalue = AxDataSource1.GetDataSourceView("FCMRooms").GetCurrentRecordDataSourceView().GetCurrentTableRowKey("FCMRooms").ToWKEY();

    // Create the table key.
    AxTableDataKey key = AxTableDataKey.Create(AxSession, FCMRoomTableNum, keyvalue);

    // Set the context value for the URL.
    menuItem.MenuItemContext = AxTableContext.Create(key);

    // Display the page that the URL Web Menu Item points to, passing the context.
    Response.Redirect(menuItem.Url.ToString());
}
```

## AxActionMenuItem

The AxActionMenuItem is used to perform actions that are defined in the **Web** \> **Web Menu Items** \> **Actions** node of the AOT. The following example uses an AxActionMenuItem to perform the action that flushes the AOD. This example uses the Business Connector proxy, which requires the following using statement:

using Proxy = Microsoft.Dynamics.Framework.BusinessConnector.Proxy;

The following code creates the action menu item and performs the SysFlushAOD action.

``` csharp
protected void FlushAOD_Click(object sender, EventArgs e)
{
    AxActionMenuItem menuItem = new AxActionMenuItem("SysFlushAOD");

    // Get the Proxy and Args for the .NET Business Connector.
    using (Proxy.Args args = new Proxy.Args(AxSession.AxaptaAdapter))
    {
        // Perform the action.
        menuItem.Run(args);
    }
}
```

