---
title: 'How to: Create Wizards'
TOCTitle: 'How to: Create Wizards'
ms:assetid: 392f2e5c-f11c-439c-9d38-5885c43561c3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa636654(v=AX.60)
ms:contentKeyID: 35242863
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create Wizards 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Create your own wizard Microsoft Dynamics AX by using the Wizard Wizard.

You'll be prompted to type a name for your wizard during the creation process. The system automatically appends Wizard to the name that you type. For example, if you type FormalOfferReply, the system changes the name to FormalOfferReplyWizard. You can customize the wizard after it is created.

## Wizard Types

Following are the available wizard types:

  - **Standard Wizard** – Helps users perform general tasks. The Report Wizard is an example of a standard wizard.

  - **Default data Wizard** – Helps users create essential default data, such as address information and [Number Sequence Framework](number-sequence-framework.md).
    
    All Default data Wizards are automatically included in the system's Default data Wizard.

## Create a New Wizard

1.  Click **Tools** \> **Wizards** \> **Wizard Wizard**. The **Wizard Wizard** dialog appears.

2.  Click **Next**.

3.  Select the wizard type:
    
      - **Standard Wizard**
        
        –or–
    
      - **Default data Wizard**

4.  Click **Next**.

5.  Type a name for the wizard.

6.  Select the number of required steps, which includes the **Welcome** and **Finished** dialogs.

7.  To change the number of steps after you complete the wizard, add or remove tabbed pages on the wizard form.

8.  Click **Next**, and then click **Finish**.

## Wizards in Projects

The **Wizard Wizard** creates a [private project](morphx-development-projects.md) that references all the items that make up your new wizard. This project is displayed in its own window after you click **Finish** (to create your wizard). The project has the name you typed for your wizard.

To see the **Properties** window for your project, right-click its node, and then choose **Properties**. The **Properties** window title bar shows the name of the project. For example, Project FormalOfferReplyWizard.

Expand the node for your project. Each subnode has the same name as the project. Set focus on a subnode to read its type name, which appears in the title bar of the **Properties** window. The three subnode types are as follows:

  - **Class**

  - **Form**

  - **Menu Item**

To see your project name under these subnodes, expand them in the Application Object Tree (AOT).

## Customize the Wizard

Following is an example of how to customize your newly created wizard. This is most straightforward if you work through its private project window.

1.  Set the title bar text for each tabbed page of your wizard by using one of the following techniques:
    
    1.  The node for your wizard's form has a **Design** node, which has the Caption property. Its value is the text that appears in the title bar of your wizard.
        
        –or–
    
    2.  Add the description method to the wizard's class:
        ```X++  
            static str description()
            {
                return "Formal Offer Reply wizard";
            }
        ```
    If the Caption property and the description method are set to different values, the user sees the Caption property's text.

2.  Navigate to each **TabPage** node, and set the Caption property. This caption appears as the header title immediately below the title bar.

3.  Navigate to each **TabPage** node between the first and last tabbed pages, and then set the HelpText property to provide a brief summary that elaborates on the idea stated in the header. This summary appears below the header text.
    
    The HelpText property is ignored on the first and last tabbed pages.

4.  Add a StringEdit control to the first **TabPage** node under your wizard's form.

5.  Set the control's Text property to a long description of the purpose or intention of the wizard.

6.  Add a StringEdit control to the last **TabPage** node.

7.  Set the control's Text property to describe the action that the wizard performs when the user clicks **Finish**.

8.  Add functionality to the wizard by using the methods in a [wizard class](wizard-classes.md).
    

    > [!NOTE]
    > <P>Test your wizard by running it from the AOT. Execute either the main method or the run method on the wizard's class.</P>

    
    Don't test your wizard by executing the run method on the wizard's form. In some cases, this test has a misleading failure.

## See also

[Enabling Wizard Buttons Depending on User Input](enabling-wizard-buttons-depending-on-user-input.md)

[Guidelines for Wizard Development](guidelines-for-wizard-development.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

