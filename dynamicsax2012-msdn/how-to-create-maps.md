---
title: 'How to: Create Maps'
TOCTitle: 'How to: Create Maps'
ms:assetid: 389c6b3a-19d0-4ff3-a638-6ee7d6953ae0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa624363(v=AX.60)
ms:contentKeyID: 35242858
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create Maps [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Maps are objects that associate a map field with a field in one or more tables. This enables you to use the same field name to access fields with different names in different tables. Maps are created in the Application Object Tree (AOT) in the **Maps** node of the **Data Dictionary**.

For more information about maps, see [Map Overview](map-overview.md).

## Create a Map by using the AOT

1.  In the AOT, expand the **Data Dictionary** node, right-click **Maps**, and then click **New Map**.

2.  Expand the new map, right-click **Fields**, click **New**, and then select a data type to add a field to the map. This is the base data type of the map field.

3.  Repeat step 2 to add more fields to the map.

4.  If the map field is associated with a table field that is an extended data type, set the map field's ExtendedDataType property as follows:
    
    1.  Right-click the map field, and then select **Properties**.
    
    2.  Select an extended data type from the **ExtendedDataType** property list.
    

    > [!NOTE]
    > <P>Table fields that have similar functionality are typically based on an extended data type. For example, a table field that contains an address is typically based on the Addressing extended data type.</P>



5.  Organize related fields into a group as follows:
    
    1.  Right-click the **Field Groups** node, and then click **New Group**.
    
    2.  Drag fields from the **Fields** node to the group that you created in step 5a.
    
    3.  Repeat steps 5a and 5b to organize fields into additional groups.

6.  Associate map fields with specific table fields as follows:
    
    1.  Right-click **Mappings**, and then click **New Mapping**. A new mapping is added with all the map fields as defined in step 2.
    
    2.  Right-click the new mapping, click **Properties**, and then select a table from the **MappingTable** property list.
    
    3.  Expand the new mapping, and then right-click a field node.
    
    4.  Click **Properties**, and then select a field from the **MapFieldTo** property list.
        
        The list of available fields varies depending on the data type that you selected in step 2.
    
    5.  Repeat step 6d for each field node that is displayed below the new mapping.

7.  Save your changes to the map.

## See also

[Map Overview](map-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

