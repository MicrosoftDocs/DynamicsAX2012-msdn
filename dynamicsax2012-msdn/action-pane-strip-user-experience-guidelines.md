---
title: Action Pane Strip User Experience Guidelines
TOCTitle: Action Pane Strip
ms:assetid: 9c6c3b52-fcde-4b84-a408-bb7c563f1526
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886602(v=AX.60)
ms:contentKeyID: 35267966
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Action Pane Strip User Experience Guidelines [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An *action pane strip* is a light version of an action pane. You use an action pane strip when a form does not have enough actions to justify a full action pane. In addition, an action pane strip enables you to put relevant actions close to records and data fields.

## Design concepts

Compared to a full action pane, an action pane strip:

  - Scales better to a few commands.

  - Takes up less room.

  - Is easier to design and code.

  - Gives the user visual clues as to what the major functions of the form are.

An action pane strip can be used for any of the following objects, depending on the scope of the actions:

  - An entire form.

  - A FastTab.

  - A grid. (This can also be a grid on a FastTab.)
    
    ![Callout of action pane strips](images/Gg886602.ActionPaneStrip_01(AX.60).png "Callout of action pane strips")

### Action pane strip for an entire form

The action pane strip can be used at the top of the forms listed in the [Form User Experience Guidelines](form-user-experience-guidelines.md) section. When used at the top of a form, the action pane strip will be next to the **File** menu.

The **File** menu displays commands common across the entire application, such as clipboard commands, common filtering, personalization, tools, and options. The **File** menu and the content of the menu are controlled in Microsoft Dynamics AX by the kernel. The **File** menu and **Help** icon are automatically placed on an action pane strip.

When used at the top of a form, an action pane strip will optionally have **New** and **Delete** as standard actions when the form supports creating and deleting records.

![Action pane strip at the top of a form](images/Gg848145.ActionPaneStrip_02(en-us,AX.60).png "Action pane strip at the top of a form")

### Action pane strip for a FastTab

An action pane strip can be used on a FastTab or a tab to host actions that apply only to the contents of the tab. This is helpful to the user when the action may be ambiguous at the top of the form, or if the user would have trouble finding the action at the top.

![Action pane strip in a FastTab](images/Gg886602.ActionPaneStrip_03(AX.60).png "Action pane strip in a FastTab")

### Action pane strip above a grid

When used above of a grid, the action pane strip provides actions that are contextually relevant to the FastTab. When applicable, the first actions should be **Add**, **Remove**, and **Details**.

![Action pane strip above a grid](images/Gg886602.ActionPaneStrip_04(AX.60).png "Action pane strip above a grid")

## Guidelines

For the guidelines that you should follow for a simple list and details action pane strip, see the [Simple List and Details User Experience Guidelines](simple-list-and-details-user-experience-guidelines.md) topic.

For the guidelines that you should follow for a simple list action pane strip, see the [Simple List User Experience Guidelines](simple-list-user-experience-guidelines.md) topic.

For the guidelines that you should follow for a FastTab action pane strip in a details form, see the [Details Form User Experience Guidelines](details-form-user-experience-guidelines.md) topic.

## Labels and text

  - An action pane strip should have a concise label.

  - Names on an action pane strip should be specific, verb-based names. The verb should be omitted if it is *Create*, *Show*, *View*, or *Manage*.

  - Actions that apply to a single object should use singular nouns. Otherwise, plural nouns should be used.

  - Menu item names should be based on user goals and tasks, not on technology.

  - A tooltip should be used for command buttons and menu buttons.

  - Button names should be in sentence case.

  - The following names should be used only for the stated purpose:
    
      - *Options* – To display program options.
    
      - *Personalize* – To display a summary of commonly used personalization settings.
    
      - *Properties* – To display the Properties window of an object.
    
      - *Details* – To display additional details about an object.

