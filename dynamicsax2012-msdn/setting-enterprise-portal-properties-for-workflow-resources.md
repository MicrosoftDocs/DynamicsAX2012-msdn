---
title: Setting Enterprise Portal Properties for Workflow Resources
TOCTitle: Setting Enterprise Portal Properties for Workflow Resources
ms:assetid: ca3e2899-22d0-44c9-b208-cb08fd007ef8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee677509(v=AX.60)
ms:contentKeyID: 35246140
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Setting Enterprise Portal Properties for Workflow Resources [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In the AOT, several of the workflow resources have properties that are used by Enterprise Portal. You must set these properties for the workflow to operate correctly in Enterprise Portal.

## Approvals

For the Approvals AOT item for your workflow, set the following properties for Enterprise Portal:

  - DocumentWebMenuItem

  - ResubmitWebMenuItem

  - DelegateWebMenuItem

Set the values for these properties to the web action menu items that you created for the workflow actions. If you have not implemented one of the actions for your workflow, you do not need to set its corresponding web menu item property.

## Tasks

For the Tasks AOT item for your workflow, set the following properties for Enterprise Portal:

  - DocumentWebMenuItem

  - ResubmitWebMenuItem

  - DelegateWebMenuItem

Set the values for these properties to the web action menu items that you created for the workflow actions. If you have not implemented one of the actions for your workflow, you do not need to set its corresponding web menu item property.

## Workflow Types

For the Workflow Types AOT item for your workflow, set the following properties for Enterprise Portal:

  - SubmitToWorkflowWebMenuItem

  - DocumentWebMenuItem

  - CancelWebMenuItem

Set the values for these properties to the web action menu items that you created for the workflow actions. If you have not implemented a cancel action for your workflow, you do not need to set the **CancelWebMenuItem** property.

