---
title: 'How to: Add Methods to Data Sets'
TOCTitle: 'How to: Add Methods to Data Sets'
ms:assetid: 27d6b70d-6226-4a0c-9b62-0fc0d4ce648d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee677497(v=AX.60)
ms:contentKeyID: 35245117
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Add Methods to Data Sets 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can add X++ methods to data sets and then call these methods from User Controls in Enterprise Portal. Typically, these data set methods perform actions on the data set, such as setting a range.

## Adding a Method to a Data Set

### To add a method to a data set

1.  In the AOT, expand the **Data Sets** node.

2.  Expand the node for the data set that you want to add a method to.

3.  Right-click the **Methods** node and then click **New Method**.

4.  Specify the name of the method.

5.  Add the X++ code to the method.

6.  Save the method.

7.  Save the changes that you made to the data set.

## Calling a Data Set Method from a User Control

To call a data set method from the C\# code for a User Control, you must add the following using statement to provide access to the data set:

using Microsoft.Dynamics.AX.Framework.Portal.Data;

In the desired location in the code for your User Control, add a statement to call the data set method. This statement retrieves the data source for the User Control, accesses the data set for the data source, and then calls the data set method by name. You can pass parameters to the data set method if they are required. The following C\# example shows the basic syntax of this statement:

this.AxDataSource1.GetDataSet().DataSetRun.AxaptaObjectAdapter.Call("DataSetMethod");

## Example

The following example is an X++ method named MyWorkOrders that was added to the FCMWorkOrderList data set for the Facility Management sample application. This method clears any existing range for the data set, and then applies a new range that limits the data accessed to include the work orders for only the current worker.
```X++  
    void MyWorkOrders()
    {
        QueryBuildDataSource qbds;
        QueryBuildRange qbr;
        
        // Retrieve the data source.
        qbds = FCMWorkOrders_q.dataSourceName(FCMWorkOrders_ds.name());
        
        // Clear the existing range.
        qbds.clearRange(fieldNum(FCMWorkOrders,RequesterRecId));
        
        // Add a new range to show the current worker's work orders.
        qbr = qbds.addRange(fieldNum(FCMWorkOrders,RequesterRecId));
        qbr.value(queryValue(SysQueryRangeUtil::currentWorkerRecId()));
        qbr.status(RangeStatus::Open);
        FCMWorkOrders_ds.executeQuery();
    }
```
A standard ASP.NET button was added to the WorkOrderList User Control. The following using statement was added to the C\# code for the User Control:

using Microsoft.Dynamics.AX.Framework.Portal.Data;

The following C\# code was added to the Click event for the button. The code calls the “MyWorkOrders” method on the data set. When the button is clicked, the range is applied that limits the records displayed to only those created by the current worker.

``` csharp
protected void Button1_Click(object sender, EventArgs e)
{
    this.WorkOrderListDataSource.GetDataSet().DataSetRun.AxaptaObjectAdapter.Call("MyWorkOrders");
}
```

## See also

[How to: Add Code to User Controls](how-to-add-code-to-user-controls.md)

