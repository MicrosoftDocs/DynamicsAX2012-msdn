---
title: Using Controls in a Form Design
TOCTitle: Using Controls in a Form Design
ms:assetid: 08dea767-9dd5-4127-9843-2f3a8e404f9e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa554541(v=AX.60)
ms:contentKeyID: 35240318
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using Controls in a Form Design [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The design of a form is determined by the controls that you add to the form, and the properties that you set on the **Design** node and on the individual controls.

To ensure a uniform application interface, many properties have Auto values. This enables a form to be created using a drag-and-drop operation, setting only a few properties manually.

## Tab Pages

Tab pages are created by adding Tabpage controls within a container Tab control. For more information, see [Walkthrough: Create a Form that Has Tabbed Pages](walkthrough-create-a-form-that-has-tabbed-pages.md).

## Buttons

Buttons are usually grouped within a ButtonGroup control. There are several different button controls:

  - CommandButton controls: Buttons that execute a commonly used command, for example: Open, Save, and Select All.

  - MenuButton controls: Buttons that open a submenu, containing MenuItemButton controls.

  - MenuItemButton controls: Buttons that activate a menu item. For example, a MenuItemButton might open another form.

  - Button controls: Other kinds of buttons.

## Field Groups

Fields on a form are usually organized into groups, using a Group control. A Group control is automatically created if you drag a field group from the form data source onto the form **Design** node. You can also group controls manually.

The heading for a group is set using the Caption property on the Group control.

The sequence of fields within a group can be changed by doing one of the following:

  - Re-arrange the fields when the form is in design mode. To open the form in design mode, click the **Edit** command in the form shortcut menu.

  - Re-arrange the fields in the **Design** node for the form.

  - Re-arrange the fields in the group in the table.

## Size of Controls

The size of a control is defined as the size of the control itself plus the control label.

The following form shows five groups (in different colors) that each have one or more controls.

![Form groups arranged with AlignChildren property](images/Aa554541.FORM0018(en-us,AX.60).gif "Form groups arranged with AlignChildren property")

The width of the groups is determined by the width of the longest control on the form, as all groups are set to have the same width, using the AlignChildren property (see "Alignment of Controls" later in this topic).

The dimensions of a control are set by the Width and Height properties. The Auto settings for these properties make allowances for preferences with respect to font, font style, font size, and so on, in that the dimensions change dynamically when, for example, a larger font size is selected.

## Position of Controls

The ArrangeMethod property on the form design or on a Group control determines whether child field groups should be arranged in columns or in rows.

Container controls (Tab, Tabpage, and Group) are arranged in one or more columns as specified by the Columns property on the parent control or the form design.

The VerticalSpacing property defines the space (in pixels) after the control.

In the following example, the Columns property has been changed from 1 to 2 on the form design, and the VerticalSpacing property for the first group (the shaded group) has been changed from Auto to 40.

![Using Columns and VerticalSpacing properties](images/Aa554541.FORM0019(en-us,AX.60).gif "Using Columns and VerticalSpacing properties")

The Top and Left properties on a control allow you to position a control at one of the corners of the form window, or you can specify coordinates to give an exact position. When controls are arranged on a form, a control where you have entered coordinates has a higher priority than a control that has Auto settings for the properties.

## Alignment of Controls

The three central alignment properties for a form control are:

  - AlignChildren: Set on the form design, or container controls. When set to Yes, the immediate children of the control are aligned in the same manner.

  - AlignChild: Set on container controls. When set to No, the container control is not included in the alignment set by the parent container control.

  - AlignControl: Set on individual controls. When set to No, the container control is not included in the alignment set by the parent container control.

In the following example, the second control in the first group (called "Label") has the AlignControl property set to No. This control is not aligned to the right-margin of the group like the first control. In the second group (shown in yellow), the AlignChild property has been set to No. This group has a different width compared to the other control groups (the width of the group is set by the widest control in the group, rather than the widest control on the form).

![Effect of AlignControl and AlignChild properties](images/Aa554541.FORM0021(en-us,AX.60).gif "Effect of AlignControl and AlignChild properties")

## See also

[Overview of Form Control Types](overview-of-form-control-types.md)

[Form Design Properties](form-design-properties.md)

[Form Control Properties](form-control-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

