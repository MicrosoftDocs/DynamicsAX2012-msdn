---
title: Lookups
TOCTitle: Lookups
ms:assetid: f34776ba-3ac4-4b85-84f3-03b5c215dfd9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc623636(v=AX.60)
ms:contentKeyID: 28119514
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- xml
- csharp
---

# Lookups [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Several techniques can be used to create lookups for non-bound fields (fields that do not come from an AxDataSource). The simplest do not require any code to be added. More complex lookups have code that defines the lookup content. In some cases, the code is added to the page markup. In other cases, it is added to the code-behind file for the User Control.

## Lookup Based on an Extended Data Type

The simplest lookup is based on an extended data type. Set the **LookupType** property for the lookup control to EDT. Set the **ExtendedDataType** property to the extended data type that will specify the lookup content. The columns displayed in the lookup will come from the **TitleField1** and **TitleField2** properties of the table associated with the extended data type.

If you want to specify which fields are contained in the lookup, you can do this in the markup for the lookup control. You can include fields that are part of the table associated with the extended data type. In the markup for the lookup control, add a \<Fields\> group that specifies which fields you want to include. The following example shows the markup for the lookup WorkOrdersLookup. It specifies that three fields are to be displayed in the lookup.

``` xml
<dynamics:AxLookup ID="WorkOrdersLookup" runat="server" TargetControlId="WorkOrder1" 
    ExtendedDataType="WorkOrderNum" LookupType="EDT">
        <Fields>
            <dynamics:AxBoundField DataField="WorkOrderNum" SortExpression="WorkOrderNum" />
            <dynamics:AxBoundField DataField="RequestDate" SortExpression="RequestDate" />
            <dynamics:AxBoundField DataField="Details" SortExpression="Details" />
        </Fields>
</dynamics:AxLookup>
```

Instead of specifying the fields directly in the markup, you could specify them in the code-behind for the lookup control. Add the handler for the Lookup event for the control. For information about adding an event handler, see [User Control Events](user-control-events.md). In this event handler, specify the fields that will appear in the lookup. The following example shows how the Lookup event handler is used to specify the fields that appear in the lookup.

``` csharp
protected void WorkOrdersLookup_Lookup(object sender, AxLookupEventArgs e)
{
    AxLookup lookup = (AxLookup)sender;

    // Specify the lookup fields.
    lookup.Fields.Add(AxBoundFieldFactory.Create(AxSession, lookup.LookupDataSetViewMetadata.ViewFields["WorkOrderNum"]));
    lookup.Fields.Add(AxBoundFieldFactory.Create(AxSession, lookup.LookupDataSetViewMetadata.ViewFields["RequestDate"]));
    lookup.Fields.Add(AxBoundFieldFactory.Create(AxSession, lookup.LookupDataSetViewMetadata.ViewFields["Details"]));
}
```

## Lookup Based on a Data Set

A lookup can be based on a data set that has been defined in the AOT. To do this, set the **LookupType** property for the lookup control to DataSetField. Set the **DataSet** property to the name of the data set that contains the content to use for the lookup. Set the **DataSetView** property to a view from the data set that contains the fields you want to use for the lookup. Set the **DataLookupField** property to the field from the data set view that you want returned from the lookup.

## Lookup Based on Custom Data Set

A lookup can be based on a custom data set that is created in code. To do this, set the **LookupType** property for the lookup control to CustomDataSet.

Items from several namespaces must be available to create the data set for the lookup. The following using statements add the required namespaces.

``` csharp
using Proxy = Microsoft.Dynamics.Framework.BusinessConnector.Proxy;
using Microsoft.Dynamics.AX.Framework.Portal.Data;
using Microsoft.Dynamics.AX.Framework.Services.Client;
```

Add the handler for the Lookup event for the control. The following example shows how the Lookup event handler is used to create a data set dynamically based on a table. Then the data set is used for the lookup.

