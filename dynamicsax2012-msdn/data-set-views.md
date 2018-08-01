---
title: Data Set Views
TOCTitle: Data Set Views
ms:assetid: b7c4d08b-5362-431e-98db-1f004486eded
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dd638058(v=AX.60)
ms:contentKeyID: 35246121
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Data Set Views [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A data set provides access to a collection of data in Microsoft Dynamics AX. The data set can have one or more data sources that define the data that is being accessed. Each data source corresponds to a table or view in Microsoft Dynamics AX. The data sources can have joins that define how the data sources are related to each other.

When you access data through a data set, you will use a data set view. The data set views available for a data set depend on the data sources defined and the relationships (joins) defined for them.

The following sections describe the three standard patterns used for data sets:

  - Single

  - One-to-One

  - One-to-Many

## Single

In this pattern, one table is added as a data source.

The data set will have two data set views:

  - The table base name. This data set view accesses all rows in the table. It is used for controls that display multiple rows, such as an [AxGridView](axgridview.md).

  - The table base name, appended with \_Current. This data set view accesses the current row in the table. It is used for controls that display a single row, such as an [AxForm](axform.md).

For example, the FCMWorkOrders table is added as the only data source for the FCMWorkOrdersList data set. The data set view named FCMWorkOrders will access all rows in the FCMWorkOrders table. The data set view named FCMWorkOrders\_Current will access only the current row in the FCMWorkOrders table.

The following illustration shows the data set views.

![Single](images/Dd638058.EP_DataSetViewSingle(AX.60).gif "Single")

## One-to-One

In this pattern, a main table is added as a data source. One or more additional tables are added as data sources that contain data related to each row in the main table. For each row in the main table, there is one corresponding row in each one of the additional tables.

  - The **JoinSource** property for each of these additional tables is set to the name of the main table.

  - The **LinkType** property for each of these additional tables is set to **InnerJoin** or **OuterJoin**. InnerJoin includes the rows in the main table, only if there is a corresponding row in the joined table. OuterJoin includes every row in the main table, even if there is no corresponding row in the joined table.

The data set will have two data set views:

  - The main table base name. This data set view accesses all rows in the table. It is used for controls that display multiple rows, such as an [AxGridView](axgridview.md).

  - The main table base name, appended with \_Current. This data set view accesses the current row in the table. It is used for controls that display a single row, such as an [AxForm](axform.md).

The fields from the additional tables will be included with each row of the main table as if they were part of the main table. The additional tables do not have data set views because their data is accessed through the main table.

For example, the FCMWorkOrders table is added as the main table for the FCMWorkOrderDetails data set. The HcmWorker table is added as an additional table. Each row in the FCMWorkOrders table can have up to one corresponding row in the HcmWorker table. The link type for the HcmWorker table is set to OuterJoin. The data set view named FCMWorkOrders will access all rows in the FCMWorkOrders table, and the corresponding rows in the HcmWorker table. The data set view named FCMWorkOrders\_Current will access only the current row in the FCMWorkOrders table and the corresponding row for the HcmWorker table. There is no data set view for the HcmWorker table.

The following illustration shows the data set view.

![One-to-One Relationship](images/Dd638058.EP_DataSetViewOneToOne(AX.60).gif "One-to-One Relationship")

## One-to-Many

In this pattern, a main table is added as a data source. One or more additional tables are added as data sources that contain one or more records for each row in the main table.

  - The **JoinSource** property for each additional table is set to the name of the main table.

  - The **LinkType** property for each additional table is set to **Active**.

The data set will have the following data set views for the main table:

  - The main table base name. This data set view accesses all rows in the main table.

  - The main table base name, appended with the \_Current. This data set view accesses the current row in the main table.

The rows accessed in the additional tables are automatically determined by the row that is currently being accessed in the main table. The data set will have the following data set views for each additional table:

  - The table base name of the additional table. This data set view accesses all rows in the additional table that correspond to the current row in the main table.

  - The table base name of the additional table appended with \_Current. This data set view accesses only the current row in the additional table that corresponds to the current row in the main table.

For example, the FCMRooms table is added as the main table for the FCMRoomDetails data set. The FCMWorkOrders table is added as an additional table. Each row in the FCMRooms table can have several corresponding rows in the FCMWorkOrders table. The link type for the FCMWorkOrders table is set to Active. The data set view named FCMRooms will access all rows in the FCMRooms table. The data set view named FCMRooms\_Current will access the current row in the FCMRooms table. The data set view named FCMWorkOrders will access all the rows in the FCMWorkOrders table that correspond to the current row in the FCMRooms table. The FCMWorkOrders data set view is updated automatically every time that a new row is selected in the FCMRooms table.

The following illustration shows the corresponding data set views in both tables.

![One-to-Many Relationship](images/Dd638058.EP_DataSetViewOneToMany(AX.60).gif "One-to-Many Relationship")

