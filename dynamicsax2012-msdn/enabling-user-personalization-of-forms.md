---
title: Enabling User Personalization of Forms
TOCTitle: Enabling User Personalization of Forms
ms:assetid: de3aa951-220e-498a-a378-8c2810f8a266
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa877413(v=AX.60)
ms:contentKeyID: 35252085
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Enabling User Personalization of Forms 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Users have several options when they personalize Microsoft Dynamics AX forms. Restrict these options by using the following:

  - AllowUserSetup property on the form control

  - AllowAdd property on the form data source field

For more information, see [User Personalization of Forms](user-personalization-of-forms.md).

For user-personalization to work, the code must be independent from the actual positioning of the control. You must not use any information about the position of the control or assume that the order of the controls is retained.

## Tab Controls

If the tabChange or tabChanged methods are overridden on a Tab control, users cannot personalize the tabs (for example, by changing their order), regardless of the AllowUserSetup property value.

The parameters received for the FormTabControl.tabChange and FormTabControl.tabChanged methods are based on tabbed page indexes. The parameters are dependent on the current position of the tabbed page. If either method is overridden, prevent users from moving a tabbed page.

Use the following methods instead of the tabChange or tabChanged methods:

  - FormTabPageControl.pageActivated

  - FormTabPageControl.allowPageDeactivate

These methods operate on the TabPage control. They neither pass information about the current positioning of the tabbed page nor allow full user setup.

## MenuButton Controls

The user-personalization level for this control is limited to Restricted if the clicked method is overridden. MenuButton controls are usually used to add menu items from code. The results of user personalization of the form can be unpredictable under these circumstances.

## Names of Controls

Control names need to be unique to help determine which control has been moved.

Controls bound to fields in the Auto field groups are automatically given the following names:

  - groupName\_FieldName for data fields

  - groupName\_M\_FieldName for display methods

Avoid using these names elsewhere in the system.

When the user creates new controls, they are automatically given a name that contains the user ID and a counter number.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

