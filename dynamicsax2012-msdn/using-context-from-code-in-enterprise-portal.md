---
title: Using Context from Code in Enterprise Portal
TOCTitle: Using Context from Code in Enterprise Portal
ms:assetid: 8289de7c-631f-42a7-9a96-9b2ad701f84d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee330227(v=AX.60)
ms:contentKeyID: 35589411
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Using Context from Code in Enterprise Portal 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You may want to access the context information from within the code for a User Control. The following sections describe three common scenarios.

## Retrieving Context

You can retrieve the context for a web part in the Page\_Load event for the User Control. The following C\# code for a User Control accesses the current row in the table indicated by the context information passed to the web part. The Description field is returned from the current row.

``` csharp
protected void Page_Load(object sender, EventArgs e)
{
    IAxaptaRecordAdapter currentRecord = AxBaseWebPart.GetWebpart(this).ExternalRecord;
    if (currentRecord != null)
    {
        String description = currentRecord.GetField("Description").ToString();
    }
}
```


> [!TIP]
> <P>To access the IAxaptaRecordAdapter type, you must include a reference to the Microsoft.Dynamics.Framework.BusinessConnector.Adapter namespace.</P>



## Registering for a Context Changed Event

You may also want to register an event so that your code is notified every time the context passed to the web part changes. You can register for this event in the Page\_Load event for the User Control. The following C\# example shows the registration for this event.

``` csharp
protected void Page_Load(object sender, EventArgs e)
{
    AxBaseWebPart.GetWebpart(this).ExternalContextChanged 
        += new EventHandler<AxExternalContextChangedEventArgs>(RoomDetails_ExternalContextChanged);
}
```

The following C\# example shows the event handler for this event. Every time the context passed to the web part changes, the event handler will retrieve the current record based on the context and update the value of a label.

``` csharp
void RoomDetails_ExternalContextChanged(object sender, AxExternalContextChangedEventArgs e)
{
    IAxaptaRecordAdapter currentRecord = AxBaseWebPart.GetWebpart(this).ExternalRecord;
    if (currentRecord != null)
    {
        Label1.Text = currentRecord.GetField("RoomName").ToString();
    }
}
```

## Creating a Menu Item that has Context

Another action you may want to do is to create a menu item that has context that can be passed to a new page that is being displayed in Enterprise Portal. The following C\# example retrieves the current row from the FCMRooms data set. The record ID for the worker assigned to the room is retrieved. A URL menu item that opens the HcmEPMyEmployeeInfo page is created. To show the data for the worker assigned to the room, the URL menu item includes context information based on the record ID that was retrieved. This example requires references to the following namespaces:

  - Microsoft.Dynamics.AX.Framework.Portal.Data

  - Microsoft.Dynamics.Framework.Portal.UI

  - Microsoft.Dynamics.Framework.Portal.UI.WebControls

  - Microsoft.Dynamics.Framework.Portal.CommonControls

The context passed allows the information for the worker from the current row in the FCMRooms data set to be displayed in the page being opened.

``` csharp
DataSetViewRow row;
AxUrlMenuItem menuItem;
string recId;

// Retrieve the current row from the data set.
row = RoomsDS.GetDataSet().DataSetViews["FCMRooms"].GetCurrent();

try
{
    // Retrieve the record ID for the employee assigned to the room.
    // This field is included in the FCMPrivateRooms table, which is part of
    // the table hierarchy.
    recId = row.GetFieldValue("FCMRooms_FCMPrivateRooms!AssignedToRecId").ToString();

    if (recId != "0")
    {
        // Use the CreateMenuItemWithTableContext helper to create a menu item
        // with context that indicates the record to display from the HcmWorker table.
        // HcmEPMyEmployeeInfo is the web menu item that indicates the page to be accessed.
        menuItem = ControlHelper.CreateMenuItemWithTableContext("HcmWorker", "RecId", recId, "HcmEPMyEmployeeInfo");

        // Display the page indicated, passing the context.
        Response.Redirect(menuItem.Url.OriginalString);
    }
    else
    {
        Proxy.Info objInfoLog = new Proxy.Info(this.AxSession.AxaptaAdapter);
        objInfoLog.add(Proxy.Exception.Info, "Room is not assigned.");
    }
}
catch (Exception ex)
{
    Proxy.Info objInfoLog = new Proxy.Info(this.AxSession.AxaptaAdapter);
    objInfoLog.add(Proxy.Exception.Info, "Room information is not available.");
} 
```

