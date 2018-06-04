---
title: Working with Data for Enterprise Portal
TOCTitle: Working with Data for Enterprise Portal
ms:assetid: f7108d37-f26b-4ced-9d4e-08a87cff5ce4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc624200(v=AX.60)
ms:contentKeyID: 28119524
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Working with Data for Enterprise Portal 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The code you add for User Controls will often be required to work with data for Enterprise Portal. Several techniques can be used to access data for Enterprise Portal. These are:

  - .NET Business Connector

  - Proxy

  - Data Sets and AxDataSource

Which you choose depends on the specific requirements for the User Control you are creating.

## .NET Business Connector

Code for User Controls can access data through the .NET Business Connector interface provided by the Managed Interop Layer (MIL) of Microsoft Dynamics AX. To access the .NET Business Connector, you must include the following using statements to reference the appropriate namespaces.

``` csharp
using Microsoft.Dynamics.Framework.BusinessConnector.Session;
using Microsoft.Dynamics.Framework.BusinessConnector.Adapter;
```

You must also use the Session object to connect to data through the .NET Business Connector interface. This object is described in [Session Object](session-object.md). For details about how to use the .NET Business Connector to access data, see [.NET Business Connector Overview](net-business-connector-overview.md).

The following example shows how to use the .NET Business Connector from code for a User Control. This example tries to retrieve all of the rows for items from the InventTable table in Microsoft Dynamics AX. For the rows successfully retrieved, the item’s alias is added to the ItemListBox listbox field for the User Control. Notice that the Session object is used to connect to the .NET Business Connector. No separate logon action is needed.

``` csharp
IAxaptaRecordAdapter axRecord;

using (axRecord = AxSession.AxaptaAdapter.CreateAxaptaRecord("InventTable"))
{
    // Try to retrieve a list of the items.
    axRecord.ExecuteStmt("select * from %1 where %1.ItemType==0");

    // Clear all of the items from the listbox.
    ItemListBox.Items.Clear();

    while (axRecord.Found)
    {
        // Add each item to the listbox.
        ItemListBox.Items.Add(axRecord.GetField("NameAlias").ToString());
        axRecord.Next();
    }
}
```


> [!IMPORTANT]
> <P>Notice that a using block encloses the code that works with the IAxaptaRecordAdapter. Use this pattern to make sure that the resources for the IAxaptaRecordAdapter will be freed when it goes out of scope.</P>



## Proxy

If you have X++ code that performs data access needed by the User Control you are creating, you may want to use the proxy to access that code. For details about how to use a proxy with Enterprise Portal, see [Proxies](proxies.md).

## Data Sets and AxDataSource

Much of the data displayed in Enterprise Portal is accessed through data set resources defined in the AOT. For more information about data sets, see [Data Sets for Enterprise Portal](data-sets-for-enterprise-portal.md). AxDataSource components added to the layout for User Controls are used to access data sets. Other User Control components such as the AxGridView and AxForm access data through the AxDataSource components. Code you add for User Controls can also access data through the AxDataSource components. To use the classes and methods that are required to work with AxDataSource components, add the following using statement to your User Control code.

``` csharp
using Microsoft.Dynamics.AX.Framework.Portal.Data;
```

### Returning the Views for an AxDataSource

A data set can have several views. Usually, these views correspond to the tables that are used to create the data set. Each data source for the data set has two views. One view represents all the rows that can be accessed through the view. The other view represents the current row, and has a name that ends with the string \_Current.

The following example shows how to retrieve the views for the HcmWorkerDS AxDataSource component. The views are added to a list when the user clicks the button.

``` csharp
protected void GetViews_Click(object sender, EventArgs e)
{
    // Clear the list of views.
    Views_ListBox.Items.Clear();

    // Get the data set
    DataSet ds = HcmWorkerDS.GetDataSet();

    // Add the views for the data set to the list.
    foreach (DataSetView dsv in ds.DataSetViews)
    {
        Views_ListBox.Items.Add(dsv.Name);
    }
}
```

