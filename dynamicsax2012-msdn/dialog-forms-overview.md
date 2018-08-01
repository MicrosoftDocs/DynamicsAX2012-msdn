---
title: Dialog Forms Overview
TOCTitle: Dialog Forms Overview
ms:assetid: e82b80c1-fd1c-49b2-80c9-9b26efa9fed3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812217(v=AX.60)
ms:contentKeyID: 44090015
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Dialog Forms Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A dialog form is a small form you use to perform an action or activity that you can explicitly commit or cancel. A dialog form is also named a dialog box. A drop dialog form is a second type of dialog form. A drop dialog form is also named a quick path. You use both the dialog and drop dialog forms to view information and to initiate an action or process.

## Dialog Form Basics

The dialog and drop dialog design patterns enable you to use a small form to show additional information or to confirm an action. You use a dialog or drop dialog form with the following scenarios:

  - You want to view, enter, or update data that is associated with a record that appears in an existing form.

  - You want to initiate a specific action or process from an existing form.

  - You want to specify whether to complete or cancel an action or process.

  - You want to avoid opening a separate form.

  - You want to use a two-phase create scenario where you use the dialog to enter required header information before you add line items.

You typically open a dialog or drop dialog form when you are working with a record in a list page, details form, or another type of form. Many times the information that you add or update in the dialog or drop dialog appears in the list page or details form. As a result, you might want to refresh the list page or details form when the action or process that appears in the dialog form is completed. To learn how to refresh another form when you close the dialog form, see [How to: Refresh the Calling Form](how-to-refresh-the-calling-form.md).

To use a dialog or drop dialog form, you must create a menu item for the form. To create the menu item, you can drag the dialog or drop dialog form on the **Display** node in the **Menu Items** section of the AOT. To open the form, you use that menu item with a menu item button or a drop dialog button.

You can also create and open a dialog form with X++. You can use classes to create and display a dialog form. For information about how to open a dialog form using X++, see [Using Classes to Create a Dialog](using-classes-to-create-a-dialog.md).

## Dialog Form Types

The Microsoft Dynamics AX client supports the following types of dialog forms:

### ![Hh812217.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh812217.collapse_all(en-us,AX.60).gif")Dialog forms

A dialog form is a form you use to initiate an action or process when you are working with a record in an existing list page or task form. You usually use a button to open a dialog form. The dialog form can open in a location that is some distance from the button. A dialog form can show messages and include fields and controls you can use to view, create, or update related information.

A dialog form always includes two buttons. You use the **OK** button to initiate an action or process. You use the **Cancel** button to stop the action or process and close the form.

### ![Hh812217.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh812217.collapse_all(en-us,AX.60).gif")Drop dialog forms

A drop dialog form is a form you use to perform an action against the data in a list page or task form. You use a drop dialog button in the action pane or action pane strip to open the form. A drop dialog form always opens next to the button. Typically, you use a drop dialog form to explicitly obtain approval before initiating an action. A drop dialog form can show messages and include fields and controls you use to view, create, or update related information.

A drop dialog form has one **OK** button that you use to initiate the specified action. If you click outside the drop dialog form, the form closes and the action is canceled. As a result, a drop dialog form should not have a **Cancel** button.

## Dialog Form Design

To create a dialog or drop dialog form you use the **Forms** node of the AOT. A dialog form and a drop dialog form include the same design elements except that a drop dialog form has the one **OK** button. The following illustration shows the design elements of a dialog form.

![Dialog form design elements](images/Hh812217.Client_DialogFormDesign(en-us,AX.60).png "Dialog form design elements")

For more information about dialog form and drop dialog form design, see [Dialog Box User Experience Guidelines](dialog-box-user-experience-guidelines.md) and [Drop Dialog User Experience Guidelines](drop-dialog-user-experience-guidelines.md).

### ![Hh812217.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh812217.collapse_all(en-us,AX.60).gif")Templates

To create a new form, you use the **Dialog** or **DropDialog** template. The template populates the **Style** property in the **Design** node and adds several controls that are required for the specified design pattern. In addition, the template configures many property values for you so that you can focus on adding fields and controls to the form. For information about how to use a template, see [How to: Create a Dialog Form](how-to-create-a-dialog-form.md).

### ![Hh812217.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh812217.collapse_all(en-us,AX.60).gif")Data Sources

To add values to the controls that appear on the form you add a data source to the form. You can use one of the following types of data sources for a dialog or drop dialog form:

  - You can add one or more tables to the **Data Sources** node of the form. To add fields to the form, you drag fields from the tables onto the content area of the form. For information about how to use a table as a data source for a form, see [How to: Add a Field Group to a Form](how-to-add-a-field-group-to-a-form.md).

  - You can use Extended Data Types (EDT) with individual controls to show field values on a dialog or drop dialog form. To use EDTs, you add the control and then use the **ExtendedDataType** property of the control to specify the EDT. The control and EDT must have the underlying data type. For more information about how to use an EDT with a dialog or drop dialog form, see [How to: Create a Dialog Form](how-to-create-a-dialog-form.md).

