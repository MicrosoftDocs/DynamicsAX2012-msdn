---
title: Drop Dialog User Experience Guidelines
TOCTitle: Drop Dialog
ms:assetid: 76e77660-d670-450c-8d6e-b6136d82dee3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886598(v=AX.60)
ms:contentKeyID: 35267962
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Drop Dialog User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A drop dialog—also known as a quick path—provides a quick way for a user to perform an action. It should feel as lightweight to use as a menu.

Example of a drop dialog

  
![An example of a drop dialog](images/Gg886598.QuickPath_01(AX.60).png "An example of a drop dialog")Example of a drop dialog

Example of another drop dialog

  
![An example of a drop dialog](images/Gg886598.QuickPath_02(AX.60).png "An example of a drop dialog")Example of another drop dialog

## Overview

Drop dialogs are attached to an action pane or an action pane strip. They are used to:

  - Clarify the user’s intent before running a task.

  - Enter header information that is required for line items to be added (in two-phase create scenarios).

  - Confirm actions on an action pane or action pane strip.

  - Display additional status information to a user.

A drop dialog has click behavior like a menu; if the user clicks away from the drop dialog, the drop dialog closes and the action is canceled. For that reason, the drop dialog should have only a button to commit to the instruction; it should not have a **Cancel** button.

### Drop dialog elements

A drop dialog is composed of the following elements:

  - Main instruction (optional)

  - Additional instructions (optional)

  - Content area

  - Progressive disclosure (optional)

  - Commit button

  - Footnote area (optional)

Elements of a drop dialog

  
![Elements of a drop dialog](images/Gg886598.QuickPath_03(AX.60).png "Elements of a drop dialog")Elements of a drop dialog

## Design concepts

Drop dialogs are an efficient and simple mechanism for a user to perform an action against the data in a list or in a task form. Drop dialogs reduce the window management of a full task page and at the same time are very efficient for users.

Dialog boxes are often used when an application needs to gather additional information from a user or to confirm an action before continuing. Frequently, these dialog boxes interrupt the flow of the user’s process, and they often open some distance from the place where the activity that initiated the dialog occurred. Drop dialogs can solve these problems. They open near the point of initiation and allow users to stay in the flow of their process.

Drop dialogs also help to improve efficiency for people who use the mouse frequently. Mouse users often click imprecisely. They might click the wrong button because the correct button has a small click target, or because their hand twitches, or because they click too quickly. If the user clicks the wrong button and it opens a dialog box, the user must now dismiss the dialog box by clicking its **Cancel** button, which might be some distance away. But clicking the wrong button is less of a problem if drop dialogs are used. That is because drop dialogs are easier to close than dialog boxes. A drop dialog will close if a user clicks away from it. So, if a user clicks the wrong button and the wrong drop dialog opens, the user only needs to click the correct button, and that one action will both close the wrong drop dialog and open the correct one.

### Use of a drop dialog in a two-phase create process

Drop dialogs may be used in a two-phase create. The first phase gathers enough information to create the document. The second phase gathers the rest of the information.

![Using a drop dialog in a two-phase create process](images/Gg886598.QuickPath_04(AX.60).png "Using a drop dialog in a two-phase create process")

## Guidelines

Always use a drop dialog instead of a dialog box when these conditions exist:

  - There are seven or fewer fields.
    
      - Defaults should be provided for all of the fields where possible.

  - The user can enter the information quickly.

  - Minimal field validation is required.

  - There are no buttons that open additional child dialog boxes.

  - There is no editable grid (select-only grids are allowed).

The default state of the form should follow these rules:

  - The minimum size of a drop dialog should be 100 pixels in width by 50 pixels in height.

  - The maximum size of a drop dialog should be 600 pixels in width by 400 pixels in height.

  - The drop dialog should be smaller than the form that it is called from.

  - Focus should be in the first editable field on the drop dialog when it is first opened.

  - There should be an 11-pixel margin between the drop dialog border and all content.

  - There should be a 15-pixel bottom margin between the last control and the commit button area.

### Specific guidelines

  - A drop dialog should have a main instruction at the top.
    
      - The main instruction should be used to explain concisely what the user should do in the drop dialog. The instruction should be a specific statement, an imperative direction, or a question. Good instructions communicate the user’s objective with the drop dialog rather than focusing purely on the mechanics of manipulating it.
    
      - The main instruction font size should be 4 points larger than the standard system font.
    
      - The main instruction should be displayed in the color R:0, G:51, B:153.
    
      - A final period should not be included if the instruction is a statement. If the instruction is a question, a question mark should be included.
    
      - Besides the main instruction, an additional instruction to the user should be displayed, and it should present additional information helpful to understanding or using the drop dialog. The additional instruction should consist of a complete sentence in sentence case and with ending punctuation.
        
        **Exception:** If the additional instruction merely repeats the main instruction with slightly different wording, do not include it.

<!-- end list -->

  - A drop dialog should have a content area.
    
      - The content area should contain only the required controls to complete the task.
        
          - All controls should be correctly marked as mandatory.
        
          - Controls should not cause an Infolog to be displayed due to entry errors.
        
          - Constrained input controls should be used (selection lists, check boxes, radio buttons, or command links).
    
      - Reasonable defaults for input should be provided whenever possible.
    
      - Controls should be disabled where the state of the control can be changed on the drop dialog.
    
      - Controls should be removed when there is no way for a user to enable it.

<!-- end list -->

  - A drop dialog should have an optional **More options** section that:
    
      - Shows the user additional or advanced options and information.
    
      - Has the **More options** fields collapsed by default.

<!-- end list -->

  - A drop dialog should have an optional footnote area (see previous illustration) that:
    
      - Alerts the user to important conditions or events.
    
      - Provides information to the user that is not essential to the drop dialog purpose, but that the user may find helpful in making decisions.
    
      - Displays the ![Alert icon](images/Gg886598.Alert_icon(AX.60).png "Alert icon") icon when alerting the user to an important event.
        

        > [!NOTE]
        > <P>The error or information standard icons should not be used.</P>



<!-- end list -->

  - A drop dialog should have a commit button area that:
    
      - Contains a button to allow the user to respond to the main instruction.
    
      - Has at least one button marked as the default button of the drop dialog.
        
          - The label of the default button should be a verb that implements the action described in the main instruction. For example, if the main instruction is “Create new product,” the button label would be “Create”. If there is no appropriate verb for the button, use “OK”.
        
          - The default button should be the safest, most secure response to the main instruction.
        
          - If safety and security are not factors, the button that is most likely to be clicked or that is most convenient for the user should be selected as the default button.
            
            **Exception:** Do not select a destructive response as the default unless there is an easy, obvious way to undo the command.
    
      - The commit button area should have specific commit button labels that make sense on their own and are a response to the main instruction.
    
      - The commit button area should have buttons spaced 5 pixels apart.

### A drop dialog should not have

  - A toolbar, a **File** menu, or an action pane strip anywhere in the drop dialog.

  - A status bar.

  - A **Cancel** button.
    

    > [!NOTE]
    > <P>The drop dialog should behave like a menu. That is, clicking outside of the drop dialog will cancel the operation and close the drop dialog.</P>



  - A Preview pane.

  - FactBoxes.

