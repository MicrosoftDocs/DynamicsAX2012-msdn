---
title: Dialog Box User Experience Guidelines
TOCTitle: Dialog Box
ms:assetid: 3e40b010-7d51-4063-bfa8-1986549a8710
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886590(v=AX.60)
ms:contentKeyID: 35267954
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Dialog Box User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A dialog box represents an action or activity that users can explicitly commit or cancel. It is used when a user initiates a specific task or process and the system needs user input on how or whether to proceed.

Dialog box

  
![Dialog box](images/Gg886590.Dialog_01(AX.60).png "Dialog box")Dialog box

## Overview

Dialog boxes can fulfill multiple roles in the system:

  - **Task** dialog boxes ask the user to clarify what options should be used to start a process or activity.

  - **Confirmation** dialog boxes ask the user to confirm actions.

  - **Message** dialog boxes report errors and display information to the user.

  - **Progress** dialog boxes provide progress information.

### Additional examples

Task dialog box

  
![Task dialog box](images/Gg886590.Dialog_03(AX.60).png "Task dialog box")Task dialog box

Confirmation dialog box

  
![Dialog box](images/Gg886590.Dialog_05(AX.60).png "Dialog box")Confirmation dialog box

## Design concepts

Dialog boxes are composed of several standard elements:

  - The **main instruction** identifies the application or system feature that originated the dialog box.

  - The **additional instruction** identifies the user’s objective with the dialog box. It optionally can include an icon.

  - The **content area** displays descriptive information and other controls.

  - **Commit buttons** let the user decide to whether to perform the action or to cancel it. Commit buttons also can include “Don’t show this \<item\> again” controls.

  - **Progressive disclosure** provides access to additional information as needed. This might be advanced information for administrators or support staff that end users wouldn’t understand or which normally would confuse them.

  - The **footnote area** is used for optional additional explanations and help; it typically is targeted at less experienced users.

Dialog box elements

  
![Dialog box](images/Gg886590.Dialog_02(AX.60).png "Dialog box")Dialog box elements

## Guidelines

The default state of the form should follow these rules:

  - The minimum size of a dialog should be 100 pixels in width by 50 pixels in width by 50 pixels in height.

  - Focus should be in the first editable field on the dialog box when the dialog box is first opened.

  - There should be an 11-pixel margin between the dialog box border and all content.

  - There should be a 15-pixel bottom margin between the last control and the commit button area.

A window title should be displayed within the window frame. The window title—as opposed to the main instruction of the dialog box—should accurately describe the command, feature, or program that launched the dialog box.

  - The title should be in sentence case.

  - If the title would be redundant with the main instruction, the title should be “Microsoft Dynamics AX”.

  - The title should be similar to the label of the command used to launch the form.

  - The title should not explain what to do in the dialog box. That is the purpose of the main instruction.

### Specific guidelines

  - A main instruction at the top of the dialog box.

  - The main instruction font size should be 4 points larger than the standard system font.

  - A final period should not be included if the instruction is a statement. If the instruction is a question, a question mark should be included.

  - An additional instruction to the user should be displayed, and it should present information helpful to understanding or using the dialog box. The additional instruction should consist of a complete sentence in sentence case and with ending punctuation.
    
    **Exception:** If the additional instruction merely repeats the main instruction with slightly different wording, do not include it.

<!-- end list -->

  - A content area.
    
      - The content area should contain only the controls required to complete the task.
        
          - All controls should be correctly marked as mandatory.
        
          - Controls should not cause an Infolog to be displayed during validation.
        
          - Constrained input controls should be used (selection lists, check boxes, radio buttons, or command links).
        
          - Reasonable defaults for input should be provided whenever possible.
    
      - A control should be disabled where the state of the control can be changed in the dialog.
    
      - A control should be removed when there is no way for a user to enable it.
    
      - Errors should be handled by:
        
          - Preventing errors whenever possible.
            
            **Example:** The primary commit button should be disabled until it is valid for the user to click it.
        
          - Displaying in-place error messages for validation messages as soon as possible.
        
          - The dialog box should be resizable if it contains a grid in the content area.

<!-- end list -->

  - An optional **More options** section that:
    
      - Shows the user additional or advanced options and information.
    
      - Has the **More options** fields collapsed by default.

<!-- end list -->

  - An optional footnote area (see previous illustration) should:
    
      - Alert the user to an important condition or event.
    
      - Provide information to the user that is not essential to a dialog box’s purpose, but that the user may find helpful in making decisions.
    
      - Display the icon AX ID 11442 ![AXID 11442](images/Gg886590.AXID11442(warning-generic)16x16(AX.60).png "AXID 11442") when alerting the user to an important event.
        

        > [!NOTE]
        > <P>Do not use the error or information standard icons.</P>



<!-- end list -->

  - A commit button area that:
    
      - Contains a button to allow the user to respond to the main instruction.
    
      - Has at least one button marked as the default button of the dialog box.
        
          - The default button should be the safest, most secure response to the main instruction.
        
          - If safety and security are not factors, the button that is most likely to be clicked or that is most convenient for the user should be selected as the default button.
            
            **Exception:** Do not select a destructive response as the default unless there is an easy, obvious way to undo the command. Specific commit button labels that make sense on their own and are a response to the main instruction should be used.
    
      - Has a **Cancel** button as the rightmost button in the commit button area.
    
      - Has buttons that are spaced 5 pixels apart.

A dialog box should adhere to standard guidelines:

  - All labels in the dialog box should be in sentence case.

  - All labels in the dialog box should be spelled correctly.

  - The contents of the dialog box should be aligned by using the fewest vertical gridlines possible.

  - No user experience (UX) guidelines should be violated when security is applied for the various roles that have access to this dialog box.


What a dialog box should not have:

  - A toolbar, the File menu, or an action pane strip at the top of the dialog box.

  - A status bar.

  - A Preview pane.

  - FactBoxes.

## Labels and text

  - The dialog box title should be in sentence case.

  - It should not include a final period if the instruction is a statement. If the instruction is a question, it should include a final question mark.

  - It should display a supplemental instruction to the user composed of a complete sentence in sentence case with ending punctuation.

Follow the [Windows User Experience Interaction Guidelines](http://msdn.microsoft.com/library/aa511258.aspx) for text in a dialog box.