### Returning the Current Row for an AxDataSource

In code for User Controls, you may want to access the current row for an AxDataSource. The current row is often set by the component linked to the AxDataSource, such as an AxGridView. The following example is a function that retrieves the current row from the HcmWorkerDS data source, which is accessing the HcmEPWorker data set. The view named HcmWorker is used to access the data source.

``` csharp
private DataSetViewRow CurrentRow
{
    get
    {
        try
        {
            DataSetView dataSetView;
            dataSetView = this.HcmWorkerDS.GetDataSet().DataSetViews["HcmWorker"];
            return (dataSetView == null) ? null : dataSetView.GetCurrent();
        }
        catch (System.Exception)
        {
            return null;
        }
    }
}
```

### Getting and Setting Field Values for a Row

To get or set the values for fields in a row, use the GetFieldValue or SetFieldValue methods for the DataSetViewRow object. The following example retrieves the value of the name\*\* field for the current row in the HcmWorkerDS data source.

``` csharp
DataSetViewRow row;
string name;

// Retrieve the current row.
row = HcmWorkerDS.GetDataSet().DataSetViews["HcmWorker"].GetCurrent();

// Retrieve the name** value.
name = row.GetFieldValue("name**").ToString();
```

The following code edits the current row in the HcmWorkerDS data source. The value of the PersonnelNumber field is set, and then the changes to the row are saved.

``` csharp
DataSetViewRow row;

try
{
    // Retrieve the current row.
    row = HcmWorkerDS.GetDataSet().DataSetViews["HcmWorker"].GetCurrent();

    // Edit the row and change the PersonnelNumber value.
    row.BeginEdit();
    row.SetFieldValue("PersonnelNumber", "987");
    row.EndEdit();
}
catch (System.Exception ex)
{
    AxExceptionCategory exceptionCategory;

    // Determine whether the exception can be handled.
    if (AxControlExceptionHandler.TryHandleException(this, ex, out exceptionCategory) == false)
    {
        // The exception was fatal and cannot be handled. Rethrow it.
        throw;
    }
}
```

### Working with a Table Hierarchy

When the tables accessed by a data set are part of a table hierarchy, you need to qualify the names of the fields that you are getting or setting in a row. For example, the following illustration shows the table hierarchy for room information in the Facility Management sample application. It consists of the base table FCMRooms, plus two tables that are derived from the base table.

![Rooms table hierarchy](images/Cc624200.EP_RoomTableHierarchy(AX.60).gif "Rooms table hierarchy")

The base table, FCMRooms, would typically be used as the main table for the data set. To access fields from one of the derived tables, the field name must be qualified to indicate its location in the table hierarchy. For instance, to access the AssignedToRecId field, which is part of the FCMPrivateRooms table, you would use the following name:

FCMRooms\_FCMPrivateRooms\!AssignedToRecId

Notice that the name begins with the base table, then the derived table, and finally an exclamation point followed by the field name.


> [!TIP]
> <P>To see the fully-qualified name for a field that is part of a table hierarchy, you can look at the field list for the data set in the <STRONG>Bound Field Designer</STRONG> in Visual Studio.</P>



The following C\# code example shows how the field value in the previous example would be retrieved.

``` csharp
DataSetViewRow row;
string recId;

// Retrieve the current row from the data set.
row = RoomsDS.GetDataSet().DataSetViews["FCMRooms"].GetCurrent();

// Retrieve the record ID for the employee assigned to the room.
recId = row.GetFieldValue("FCMRooms_FCMPrivateRooms!AssignedToRecId").ToString();
```

### Custom Data Set for a Lookup

When adding a lookup component to a User Control, you may want to access data for which no data set has been defined in the AOT. You can use C\# code to create a custom data set for the lookup. For an example of this, see [Lookups](lookups.md).

