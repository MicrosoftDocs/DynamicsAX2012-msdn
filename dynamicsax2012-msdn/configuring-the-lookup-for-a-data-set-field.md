---
title: Configuring the Lookup for a Data Set Field
TOCTitle: Configuring the Lookup for a Data Set Field
ms:assetid: 50d6e89a-34e9-456c-b219-bcc087db97ec
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh830903(v=AX.60)
ms:contentKeyID: 45260823
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Configuring the Lookup for a Data Set Field [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The **TitleField1** and **TitleField2** properties from the underlying table are used as the default content for a lookup in Enterprise Portal. You can use the dataSetLookup() method in the field for the data source of the data set to configure the content of the lookup.

## Configuring the Lookup

The following illustration shows the default lookup that is displayed for the **Room** field in the **AddEditWorkOrder** User Control. The lookup contains the two default fields that were specified for the **TitleField1** and **TitleField2** properties of the underlying **FCMRooms** table.

![Original Lookup](images/Hh830903.EP_DataSetLookupOriginal(AX.60).gif "Original Lookup")

The **FCMWorkOrderAddEdit** data set is used to access data for this User Control. The **FCMWorkOrders** table is the main data source for this data set. Expanding the list of fields for the **FCMWorkOrders** data source shows the **RoomRecId** field, which corresponds to the **Room** field that is displayed in the form.

You can add the dataSetLookup() method to the **RoomRecId** field to specify the fields that are displayed in the lookup for it. The following code example shows how this X++ method is used to add three fields to the Room lookup.

    void dataSetLookup(SysDataSetLookup sysDataSetLookup)
    {
        List list = new List(Types::String);
        Query query = new Query();
    
        // Add the table to the query.
        query.addDataSource(tableNum(FCMRooms)); 
    
        // Specify the fields to use for the lookup.
        list.addEnd(fieldStr(FCMRooms,RoomName));
        list.addEnd(fieldStr(FCMRooms,RoomType));
        list.addEnd(fieldStr(FCMRooms,InService));
    
        // Supply the set of lookup fields.
        sysDataSetLookup.parmLookupFields(list);
     
        // Specify the field that is returned from the lookup.
        sysDataSetLookup.parmSelectField('RoomName');
    
        // Pass the query to the SysDataSetLookup so that the query is used.
        sysDataSetLookup.parmQuery(query);
    }

The following illustration shows the method that is added to the field for the data source that is part of the data set.

![dataSetLookup Method](images/Hh830903.EP_DataSetLookupMethod(AX.60).gif "dataSetLookup Method")

When the lookup for the **Room** field is displayed, the dataSetLookup() method configures the contents of the lookup to display the following values:

![Overridden Lookup](images/Hh830903.EP_DataSetLookupOverridden(AX.60).gif "Overridden Lookup")

