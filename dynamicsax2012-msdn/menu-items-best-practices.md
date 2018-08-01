---
title: Menu Items Best Practices
TOCTitle: Menu Items
ms:assetid: a97136ba-145f-4649-9995-e0a54318efed
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa852732(v=AX.60)
ms:contentKeyID: 35249501
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Menu Items Best Practices [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Create menu items for runnable application objects for placement in menus and as buttons on forms.

Create the menu item in the appropriate conceptual folder as follows:

  - **Display** - Must be used for runnable application objects that primarily present forms, dialogs, and so on, to the user.

  - **Output** - Must be used for runnable application objects whose primarily function is to print a result.

  - **Action** - Must be used for runnable application objects whose primarily function is to do some kind of a job, such as creating or updating transactions in the database.

## Menu Item Properties

The following table describes the best practices for menu item properties, which are in the same order that they appear in the Application Object Tree (AOT).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>The Name property should have the same name as the object that the menu item opens.</p></td>
</tr>
<tr class="even">
<td><p><span id="rx15menuitemlabelprop"></span> Label</p></td>
<td><p>Use a label. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>Use the same label that is used for the Caption property of the object that the menu item opens.</p></td>
</tr>
<tr class="odd">
<td><p>RunOn</p></td>
<td><p>Ensure that you set this correctly. Client is the default value.</p></td>
</tr>
<tr class="even">
<td><p>ConfigurationKey</p></td>
<td><p>Use the key for the module it belongs to.</p></td>
</tr>
<tr class="odd">
<td><p>CountryConfigurationKey</p></td>
<td><p>For only country/region-specific functionality, use the CSE (country/region-specific engineering) configuration key.</p></td>
</tr>
<tr class="even">
<td><p>WebConfigurationKey</p></td>
<td><p>Use the key of the Web application it belongs to (if any).</p></td>
</tr>
<tr class="odd">
<td><p>NeededAccessLevel</p></td>
<td><p><span id="rx09menuaccesslevno"></span>This property sets the access level needed to start the menu item.</p>

> [!caution]  
> <P>If you set the NeededAccessLevel property to NoAccess, every user has full access to the item.</P>

<p>Set to View for output items and most display items. A Best Practices error occurs if you set NeededAccessLevel to NoAccess for output items and display items. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>Set NeededAccessLevel to Edit, Create, or Delete for action items.</p>
<p>For menu items that run classes, see the following section.</p></td>
</tr>
</tbody>
</table>


## NeededAccessLevel for Menu Items That Run Classes

You must set the NeededAccessLevel property to the appropriate level for every menu item that runs a class. There are no access level settings on individual classes.

Determine the access level required for a class by using the following criteria:

  - Decide what the logical function of the menu item is (the functionality from the users' point of view).

  - Look at all the tables accessed in the class, and find out which is the "highest" access type, and then use it for the required access level:
    
      - The "highest" access type is Delete.
    
      - Add is lower.
    
      - Edit is lower than Add, and so on.
    
    Do not include "service tables," such as SysLastValue, in the analysis.

  - A class that is changing a status ("Edit") for several records and is simultaneously creating transactions ("Add") to reflect that change can have the NeededAccessLevel set to Edit because that is the primarily logical function of the class.
    
    Another class that has the same function, where the status change is a logical Delete, can have the NeededAccessLevel set to Delete. This is partially checked by the checkMenuItemActionAccessLevel method in the SysApplCheck class.

## See also

[Instantiating Application Objects Design Pattern](instantiating-application-objects-design-pattern.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

