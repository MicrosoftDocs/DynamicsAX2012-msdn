---
title: 'Walkthrough: Create and Use a Custom Operating Unit Type'
TOCTitle: 'Walkthrough: Create and Use a Custom Operating Unit Type'
ms:assetid: b98eef46-fd24-4472-bf3d-b901f32a68b8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg989762(v=AX.60)
ms:contentKeyID: 35405120
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Create and Use a Custom Operating Unit Type 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX organization model includes a set of operating unit types. These types are elements on the **OMOperatingUnitType** enumeration. You can add custom operating unit types to the enumeration.

Every instance of an operating unit that is created must be categorized as one of these operating unit types. A custom operating unit can represent a unit in retail, professional services, the public sector, and so on.

In this topic you will create an operating unit named Branch.

## Create a New Base Enumerated Value

You can create a new base enumerated value for your custom operating unit by following these steps:

1.  Create a private or shared project named **CustomOperatingUnit**.
    
    A project provides an overview of the application objects you are currently working on. For information about how to create a project, see [How to: Create a MorphX Development Project](how-to-create-a-morphx-development-project.md).

2.  Drag the **AOT** \> **Data Dictionary** \> **Base Enums** \> **OMOperatingUnitType** node onto the project node.

3.  Add an element named **OMBranch** to the **OMOperatingUnitType** enum.
    
    You do this by right-clicking the enum, and then clicking **New Element**.

4.  In the **Properties** window for the new element, set the property values as shown in the following table.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Name</p></td>
    <td><p>OMBranch</p></td>
    </tr>
    <tr class="even">
    <td><p>Label</p></td>
    <td><p>Branch</p></td>
    </tr>
    </tbody>
    </table>


5.  Add the new operating unit type to the switch case in \\Classes\\NumberSeqScope\\getFormatSegmentShortName and create a new shortNameValue that is unique

## Create a View

In this section you create a view named **DimAttributeOMBranchView**. The view resembles the views that are created for other types of operating units. For example, the **DimAttributeOMBusinessUnit** view was created for business units.

1.  Locate **DimAttributeOMBusinessUnit** under the **AOT** \> **Data Dictionary** \> **Views** node.

2.  Duplicate **DimAttributeOMBusinessUnit** by right-clicking the **DimAttributeOMBusinessUnit** node, and then clicking **Duplicate**. The AOT will create the **CopyOfDimAttributeOMBusinessUnit** node.

3.  Drag the **CopyOfDimAttributeOMBusinessUnit** node onto the project node.

4.  In the **Properties** window for the newly created enum element, set the properties as shown in the following table.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Name</p></td>
    <td><p>DimAttributeOMBranchView</p></td>
    </tr>
    <tr class="even">
    <td><p>Label</p></td>
    <td><p>Branch</p></td>
    </tr>
    <tr class="odd">
    <td><p>SingularLabel</p></td>
    <td><p>Branch</p></td>
    </tr>
    <tr class="even">
    <td><p>DeveloperDocumentation</p></td>
    <td><p>The <strong>OMBranchView</strong> contains all records from the <strong>OMOperatingUnit</strong> table that are marked as branches.</p></td>
    </tr>
    </tbody>
    </table>


5.  Locate the **OMOperatingUnitTypeOMBusinessUnit** range under the new **DimAttributeOMBranchView** view. The range is under the **Metadata** \> **Data Sources** \> **BackingEntity(OMOperatingUnit)** \> **Ranges** node.

6.  In the **Properties** window for the **OMOperatingUnitTypeOMBusinessUnit** range, set the properties as shown in the following table.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Name</p></td>
    <td><p>OMOperatingUnitTypeOMBranch</p></td>
    </tr>
    <tr class="even">
    <td><p>Field</p></td>
    <td><p>OMOperatingUnitType</p></td>
    </tr>
    <tr class="odd">
    <td><p>Value</p></td>
    <td><p>Branch</p></td>
    </tr>
    </tbody>
    </table>


## Create a Menu Item for the Branch Unit Type

1.  Create the menu item **OMBranchMenuItem** in the **CustomOperatingUnit** project. To do this, right-click the project node, and then click **New** \> **Menu Item** \> **Display**.

2.  In the **Properties** window for **OMBranchMenuItem**, set the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Name</p></td>
    <td><p>OMBranchMenuItem</p></td>
    </tr>
    <tr class="even">
    <td><p>Label</p></td>
    <td><p>Branches</p></td>
    </tr>
    <tr class="odd">
    <td><p>Object</p></td>
    <td><p>OMOperatingUnit</p></td>
    </tr>
    <tr class="even">
    <td><p>EnumTypeParameter</p></td>
    <td><p>OMOperatingUnitType</p></td>
    </tr>
    <tr class="odd">
    <td><p>EnumParameter</p></td>
    <td><p>OMBranch</p></td>
    </tr>
    </tbody>
    </table>


## Review the Project

At this point you have created all the items that are shown in the following image.

![Custom unit project](images/Gg989762.AOTOrgMCustUnitProj(en-us,AX.60).jpg "Custom unit project")

**The project that you create**

## Use Your New Operating Unit Type

In this section you use the new **OMBranch** operating unit type that you created. You create a new instance of an operating unit, and it is associated to the **OMBranch** type. Perform the following steps:

1.  Right-click the **OMBranchMenuItem**, and then click **Open**.

2.  Click **New** on the toolbar, and then enter the branch name as **My Branch**.

3.  The **Branch** form contains the new unit instance that you created, as shown in the following image.
    
    ![Custom unit form](images/Gg989762.AOTOrgMCustUnitCreateForm(en-us,AX.60).jpg "Custom unit form")
    
    **The new operating unit that you create**

## Next Steps

An operating unit is an organization that divides the control of economic resources and operational processes among people who have a duty to maximize the use of scarce resources, to improve processes, and to account for their performance. After you complete this walkthrough you have a new operating unit type. Now you can create a new operating unit. For information about how to create an operating unit, see [Create or modify an operating unit](https://msdn.microsoft.com/en-us/library/hh209234\(v=ax.60\)).

You can incorporate the instances of new types of operating units in the organization hierarchy. You can also use operating units in end-to-end transaction scenarios to:

  - Define and apply data security policies for transactions.

  - Define business rules and policies to be applied for transactions.

  - Perform aggregated rollup reporting.

## See also

[Extending the Organization Model](extending-the-organization-model.md)

[Create or modify an operating unit](https://msdn.microsoft.com/en-us/library/hh209234\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