``` csharp
protected void WorkOrdersLookup_Lookup(object sender, AxLookupEventArgs e)
{
    AxLookup lookup = (AxLookup)sender;

    // Create the lookup data set. The Work Orders table will be used.
    Proxy.SysDataSetBuilder sysDataSetBuilder;
    sysDataSetBuilder = Proxy.SysDataSetBuilder.constructLookupDataSet(AxSession.AxaptaAdapter, TableMetadata.TableNum(AxSession, "FCMWorkOrders"));

    // Set the generated data set as the lookup data set.
    lookup.LookupDataSet = new DataSet(AxSession, sysDataSetBuilder.toDataSet());

    // Specify the fields for the lookup.
    lookup.Fields.Add(AxBoundFieldFactory.Create(AxSession, lookup.LookupDataSetViewMetadata.ViewFields["WorkOrderNum"]));
    lookup.Fields.Add(AxBoundFieldFactory.Create(AxSession, lookup.LookupDataSetViewMetadata.ViewFields["Details"]));
    lookup.Fields.Add(AxBoundFieldFactory.Create(AxSession, lookup.LookupDataSetViewMetadata.ViewFields["RequestDate"]));

    // Specify the select field for the lookup.
    lookup.SelectField = "WorkOrderNum";

}
```

## Lookup Based on a User Control in the AOT

The content of a lookup can be defined by a User Control that has been added to the AOT. For example, you could create a User Control that uses the AxGridView component to define the contents of the lookup. The value returned by the lookup is based on the row selected in the AxGridView. The markup for the lookup control is edited to reference the managed content item.

``` xml
<dynamics:AxLookup ID="WorkOrdersLookup" runat="server" LookupType="Custom" TargetControlId="WorkOrder1" PredefinedButtons="Ok">
    <ContentTemplate>
        <dynamics:AxContentPanel ID="AxContentPanel1" runat="server" ManagedContentItem="WorkOrderList" />
    </ContentTemplate>
</dynamics:AxLookup>
```

The User Control that is being used as a lookup must contain code that specifies the characteristics of the lookup. This code must also specify what value is returned from the lookup. Events registered by the User Control are used to do this. Since the User Control can also be used in a standard web part, this code must be run only when the control is being used as a lookup.

The following example is the Page\_Init() method for a User Control that can be used in a lookup. The code determines whether the control is being used within a lookup. If it is, the characteristics of the lookup are set and the events for the lookup are registered.

``` csharp
void Page_Init(object sender, EventArgs e)
{
    // Determine whether the control is being used in a lookup.
    AxLookup lookupControl = AxLookup.GetLookup(this);
    if (lookupControl != null)
    {
        // It is a lookup, so set properties and register events.
        this.WorkOrdersGridView.ShowContextMenu = false;
        this.WorkOrdersGridView.ShowFilter = false;
        this. WorkOrdersGridView.AllowGrouping = false;

        // Register the events to handle.
        lookupControl.OkClicked += new EventHandler<AxLookupEventArgs>(lookupControl_OkClicked);
        lookupControl.Lookup += new EventHandler<AxLookupEventArgs>(lookupControl_Lookup);
    }
}
```

The following examples are the event handlers for the events that were registered for the lookup in the previous example. The Lookup event specifies what is selected in the lookup when it is displayed. The OkClicked event specifies what value is returned from the lookup when OK is clicked.

``` csharp
void lookupControl_Lookup(object sender, AxLookupEventArgs e)
{
    // Display the lookup contents and select the first row.
    this.WorkOrdersGridView.DataBind();
    this.WorkOrdersGridView.SelectedIndex = 0;
}

void lookupControl_OkClicked(object sender, AxLookupEventArgs e)
{
    DataSetViewRow currentRow;

    // Get the current row in the data source used for the control.
    currentRow = this.WorkOrderListDataSource.GetDataSourceView(this.WorkOrdersGridView.DataMember).DataSetView.GetCurrent();
    if (currentRow != null)
    {
        e.LookupControl.TargetITextControl.Text = (string)currentRow.GetFieldValue("WorkOrderNum");
    }
}
```

## Multi-select Lookups

When you set the **AllowMarking** property to true for an AxLookup component, the user can mark multiple rows in the lookup. You can access the rows that have been marked by examining the data set for the lookup.

The following example is the event handler for the OkClicked event for the Work Order lookup. In this event, the GetMarkedRowsSet() method retrieves the set of rows that the user marked in the lookup. The Work Order Number field is read from each row in the set and assembled into a string that is displayed in a text box.

``` csharp
protected void WorkOrderLookup_OkClicked(object sender, AxLookupEventArgs e)
{
    string retval = "";
        
    // Look at each value returned from the multi-select lookup
    foreach (DataSetViewRow row in e.LookupControl.LookupDataSetView.GetMarkedRowsSet())
    {
        // Retrieve the Work Order Number from the current marked row
        retval = retval + row.GetFieldValue("WorkOrderNum").ToString() + " - ";
    }

    // Display the results in a text box
    WorkOrder1.Text = retval;
}
```

