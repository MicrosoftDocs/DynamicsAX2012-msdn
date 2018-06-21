---
title: Instantiating Application Objects Design Pattern
TOCTitle: Instantiating Application Objects
ms:assetid: 1fb0218b-ec33-4c90-8155-36ab41fdc6a1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa619732(v=AX.60)
ms:contentKeyID: 35241522
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Instantiating Application Objects Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You must use menu items to open application objects instead of opening them directly.

Menu items can be seen as APIs to the application. They are an abstract layer (interface) between the user and the actual application object that implements the functionality.

Changes to application objects are automatically reflected in the user interface when menu items are used.

## Example: CustTable

The menu item for browsing customers is the display menu item CustTable. This activates the form CustTable. All menus, menu item buttons, the "go to main table" command, and X++ code starts the customer browser by using this menu item.

To make a completely new customer browser by constructing a new form, you would have to change only the menu item CustTable to call the new application object. The new form would then be used everywhere. The same menu item is still called, but now it starts a different runnable application object.

## Instantiating an Application Object

The following table describes the ways to instantiate an application object, such as a form or a report, by using X++ code.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Way to instantiate an application object</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>MenuFunction</p></td>
<td><p>Use this by default.</p></td>
</tr>
<tr class="even">
<td><p>ClassFactory</p></td>
<td><p>Use this to start the Application object directly.</p></td>
</tr>
<tr class="odd">
<td><p>new FormRun or new ReportRun</p></td>
<td><p>Do not use.</p></td>
</tr>
</tbody>
</table>


### ![Aa619732.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa619732.collapse_all(en-us,AX.60).gif")MenuFunction

To instantiate a menu item from the X++ code, use MenuFunction.run:

  - If nothing should be delivered from the environment:
    
    new MenuFunction (menuItem CategoryStr (...), MenuItemType::....).run();

  - If something should be delivered from the environment, initialize an Args object with the needed values, and supply that:
    
    Args args = new Args();
    
    ...
    
    args.caller(...);
    
    args.record(...);
    
    new MenuFunction(menuItem CategoryStr (...),MenuItemType::...).run(args);

  - You can also use a handle to instantiate the menu function:
    
    MenuFunction menuFunction;
    
    if (...)
    
    {
    
    menuFunction = new MenuFunction(
    
    menuItem CategoryStr (...),MenuItemType::...);
    
    }
    
    else
    
    {
    
    menuFunction = new MenuFunction(
    
    menuItem CategoryStr (...),MenuItemType::...);
    
    menuFunction.run();
    
    }

menuItem CategoryStr above is one of:

  - menuItemDisplayStr

  - menuItemActionStr

  - menuItemOutputStr

Do not use MenuFunction.create to create an ObjectRun object. For example, you should not use the following:

Args args = new Args();

MenuFunction menuFunction = new MenuFunction(

menuItem..Str(...),MenuItemType::...);

ObjectRun objectRun;

;

...

args.caller(...);

args.record(...); objectRun = menuFunction.create(args); objectRun.run();

This cannot handle a situation where the object of the menu item is changed to a class—it is not general enough.

### ![Aa619732.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa619732.collapse_all(en-us,AX.60).gif")ClassFactory

If you have reasons to directly instantiate the application object, you must use ClassFactory. For example:

formRun = ClassFactory.formRunClass( args  object );

...

reportRun = ClassFactory.reportRunClass( args  object );

This takes into account any special ObjectRun subclasses that are used on the installation.

### ![Aa619732.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa619732.collapse_all(en-us,AX.60).gif")new FormRun/ReportRun

Never instantiate the application object directly. For example, do not do this:

formRun = new FormRun(...);

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

