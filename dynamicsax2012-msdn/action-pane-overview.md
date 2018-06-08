---
title: Action Pane Overview
TOCTitle: Action Pane Overview
ms:assetid: a8974ad9-c28a-42f2-b0d6-d6112997936a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg847253(v=AX.60)
ms:contentKeyID: 35249500
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Action Pane Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An action pane is the part of a form that organizes and displays buttons that represent the actions the form supports. An action is a task or operation that occurs when you click an action pane button. Actions enable you to use data from the current form to perform commands, open related forms, or execute custom X++ code.

The following illustration shows an action pane for a form. The action pane includes several action pane tabs, button groups, and buttons.

![Action pane](images/Gg847253.ActionPane01(en-us,AX.60).png "Action pane")

## Action Pane Design

There are two ways you can customize an action pane:

  - You add an action pane to a new form.

  - You add tabs, groups, or buttons to an existing action pane.

To create or update an action pane, you add action pane tabs, action pane button groups, and action pane buttons. You use the tabs and button groups to organize and label a collection of action pane buttons. The first tab of the typical action pane includes groups labeled **New**, **Maintain**, **List**, and **Attachments**.

You use the action pane buttons to perform a specified action. The typical action pane should include buttons that create, edit, and delete records, export to Excel, and handle attachments for records. You can add other buttons that perform additional actions using the records or information that appears in the form.

### ![Gg847253.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg847253.collapse_all(en-us,AX.60).gif")Forms with action panes

The form design guidelines include an action pane across the top of the following types of forms:

  - Details forms

  - Details forms with lines

  - List pages

You can use templates to create details forms and list pages. The template adds the controls for the action pane to the **Design** node of the form. You can customize the action pane by modifying or adding tabs, groups, and buttons. The action pane tabs appear next to the **File** menu.


> [!NOTE]
> <P>The <STRONG>File</STRONG> menu is a system-generated menu that displays commands that you use across all forms. The menu includes clipboard commands, filtering, personalization, tools, and other options.</P>



For more information about form design, see [Form User Experience Guidelines](form-user-experience-guidelines.md) and [List Page User Experience Guidelines](list-page-user-experience-guidelines.md).

### ![Gg847253.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg847253.collapse_all(en-us,AX.60).gif")Organizing action pane tabs, groups, and buttons

When you add or modify an action pane, take time to design the layout of the action pane. The most important task in building an effective action pane is organizing the display of the action pane buttons. The following list provides an overview of the design process for an action pane. For detailed information about how to design an action pane, see [Action Pane User Experience Guidelines](action-pane-user-experience-guidelines.md).

  - Identify who will use the form. Determine the types of tasks you expect users to perform.

  - Group the list of tasks into related activities. You will add an action pane tab for each group of activities. In addition, you will use the action pane tab to label each group of related activities. For example, the **All sales orders** form uses **Sell**, **Manage**, **Pick and pack**, and **Invoice** as the activities for sales orders.
    

    > [!TIP]
    > <P>For activities that are not associated with a specific type of task or are used by many roles, you create an action pane tab labeled <STRONG>General</STRONG>.</P>



  - List the specific actions that are needed for each type of activity. To identify the action pane tab where each action will appear, group actions by the activity that each action supports.

  - Review the actions you mapped to each action pane tab and identify related groups of actions. You will add an action pane button group for each group. In addition, you will use the button group to label each group of related actions. For example, the **Invoice** tab of the **All sales order** form uses **Generate**, **Bill**, **Settle**, and **Journal** to label the groups that appear in the action pane tab.

  - Review the groups in the tab and determine how often you expect to access each group. You should place the most frequently used group on the left side of the tab. This helps provide visibility to these actions when the size of the form decreases.

  - Review the list of actions for each group. You will add a button control that implements each action. For example, the **Customer** group of the **Manage** tab of the **All sales order** form includes buttons for **Check credit limit**, **Prices**, and **Credit card** actions. For more information about action pane buttons, see [How to: Create an Action Pane Button](how-to-create-an-action-pane-button.md).

  - Review the buttons in the group and determine how often you expect to access each button. You should place the most frequently used buttons on the left side of the button group. In addition, the most frequently used buttons must appear as large buttons. This helps provide visibility to these actions when the size of the form decreases. The large buttons on the left are the last buttons to be added to the button group overflow menu.

## Action Pane Controls

The action pane on a form includes several types of controls that organize, label, and execute actions. To view or create an action pane, use the Application Object Tree (AOT) to expand the node for the form, and then click the **Design** node. An action pane includes the following types of controls.

### ![Gg847253.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg847253.collapse_all(en-us,AX.60).gif")Action pane

An action pane is a control that adds an action pane bar to a form. You should not add more than one action pane control to a form. If you use a template to create a form, you will find the template adds the action pane control when the form is created. To see an action pane on the form, the action pane must include at least one action pane tab control.

### ![Gg847253.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg847253.collapse_all(en-us,AX.60).gif")Action pane tab

An action pane tab is a control that displays and labels a collection of related actions. You use an action pane tab to group actions by task or role. In the action pane illustration, the action pane tabs are labeled **Customer**, **Sell**, **Invoice**, **Collect**, **Projects**, **Service**, **Market**, and **General**.

If you use a template to create a form, you will find the template adds a single action pane tab control to the action pane. To see an action pane tab in the action pane, the action pane tab must include a least one action pane button group.

### ![Gg847253.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg847253.collapse_all(en-us,AX.60).gif")Action pane button group

An action pane button group is a control that displays and labels a collection of action pane buttons. Use button groups to put related actions into labeled categories. In the action pane illustration, the action pane button groups are labeled **New**, **Maintain**, **Accounts**, **Transactions**, **Balance**, **Forecast**, **Setup**, **List**, and **Attachments**.

If you use a template to create a form, you might find the template adds button groups to the action pane tab. To see an action pane button group in the action pane tab, the action pane button group must include at least one action pane button.

The action pane button group also manages where buttons are displayed when the client changes size. Each action pane button group includes an overflow menu that enables the button group to display a list of action pane buttons that are not currently visible. When the application workspace changes size, buttons are automatically added or removed from the overflow menu based on several action pane button properties. For more information, see [Action Pane Button Overview](action-pane-button-overview.md).

### ![Gg847253.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg847253.collapse_all(en-us,AX.60).gif")Action pane button

An action pane button is a control that implements a task or operation. You use action pane buttons to open forms, execute commands, or display drop-down menus. In the action pane illustration, examples of action pane buttons are labeled **Customer**, **Edit**, **Balance**, and **Forecast**.

Each button provides several properties that control its appearance and behavior. When a button cannot be used with the data displayed on the form, the button should be disabled. If you use a template to create a form, you might find that the template adds one or more buttons to a button group. For more information about action pane buttons, see [Action Pane Button Overview](action-pane-button-overview.md).

## See also

[Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

