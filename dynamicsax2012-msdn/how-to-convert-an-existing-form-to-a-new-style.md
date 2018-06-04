---
title: 'How to: Convert an Existing Form to a New Style'
TOCTitle: 'How to: Convert an Existing Form to a New Style'
ms:assetid: 5fcab32f-f50b-4aca-a419-11095b5e1ac5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh397317(v=AX.60)
ms:contentKeyID: 36929808
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Convert an Existing Form to a New Style 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You might want to change an existing form to use a different design pattern. A design pattern is a set of guidelines that standardize the appearance and use of a form. You use the **Design.Style** property of the form to specify the style of the form. For more information about form styles and design patterns, see [Form Overview](form-overview.md).

For example, you can convert a form that has no specified design pattern to one that implements a simple list. You use the form style best practices tool to help you convert the form to the new style. The following steps show how to use the tool to convert an existing form to a new style.

### To set the design style property

1.  In the AOT, expand **Forms**, and then click the form that you want to convert to a new form style.

2.  Expand the form, expand **Designs**, and then click **Design**.

3.  In the property sheet change the value of the **Style** property to the form style you want the form to use.
    
    For example, you want to convert an existing form to the simple list design pattern. You change the value of the **Style** property to **SimpleList**.

4.  Save the changes to the form.

### To convert the form to the new style

1.  Right-click the form, click **Add-Ins**, and then click **Check form style best practices**. The **Form style analysis** window opens. Click the **Violations** tab to see the changes that are required to convert to the specified style.

2.  Click a record in the **Violations found** list. If the **Fix violation** button is enabled, you can click the button to make the changes specified by the violation. If the **Fix violation** button is disabled, you have to use the AOT to find the specified control or property and manually make the recommended change.
    
    The **Rules not checked (blocked)** list shows controls and values that the template includes that were not found on the form. You can use the **Structure analysis** tab to identify the missing controls.

3.  Click the **Structure analysis** tab. The tab shows a hierarchical view of the controls on the form and the form style template. You can use the side-by-side view of the form and template structure to identify controls that you may want to add to the form. In addition, you might find you have an existing control that has to move to a different location in the control hierarchy. To change the structure of the form, you have to use the AOT to add or move the control.

4.  After you have made changes to the form, click the **Re-analyze** button to refresh the **Violations** and **Structure analysis** tabs.
    
    If the **Violations** and **Structure analysis** tabs show additional violations, repeat the previous two steps until all the violations and structural differences are resolved.
    
    If the **Violations** and **Structure analysis** tabs do not show any violations, you have completed the conversion to the new form style.

5.  Close the **Form style analysis** window and save the changes to the form. When you open the form, the appearance of the form follows the design pattern of the specified form style.

## See also

[How to: Validate the Style of a New Form](how-to-validate-the-style-of-a-new-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

