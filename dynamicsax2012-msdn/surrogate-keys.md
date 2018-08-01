---
title: Surrogate Keys
TOCTitle: Surrogate Keys
ms:assetid: fedb0c16-dc77-45d1-83ba-c40baf8deffd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh330357(v=AX.60)
ms:contentKeyID: 36806170
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Surrogate Keys [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

If you store surrogate foreign key values in your tables, you will have to correctly work with these values in your Enterprise Portal integration. This involves creating a reference data source to link to the data that is accessed by the surrogate foreign key. It can also include using the AxReferenceField to access the surrogate foreign key value.

## Reference Data Sources

A reference data source supplies the data values that are accessed through a surrogate foreign key. A reference data source appears as a child node of the data source that is used for a data set, and is found in the **Reference Data Sources** node. On your data set, you must create the reference data source before a User Control can use the data that is accessed through the surrogate foreign key.

### To create a reference data source

1.  In the AOT, expand the **Data Sets** node.

2.  Expand the node for the data set that you want to add a reference data source for.

3.  Expand the **Data Sources** node.

4.  Expand the data source for the table that contains the surrogate foreign keys that you want to access data for.

5.  Right-click the **Reference Data Sources** node, and then click **New Reference Data Source**.

6.  Right-click the new reference data source, and then click **Properties**.

7.  Set the **Name** property to specify the name of the reference data source. Use a name that describes the type of data being accessed through the surrogate foreign key.

8.  Set the **JoinRelation** property to the relation that indicates which related data to access. The values available correspond to the relations that were defined for the table that is being used for the data source. The relations are the items in the Relations node for the table.

9.  Save the changes in the AOT.

For example, consider the Facility Management sample application. The FCMWorkOrders table has three foreign key fields defined. Each of these foreign keys reference surrogate keys fields in the parent tables. The first foreign key indicates the room that the work order is associated with. The second indicates the worker that is initiating the work order. The third indicates the worker that is performing the action for the work order. When the FCMWorkOrders table was created, a relation for each one of the surrogate foreign keys had to be added to the table. The following illustration shows these three relations. Notice that two of the relations link to the HcmWorker table.

![Relations for Surrogate Foreign Keys](images/Hh330357.EP_TableRelations(AX.60).gif "Relations for Surrogate Foreign Keys")

The FCMWorkOrderDetails data set displays detailed information about a work order. To access the data referenced by the three surrogate foreign keys, a reference data source for each surrogate foreign key is added. The following illustration shows the three reference data sources that were added to access the surrogate foreign key data.

![Reference Data Sources for Surrogate Foreign Keys](images/Hh330357.EP_Reference(AX.60).gif "Reference Data Sources for Surrogate Foreign Keys")

When the FCMWorkOrderDetails data set is accessed in a User Control, the fields that can be accessed through the surrogate foreign keys are available for use. The following illustration shows the Available Fields list in the **Bound Field Designer** that is accessing fields from the FCMWorkOrderDetails data set. Notice that the list of available fields includes those accessed through the HcmWorkerRequester reference data source that is based on the surrogate foreign key.

![Fields available from Reference Data Sources](images/Hh330357.EP_BoundFieldDesignerRefDataSource(AX.60).gif "Fields available from Reference Data Sources")

## Surrogate Foreign Key Replacement

If you want to display only the friendly name for a surrogate foreign key, you can use the AxReferenceBoundField component to do this. When you use an AxReferenceBoundField component in a form or grid for a User Control, surrogate foreign key replacement is used to show the value. The actual value shown is the list of fields in the AutoIdentification field group for the row referenced by the surrogate foreign key. The ReferenceField group in the Available Fields list of the **Bound Field Designer** lists the surrogate foreign key fields for the selected data source. When you select one of the fields from this group, an AxReferenceBoundField component that accesses the surrogate key field is added to the User Control.

The following illustration shows the ReferenceField values (surrogate key values) that are available for the FCMWorkOrders data set. RoomRecId is a surrogate foreign key that is stored in the FCMWorkOrders table. When RoomRecId is selected from the ReferenceField group, an AxReferenceBoundField component is created. The AxReferenceBoundField component uses surrogate foreign key replacement to display the friendly name for the room.

![ReferenceField group lists surrogate foreign keys](images/Hh330357.EP_BoundFieldDesginerReferenceField(AX.60).gif "ReferenceField group lists surrogate foreign keys")

For information about the AxReferenceBoundField component, see [Other Bound Field Types](other-bound-field-types.md).

