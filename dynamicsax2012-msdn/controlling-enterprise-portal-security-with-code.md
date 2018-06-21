---
title: Controlling Enterprise Portal Security with Code
TOCTitle: Controlling Enterprise Portal Security with Code
ms:assetid: 904ed6aa-b2ad-441c-856e-0860521a201c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh608237(v=AX.60)
ms:contentKeyID: 39555626
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Controlling Enterprise Portal Security with Code [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Forms in the Microsoft Dynamics AX client can automatically check security permissions for the current user, and then hide or show the items in the action pane appropriately. List pages that are shared by both the Microsoft Dynamics AX client and Enterprise Portal can also show or hide the action pane items based on the current user's security access. Other pages in Enterprise Portal that contain User Controls do not automatically show or hide items in the action pane based on the current user's security access. If you want to control access based on the user's security settings, you must do this with code that you add to the User Control.

The SetMenuItemProperties event of the User Control is used to show or hide the specific items in the action pane, based on the current user's security settings. The following code is part of the Page\_Load method for a User Control. It registers the SetMenuItemProperties event.

``` csharp
// Register the event to set properties for the Action Pane items
AxBaseWebPart webpart = AxBaseWebPart.GetWebpart(this);
webpart.SetMenuItemProperties += new EventHandler<SetMenuItemPropertiesEventArgs>(webpart_SetMenuItemProperties);
```

The SetMenuItemProperties event handler is called one time for each item in the action pane. Because there are multiple items in the action pane, this single event handler is called multiple times. The code in the event handler must filter which events correspond to the action pane items that you are controlling access for. Usually, you do this based on the name of the item in the action pane. For example, assume that you wanted Microsoft Dynamics AX security to control access for the RoomEdit action for a User Control. In the code for the User Control, you could define the following constant that contains the name of the action:

``` csharp
protected const string ROOM_EDIT = "roomedit";
```

In the SetMenuItemProperties callback, you would compare the name of the item with this constant. If they match, the code can set the properties of the menu item.

``` csharp
void webpart_SetMenuItemProperties(object sender, SetMenuItemPropertiesEventArgs e)
{
    // Is this the Edit button?
    if (e.MenuItem.MenuItemAOTName.ToLower() == ROOM_EDIT)
    {
        // This is the Edit button. Code to configure its properties goes here.
    }
}
```

To determine the level of security access the current user has, you must check the data set view that is being accessed by the User Control. Properties of the data set view, such as AllowDelete, AllowEdit, and AllowNew, are automatically set based on the security permissions the user has in Microsoft Dynamics AX. Use these properties to set the characteristics of the specific action pane item.

Continuing the previous example, if the user has edit access to the data set view (the AllowEdit property of the data set view is true) then the Edit button should be visible. Otherwise, it should be hidden. The following example shows the complete event handler that sets the visibility of the Edit button:

``` csharp
void webpart_SetMenuItemProperties(object sender, SetMenuItemPropertiesEventArgs e)
{
    // Is this the Edit button?
    if (e.MenuItem.MenuItemAOTName.ToLower() == ROOM_EDIT)
    {
        // Does the data set have edit access? If it does not, hide the Edit button.
        if(this.RoomsDS.GetDataSet().DataSetViews["FCMRooms"].AllowEdit == true)
        {
            e.MenuItem.Hidden = false;
        }
        else
        {
            e.MenuItem.Hidden = true;
        }
    }
}
```

