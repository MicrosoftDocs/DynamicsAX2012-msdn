---
title: Best Practices for Labels
TOCTitle: Best Practices for Labels
ms:assetid: 10158fcc-1fa4-4056-835f-98c79e0cd390
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa586081(v=AX.60)
ms:contentKeyID: 35240519
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Labels [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Every user interface text must be defined by using a label. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

A new label must be created for each new semantic use.

Existing labels must be reused. Always try to find a label that expresses the same semantics as the semantics you want to express.

A label should have an uppercase first letter and all the other letters should be in lowercase. Labels should not end with a period unless they end with three periods, for example: "New…", "Add…". ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

You should not use text constants (for example "%1 - %2") to format labels. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

Describe the use of the text that is used in the label in US-English in the **Description** field on the **Label editor** form. This is particularly important for shorter labels where the context is not completely clear. The comment is used when the label is translated to other languages.

## Inherit Labels from Underlying Data Types

The contents of label-type properties are usually automatically taken from the underlying definitions. For example, the label used for a field HelpText is often inherited from the HelpText of the underlying extended data type. It is an error to insert the same label as that used in the underlying definition (inherit it, do not duplicate it). ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

However, the label should be changed, if a different description is needed for the item. The following illustration shows a typical situation:

![Inheritance of labels](images/Aa586081.Image1(en-us,AX.60).gif "Inheritance of labels")

  - A label is defined on an extended data type.

  - The extended data type is extended by another extended data type, but as long as the label is not changed, it is inherited and reused.

  - That other extended data type is used on a field, and as long as the label is not changed on the field, it is reused again.

  - The field is shown using a control on a form, but as long as the label is not changed on the control, it is reused again.

When possible, a label should be created on an extended data type rather than on a field. If an existing extended data type can be reused, but the existing label is considered unsuitable, create a new extended data type based on the former one and change only the label.

## See also

[HelpText Guidelines](helptext-guidelines.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

