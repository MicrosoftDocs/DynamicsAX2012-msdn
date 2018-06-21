---
title: FastTabs
TOCTitle: FastTabs
ms:assetid: 7a864c55-7eeb-4edd-8c24-e4d57349d894
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528505(v=AX.60)
ms:contentKeyID: 37835253
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# FastTabs [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A FastTab is an expandable and collapsible area of a form. FastTabs enable you to quickly customize the appearance of a form. You can expand one or more FastTabs that show additional fields you can work with on the form. In addition, you can collapse FastTabs to hide fields that are not relevant to you.

## FastTab Design

You use FastTabs to provide an efficient way to view and enter information for a record. A FastTab differs from other types of tabs because you can view the contents of more than one FastTab that appear on the form. This enables you to scroll from top to bottom and view the form like a document.

To support the document view, FastTabs appear in the details views of several types of forms. You can add FastTabs to the following types of forms:

  - Details forms

  - Dialog forms

  - Simple list and details forms

  - Table of contents forms

The form style templates you use to create these types of forms include a hierarchy of group, tab, and tab page controls to construct the details view. You can add a FastTab to a form by adding tab pages to an existing tab or by adding a new tab and tab pages.

You should use FastTabs to group fields based on activity, similar to the way that tabs are organized on an action pane. In addition, you should organize the FastTabs on a form to support the work process. For example, the first FastTab in the **Sales order** form is named **Sales order header** and shows detailed information about a customer. The second FastTab is named **Sales order lines** and shows the lines associated with the specified customer.

You should not use FastTabs to replace all existing tabs. For example, you should use regular tabs for a form where you do not have to see more than one tab at the same time or where the content is complex. For more FastTab design guidelines, see [FastTab User Experience Guidelines](fasttab-user-experience-guidelines.md).

### ![Hh528505.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh528505.collapse_all(en-us,AX.60).gif")Title

You use the FastTab title area to label each FastTab that appears on the form. The title remains visible when the FastTab is collapsed. The label in the title should describe the contents of the FastTab. You should supply a title that helps you decide whether to expand and view the FastTab.

### ![Hh528505.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh528505.collapse_all(en-us,AX.60).gif")Summary Fields

A summary field is a field value that appears in the FastTab title. You use summary fields to provide quick access to important data values that build context for the record. In addition, summary fields remain visible when the FastTab is collapsed. This enables you to view important information even when the FastTab is collapsed.

The summary fields include the values of the first five fields from the **AutoSummary** field group that appear on the form. However, you can customize the summary fields to add or remove individual field values. Summary fields are optional and you can prevent the FastTab from displaying any summary field values.

### ![Hh528505.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh528505.collapse_all(en-us,AX.60).gif")Action Pane Strip

A FastTab can include an action pane strip. You add an action pane strip to a FastTab when you want to add buttons that represent additional actions. The buttons in the action pane strip should show actions that supplement the actions that are available in the action pane or action pane strip of the form. For more information about the action pane strip, see [Action Pane Strip Overview](action-pane-strip-overview.md).

An action pane strip for a FastTab is optional. You can create FastTabs that do not have a separate action pane strip for that tab.

## FastTab Controls

To create a FastTab you use a tab, tab pages, and other controls. If you use a form design template to create a form, many of the controls and required property values are added for you. There are two ways to add a FastTab to a form:

  - You add a new FastTab to a form. You must add a tab control and one or more tab page controls in the **Design** node of the form.

  - You add a FastTab to a collection of existing FastTabs. You add a tab page control to an existing tab control in the **Design** node of the form.

For more information about how to add a FastTab to a form, see [How to: Add FastTabs to a Form](how-to-add-fasttabs-to-a-form.md).

### ![Hh528505.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh528505.collapse_all(en-us,AX.60).gif")Tab Control

To add a FastTab to a form, you must have a **Tab** control. A tab control is a container where you can add one or more tab page controls. To specify that the tab appear as a FastTab, you set the **Style** property of the **Tab** control to **FastTabs**.


> [!TIP]
> <P>You can convert an existing tab to a FastTab by changing the <STRONG>Style</STRONG> property of the tab control to <STRONG>FastTabs</STRONG>.</P>



You should add a tab to the form only if there are no existing FastTabs. If you use a form template to create the form, you typically do not have to add any additional tabs to the form.

### ![Hh528505.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh528505.collapse_all(en-us,AX.60).gif")TabPage Control

To organize the fields that appear in a FastTab, you use one or more **TabPage** controls. A tab page control is a container where you can add controls that show field values. A form with FastTabs should have at least two tab pages but should not include more than twelve.

You use tab pages to organize and label the fields that appear in the FastTab. You use the **Caption** property of the **TabPage** control to specify the label that appears as the title of the FastTab. In addition, you use the **Columns** property to specify the layout of fields and groups. Typically, a FastTab has two columns but you can use three columns.

### ![Hh528505.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh528505.collapse_all(en-us,AX.60).gif")Field and Grid Controls

To populate a FastTab you add fields or field groups to a **TabPage** control. You add fields or field groups to the FastTab by dragging fields or field groups from the form data source to the tab page. You should limit the number of groups in a FastTab to between two and four field groups.

You can add a **Grid** control to a FastTab. Typically, a grid that appears in a FastTab should show five lines. However, a grid that shows line items should display eight lines.

To specify whether a field value appears as a summary field, you use the **FastTabSummary** property of the control. Summary fields are displayed without labels. As a result, you should not have more than one field of the same type in the summary fields.

If you want to use a field from a reference group control in the summary fields you must explicitly add the referenced data source to the **Data Sources** node of the form. You can then drag the field you want to use on to the tab page, and set the **FastTabSummary** property of the control to **Yes**.

## See also

[How to: Add a FastTab to a Details Form](how-to-add-a-fasttab-to-a-details-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

