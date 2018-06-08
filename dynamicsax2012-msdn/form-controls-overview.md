---
title: Form Controls Overview
TOCTitle: Form Controls Overview
ms:assetid: 4bd2926c-4a8d-4d7e-9a2a-95a237fc2104
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa605589(v=AX.60)
ms:contentKeyID: 35243370
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Form Controls Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

All items added to a form are controls. Examples of controls include text boxes, list boxes, option buttons, command buttons, and images.

Controls display data, perform actions, or provide decoration. For example, you can use a text box on a form to display data, a command button on a form to open another form, or a picture on a form to show a company logo. For more information on the different types of controls available in Microsoft Dynamics AX, see [Overview of Form Control Types](overview-of-form-control-types.md).

The properties on a form control determine the data source and behavior of a control. Control settings can usually remain at Auto. Some controls, however, have properties that must be set. For more information, see [Form Control Properties](form-control-properties.md).

The behavior of a control must sometimes be programmed. Each form control has a set of methods that can be overridden. You can also create your own methods. For more information, see [Methods on Form Controls](methods-on-form-controls.md). If you need to add code, write it on the form data source (table), or in a class rather than on a control. This enables the code to be reused.

The data source for a control can be a database field (a bound control), or the result of a calculation (a calculated control). Other controls do not have a data source or display a hard-coded text string or graphic. These are unbound controls. For more information, see [Bound Controls, Unbound Controls, and Calculated Controls](bound-controls-unbound-controls-and-calculated-controls.md).

Controls are sometimes containers for other controls. For example, Grid controls can contain edit controls (StringEdit, IntEdit, and so on), and a Tab control can contain TabPage controls.

For examples of how controls are used in Microsoft Dynamics AX, see the tutorial\_Form\_Controls, tutorial\_Form\_ListControl, tutorial\_Form\_TableControl, tutorial\_Form\_TreeControl, and tutorial\_Form\_Windowingrid forms.

## See also

[How to: Add a Control to a Form](how-to-add-a-control-to-a-form.md)

[Forms in Microsoft Dynamics AX](forms-in-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

