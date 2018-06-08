---
title: Table Inheritance
TOCTitle: Table Inheritance
ms:assetid: 39270682-7477-44a8-a456-fa8c628f45b4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh330283(v=AX.60)
ms:contentKeyID: 36806097
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Table Inheritance 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When the tables you use for your Enterprise Portal integration are part of a table inheritance hierarchy, you must take that hierarchy into account when you create the data sets. The following sections discuss issues you should consider.

## Table Selection

When creating a data set, the table you select to use for the data set determines the types from the table hierarchy that can be accessed by the data set. You can access types for the base table. You can also access types for the tables that inherit from the base table.

For example, the following illustration shows the table hierarchy for room information in the Facility Management sample application. It consists of the base table FCMRooms, plus two tables that are derived from the base table. If you select the FCMRooms table as the main table for the data set, you could access data for rooms. You could also access data for private rooms and public rooms, because these types inherit from the FCMRooms table. If you selected the FCMPublicRooms table as the main table for the data set, you could access data only for public rooms. That is because this table is at the end of the hierarchy.

![Rooms table hierarchy](images/Cc624200.EP_RoomTableHierarchy(AX.60).gif "Rooms table hierarchy")

For more information about how to design a table inheritance hierarchy, see [When to Use Table Inheritance](when-to-use-table-inheritance.md).

## Creating Records

When you create a new record in a User Control for Enterprise Portal, the table hierarchy is examined to determine what types of records can be created. A dialog box is displayed that allows users to select the type of record they want to create.

![Record type selection](images/Hh330283.EP_SelectRecordType(AX.60).gif "Record type selection")

For example, the FCMRooms data set accesses the FCMRooms table shown in the hierarchy in the previous section. When creating a new record based on this data set, the user can decide to create a room, a private room, or a public room. These are the three types that are defined in the table hierarchy.

If you do not want the user to choose the type of record to create, but instead want to create a record of a specific type, you can use the AxRowCreating event of the [AxForm](axform.md) component to do this. For example, the following code causes the AxForm to create a private room.

``` csharp
protected void RoomForm_AxRowCreating(object sender, FormViewRowCreateEventArgs e)
{
    FormViewPolymorphicRowCreateEventArgs args;

    // Cast the arguments passed in to be the needed type.
    args = (FormViewPolymorphicRowCreateEventArgs)e;

    // Clear any existing types.
    args.ConcreteTypes.Clear();

    // Add the type for private rooms.
    args.ConcreteTypes.Add(args.ViewMetadata.DataSources["FCMRooms_FCMPrivateRooms"]);
}
```

Notice the syntax for the specifying the concrete type. If you wanted to create the base type (rooms) you would use the string “FCMRooms”. If you wanted to create a public room you would use the string “FCMRooms\_FCMPublicRooms”. Because a public room is a derived type, its name is qualified with the base type.

## Data Set Fields

The Enterprise Portal framework interprets the table hierarchy when you add fields from a data set to a User Control. The **Bound Field Designer** lists the fields that are available, grouping them according to the tables that they are part of in the hierarchy. The following illustration shows the Available Fields list in the **Bound Field Designer** when fields are being selected from the FCMRooms data set. Notice that fields from the base table (FCMRooms) are available, as are fields from the derived tables (FCMPublicRooms and FCMPrivateRooms).

![Table hierarchy in Bound Field Designer](images/Hh330283.EP_BoundFieldDesignerTableInheritance(AX.60).gif "Table hierarchy in Bound Field Designer")

The Enterprise Portal framework can interpret the table hierarchy, displaying data for the fields in the User Control that are valid for the type of data being displayed. The fields that are not valid for the specific type are shown as not being available.

For example, a record of type FCMPrivateRoom can be assigned to a specific worker in Microsoft Dynamics AX. If a record for a private room is being displayed, the Assignment field is active. If a record for a room (FCMRoom) or a public room (FCMPublicRoom) is being displayed, the Assignment field is unavailable because this field is not valid for either of those types. The following illustration shows the fields that are available for a public room. Notice that neither of the fields in the Assignment group can be accessed, because these fields are valid only for records of type FCMPrivateRoom.

![Available fields for public rooms](images/Hh330283.EP_TableHierarchyAvailableFields(AX.60).gif "Available fields for public rooms")

