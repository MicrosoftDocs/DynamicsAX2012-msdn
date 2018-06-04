---
title: Enterprise Portal Two-Phase Create Dialog User Experience Guidelines
TOCTitle: Enterprise Portal Two-Phase Create Dialog
ms:assetid: 30419f01-8d5e-444d-8f3b-fb300f8cb717
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886587(v=AX.60)
ms:contentKeyID: 35267951
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enterprise Portal Two-Phase Create Dialog User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The header creation dialog is used for entity creation tasks where required header information needs to be stored in the database before line items can be added. For example, a header creation dialog is used for **Purchase Requisition** forms, **Sales Order** forms, and **Expense Report** forms. In these cases, a popover dialog is used to first prompt the user for the header information before the full details form is opened. This process is referred to as *two-phase create*.

If both header and lines can be created in the same form without the need to save the header first, then this model does not have to be used. For example, the **Sales Order** form uses a temporary table to create both the header and the lines together in the same form.

The following illustration shows the UI flow for the creation of 1-to-*n* entities in Enterprise Portal.

![UI flow for two-phase create](images/Gg886587.TwoPhaseCreate_01(AX.60).png "UI flow for two-phase create")

Here is an example of a two-phase create header creation dialog.

![New purchase requistion header creation dialog](images/Gg886587.TwoPhaseCreate_02(AX.60).png "New purchase requistion header creation dialog")

## Guidelines

  - A header creation dialog title should use the following format: New \[entity type\].

  - The title of the dialog should start with the word "New”.

  - The size of the dialog should be set to **Small (550 x 412px)**.

  - The dialog should be smaller than the details form that opens after the **Create** button is clicked.

  - The dialog should have a single column layout.

  - The dialog should not contain FastTabs.

  - No more than eight fields should be requested in the dialog.

  - Required header fields should always be placed in the dialog.

  - The dialog should not include an action pane or a toolbar at the top.

  - The content area should provide reasonable defaults.

  - The label of the primary button should be “Create”.

  - The dialog should have a **Cancel** button.

  - After the **Create** button is clicked, the dialog should close and the detail form for the record should open.

  - Constrained input controls with defaults values should be used when possible.

