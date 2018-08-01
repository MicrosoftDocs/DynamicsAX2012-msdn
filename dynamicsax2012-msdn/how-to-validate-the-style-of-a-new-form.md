---
title: 'How to: Validate the Style of a New Form'
TOCTitle: 'How to: Validate the Style of a New Form'
ms:assetid: de23873d-e079-4af1-acd5-df7d5f77b4ca
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh397319(v=AX.60)
ms:contentKeyID: 36929810
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Validate the Style of a New Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX Development Workspace includes the form style best practice tool. You use the form style best practice tool to verify that the form follows the design pattern guidelines for the specified style. You use the **Design.Style** property of the form to specify the style of the form. The form style best practice tool helps you create forms that look and behave like existing Microsoft Dynamics AX forms. For information about templates, form styles, and design patterns, see [Form Overview](form-overview.md).

The form style best practice tool compares the structure and property values of a form to a template based on the form design pattern. A design pattern is a set of guidelines that standardize the appearance and use of the form. The form style best practice tool produces a list of the differences between the form and the template for the specified form style. In addition, you can quickly correct many of the issues that are found.


> [!NOTE]
> <P>Many form style violations do not prevent the form from opening or completing a task. However, a form with violations might not appear or behave like other forms that perform the same type of task. You should carefully evaluate the affect of any violations that you decide to ignore.</P>



The following steps describe how to use the form style best practice tool.

### To validate the form

1.  In the AOT, expand the **Forms** node, and then expand the form that you want to validate.

2.  Expand **Designs**, and then click **Design**. In the property sheet, verify that the **Style** property identifies the style for the form.
    

    > [!NOTE]
    > <P>The value of the <STRONG>Style</STRONG> property identifies the template that the form style best practice tool uses to validate the form. Typically, the value is set when you use a template to create the form.</P>



3.  Right-click the form, click **Add-Ins**, click **Check form style best practices**. The **Form style analysis** window opens. The **Violations** tab shows a list of the differences that were found.

4.  Review the issues identified in the **Violations found** list. Click the violation you want to fix.
    
    If the **Fix violation** button is enabled, click the button to have the form style best practice tool make the changes that are required to fix the violation. If the **Fix violation** button is disabled, you have to use the AOT to manually add the control, move controls in the form design, or set a property value.

5.  To refresh the list of violations in the **Form style analysis** window, click the **Re-analyze** button. If the **Violations found** list shows additional issues, repeat the previous step until all the issues have been resolved.

6.  Close the **Form style analysis** window, and save the changes to the form.

## See also

[How to: Convert an Existing Form to a New Style](how-to-convert-an-existing-form-to-a-new-style.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

