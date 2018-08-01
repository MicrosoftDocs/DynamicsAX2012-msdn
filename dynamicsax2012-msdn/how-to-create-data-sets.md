---
title: 'How to: Create Data Sets'
TOCTitle: 'How to: Create Data Sets'
ms:assetid: 31547e4a-ae10-42dc-a012-704d6eb04d30
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc552190(v=AX.60)
ms:contentKeyID: 35245187
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Create Data Sets [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To access data in Microsoft Dynamics AX with Enterprise Portal, you must use a data set. After the data set is created, you will use the [AxDataSource](axdatasource.md) component in a User Control to access the data set.

## Creating a Data Set

### To create a data set

1.  In the AOT, expand the **Data Sets** node.

2.  Right-click the **Data Sets** node and then click **New Data Set**.

3.  Right-click the new data set, and then click **Properties**.

4.  Rename the data set by modifying the **Name** property.

5.  Save the changes in the AOT.

## Adding Data Sources to a Data Set

### To add data sources to a data set

1.  In the AOT, expand the **Data Sets** node.

2.  Expand the node for the data set that you want to add a data source to.

3.  Right-click the **Data Source** node and then click **New Data Source**.

4.  Right-click the new data source and then click **Properties**.

5.  Rename the data source by modifying the **Name** property.

6.  Modify additional data source properties, as needed. For more information, see [Data Set Data Source Properties](https://msdn.microsoft.com/en-us/library/cc550315\(v=ax.60\)).

7.  If the data set will be used to save data, set the **ChangeGroupMode** property for the **Data Sources** node of the data set. This property control whether joined data sources will be saved independently or as a single unit.

