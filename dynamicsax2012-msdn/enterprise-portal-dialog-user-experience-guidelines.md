---
title: Enterprise Portal Dialog User Experience Guidelines
TOCTitle: Enterprise Portal Dialog
ms:assetid: cff7555b-0d0e-484a-9fc5-1c3d661da3b3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886607(v=AX.60)
ms:contentKeyID: 35267971
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enterprise Portal Dialog User Experience Guidelines [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Enterprise Portal uses the following three dialogs to request more information from the user:

  - Simple task dialog

  - Workflow dialog

  - Confirmation dialog

## Guidelines

This section includes both general and specific guidelines for simple task, workflow, and confirmation dialogs. It also includes guidelines about what these dialogs should not have.

### General guidelines

  - Dialogs should be used when the system needs to request additional information about how a specific task or processing step should proceed.

  - The size of a dialog should be set to **Small (550 by 412 pixels)**.

  - Focus should be on the first editable field when the dialog is opened.

  - The dialog title should be similar to the text of the label used to open the form.

  - The dialog title should start with a verb.

  - The dialog title should be in sentence case.

  - The dialog title should not explain what to do in the dialog—that is the purpose of the main instruction.

  - The dialog should have a main instruction at the top.

  - The content area should contain only the controls required to complete the task.

  - All required controls in the content area should be marked as mandatory.

  - The content area should use constrained input controls (selection lists, check boxes, radio buttons, or command links).

  - The content area should provide reasonable defaults.

  - The content area should disable a control when its state is not valid.

  - The content area should not have controls with which the user cannot interact.

  - The dialog should use a one-column layout of fields.

  - The dialog should use an Infolog for validation.

  - The commit button area (lower right) should contain a button that allows the user to respond to the main instruction.

  - The commit button area should have a button marked as the default button that allows the user to pick the safest or most likely response.

  - The commit button label should make sense on its own or should be a response to the main instruction.

  - The **Cancel** button should be the rightmost button in the commit button area.

### Specific guidelines

#### For a simple task dialog

Example of a simple task dialog

  
![Simple task dialog](images/Gg886607.EPDialog01(AX.60).png "Simple task dialog")Example of a simple task dialog

  - A simple task dialog should be used for simple tasks where the user needs to specify a few options in order to complete the task. In the example above, the user has initiated the task of adding items to an existing order, and the system needs to prompt the user which order to add them to.

  - The dialog should have **OK** and **Cancel** as commit buttons.

  - The dialog should not include an action pane or toolbar.

#### For a workflow dialog

Example of a workflow dialog

  
![Workflow dialog](images/Gg886607.EPDialog02(AX.60).png "Workflow dialog")Example of a workflow dialog

  - A workflow dialog should be used to prompt the user for any additional information required to complete a workflow action, for example, **Approve**, **Reject**, and **Delegate**.

  - The dialog should not have an **OK** button.

  - The dialog should have no more than six fields.

#### For a confirmation dialog

Example of a confirmation dialog

  
![Confirmation dialog](images/Gg886607.EPDialog03(AX.60).png "Confirmation dialog")Example of a confirmation dialog

  - A confirmation dialog should be used to provide the user with a way to confirm a delete action.

  - The dialog should ask a question for the user to answer.

  - The dialog should have a warning icon.

  - The dialog should have a **Yes** and a **No** button.

### What a simple task, workflow, or confirmation dialog should not have

  - A toolbar or action pane at the top

  - A Preview pane

  - FactBoxes

## Labels and text

### For a simple task dialog

  - The simple task dialog title should match the name of the action that opened the dialog.

### For a workflow dialog

  - The workflow dialog title should have the following format: \[Action verb\] \[Record ID\]. It should match the name of the action that opened the dialog.

  - The label of the first button should be a verb that addresses the action being completed, such as “Submit,” “Publish,” or “Approve.”

  - The label of the second button should be “Cancel.”

### For a confirmation dialog

  - A confirmation dialog title should have the following format: \[Action verb\] \[Entity type\].

  - The dialog should provide an identifying line for the record in the following format: \[ID\] - \[Name\].

