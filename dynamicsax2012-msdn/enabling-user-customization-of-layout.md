---
title: Enabling User Customization of Layout
TOCTitle: Enabling User Customization of Layout
ms:assetid: abc6c017-9779-4418-8eab-438ee2fbf195
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa853799(v=AX.60)
ms:contentKeyID: 35249667
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Enabling User Customization of Layout 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This is the second highest level that can be set for [user personalization of forms](user-personalization-of-forms.md). It requires that you set the AllowUserSetup property on the form control to Yes and AllowAdd property on the form data source field to Restricted.

Users can adjust properties on controls and move controls between containers. Users can also create their own tabbed page.

Controls can be moved from the **Setup** form (available in the shortcut menu for open forms) either by dragging them with the mouse pointer or by using the navigation buttons. Grid columns can be moved within the grid by dragging them directly into the form.

You should ensure that most forms support the moving of controls. No code can be dependent on exact positioning of controls. In general, if the form does not interfere with the automatic arranging mechanism, and it is not dependent on focus issues, ordering, and so on, there is usually no need to change the code to support this feature. For more information see [Enabling User Personalization of Forms](enabling-user-personalization-of-forms.md).


> [!NOTE]
> <P>For a control to be moved, both the origin container and the target container must have the AllowUserSetup property set to Yes.</P>



## See also

[Form Control Properties](form-control-properties.md)

[Form Data Source Field Properties](form-data-source-field-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