### ![Hh812217.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh812217.collapse_all(en-us,AX.60).gif")Task Instruction

The task instruction group provides one or two lines of text that help you use the dialog form. The task instructions will appear at the top of the content pane. The task instruction group includes the following text elements:

  - A main instruction is a line of text that appears as a heading at the top of the content pane. You use the main instruction to describe the task. Every dialog form must have a main instruction.

  - A supplemental instruction is a line of plain text that appears under the main instruction. You use the supplemental instruction to provide additional guidance about how to complete the task. Supplemental instructions are optional and you can decide not to include a supplemental instruction. If you add a supplemental instruction, always use complete, concise sentences that include ending punctuation.

To add task instructions, you add a group control and two static text controls to the tab page in the **Design** node of the form. You should use labels to populate the **Text** property of the static text controls. The labels should specify the text you want to appear in the static text controls. To format the text, use the **Style** property of the group control and the static text controls. For information about how to add a task instruction group, see [How to: Create a Dialog Form](how-to-create-a-dialog-form.md).

### ![Hh812217.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh812217.collapse_all(en-us,AX.60).gif")Content Area

The content pane is the section of the form under the task instructions. The content pane includes the fields and controls you use to view, create, update, or delete a record.

### ![Hh812217.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh812217.collapse_all(en-us,AX.60).gif")Show More Fields

The more options section is an optional group of controls you can use to support additional or advanced scenarios. When the form opens, the fields in the more options section should be hidden. To see the hidden fields and controls, you click the **Show more fields** button. You typically add a more options section when you want the form to support advanced scenarios. For information about how to add fields to the more options section, see [How to: Hide fields on a Dialog Form](how-to-hide-fields-on-a-dialog-form.md).

### ![Hh812217.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh812217.collapse_all(en-us,AX.60).gif")Buttons

A dialog or drop dialog form always includes at least one button that lets you respond to the main instruction. By default, the button includes the **OK** label. However, you can change the label to use a word or phrase that makes sense as a response to the main instruction. You always use the **OK** button to initiate the specified action or process.

In addition, you must specify one button as the default button. The default button should be a safe, secure response to the main instruction. If safety and security are not factors, the button that is most likely to be clicked should be selected as the default button.


> [!WARNING]
> <P>Do not select a destructive response as the default button unless there is an easy, obvious way to undo the completed action or process.</P>



A dialog form always includes a **Cancel** button to the right of the **OK** button. You use the Cancel button to stop the action or process and to close the dialog form.

### ![Hh812217.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh812217.collapse_all(en-us,AX.60).gif")Footnote Area

The footnote area is an optional section of the form you use to show text messages. You can use this section to provide guidance or to show a message about an important condition or event. You can also use the footnote are to provide information that is not required but helps you decide how to continue. You can include icons in the footnote area. For example, you can use image resource with the ID of 11442 to identify the message as an alert. For more information about how to add a footnote message to a dialog form, see [How to: Add a Footnote Section to a Dialog Form](how-to-add-a-footnote-section-to-a-dialog-form.md).

### ![Hh812217.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh812217.collapse_all(en-us,AX.60).gif")Permissions

To secure a dialog form or a control that is used on the form, you use the Microsoft Dynamics AX role-based security system. Role-based security uses permissions and roles to restrict access to forms, controls, and data records. For more information about the role-based security system, see [Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md).

In the AOT, each form includes a **Permissions** node. You use **Permissions** to specify user rights for controls, tables, and methods that are associated with the form. For information about how to use security permissions and roles, see [Security Permissions Properties for a Form](security-permissions-properties-for-a-form.md).

## Development Tools

To create a dialog or drop dialog form, you use the same techniques that you use when you create other Microsoft Dynamics AX forms. The AOT provides the tools that you use to create or modify the form. In addition, you can use the AOT to specify the template, add the form data source, and add controls to the form. For more information about how to create a dialog form or drop dialog form, see [How to: Create a Dialog Form](how-to-create-a-dialog-form.md).

As you create a dialog or drop dialog form, you can use the form style best practice tool to validate the form. You can use the tool to identify differences between the form and the template for the specified type of form. Periodically run the form style best practice tool to check the form for compliance with best practice guidelines for the dialog or drop dialog forms. For information about how to use the form style best practice tool, see [How to: Validate the Style of a New Form](how-to-validate-the-style-of-a-new-form.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

