---
title: User Control Events
TOCTitle: User Control Events
ms:assetid: a11a7859-5df1-482f-9126-364d81936c0a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc607781(v=AX.60)
ms:contentKeyID: 28119461
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# User Control Events [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The components of User Controls have various events that occur as the control displays and processes data. You can add code to a User Control to respond to these events.

## Available Events

The User Control components have the standard ASP.NET control events available.

  - DataBinding

  - Disposed

  - Init

  - Load

  - PreRender

  - Unload

Many of the User Control components have additional events that are specific to that component. For example, the AxSection component has the following additional events available.

  - Activate

  - Deactivate

  - SectionCollapsed

  - SectionCollapsing

  - SectionExpanded

  - SectionExpanding

  - RenderingSummaryField

For the list of events available for each User Control component, see the Events list for the component in [User Control Components](user-control-components.md).

## Registering for Events

The registration for User Control events is typically done in the Page\_Init method. Add this method to the User Control code.

``` csharp
protected void Page_Init(object sender, EventArgs e)
{

}
```

In Page\_Init method, add registrations for the events to which your code should respond. The IntelliSense in Visual Studio will help you find which events are available, as shown in the following illustration.

![User Control Events](images/Cc607781.EP_UserControlEvents(AX.60).gif "User Control Events")

**Events for a User Control**

It will also help you add the event handler code to your project. After you have selected the event, type += and use the tab key as instructed by the IntelliSense to add the registration and event handler method. This is shown in the following illustration.

![User Control Event Registration](images/Cc607781.EP_UserControlEventRegistration(AX.60).gif "User Control Event Registration")

**Event registration added by IntelliSense**

The completed event registration and the event handler will resemble the following code.

``` csharp
this.RoomForm.ItemCommand += new DetailsViewCommandEventHandler(RoomForm_ItemCommand);


void RoomForm_ItemCommand(object sender, DetailsViewCommandEventArgs e)
{

}
```

## Responding to Events

The code in the event handler method will respond to the event. Use the event arguments passed to the event handler to determine what task has to be performed. For example, the following code examines the CommandName property of the event arguments to determine whether the Cancel button for the AxForm component was clicked.

``` csharp
void RoomForm_ItemCommand(object sender, DetailsViewCommandEventArgs e)
{
    if (e.CommandName == "Cancel")
    {            
        this.DataSourceView.CancelEdit();
        this.RedirectToPreviousPage();
    }
}
```

Events that occur before an action is performed by Enterprise Portal can be canceled. The event argument object passed to the event handler for these events has a Cancel property. Set this property to false to prevent the event from continuing.

## See also

[How to: Add Code to User Controls](how-to-add-code-to-user-controls.md)

