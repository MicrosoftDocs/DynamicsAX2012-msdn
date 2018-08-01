---
title: Page Interaction Patterns
TOCTitle: Page Interaction Patterns
ms:assetid: 13536d50-6d7c-4eb3-a293-8788d91aa4a1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812491(v=AX.60)
ms:contentKeyID: 44090277
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Page Interaction Patterns [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The page types in Enterprise Portal work together to provide a consistent experience for the user. Some of the pages are displayed in the main browser window, although other pages are displayed in modal dialogs. The following diagrams describe the page interaction patterns for several common scenarios in Enterprise Portal.

## View and Edit

In this pattern, a list page displays entities of a specific type. The View button in the action pane for the list page opens the entity overview page. The entity overview page displays the details for the selected entity. The entity overview page contains an action pain that includes the Edit action. When the user clicks the Edit action, a task page opens that allows the entity to be edited.

![View and Edit Details](images/Hh812491.EP_PagePatternViewEdit(AX.60).gif "View and Edit Details")

## Direct Edit

In this pattern, a list page displays entities of a specific type. The Edit action in the action pane for the list page opens the task page that allows the entity to be edited.

![Direct Edit](images/Hh812491.EP_PagePatternDirectEdit(AX.60).gif "Direct Edit")

## Edit with Additional Details

In this pattern, a list page displays entities of a specific type. The Edit button in the action pane for the list page opens a task page that allows the entity to be edited. A button on the task page opens another task page that allows for additional details for the entity to be edited. When the user has completed editing the additional details, they are returned to the task page used to edit the entity.

![Edit with Additional Details](images/Hh812491.EP_PagePatternEditWithDetails(AX.60).gif "Edit with Additional Details")

## View and Edit Details

In this pattern, a list page displays entities of a specific type. The View button in the action pane for the list page opens the entity overview page. The entity overview page contains a button to display details in an additional page. The additional page contains an Edit action that can be used to edit the details that are displayed. When the user has completed editing the details, they are returned to the entity overview page for the selected entity.

![View and Edit Details](images/Hh812491.EP_PagePatternViewEditDetails(AX.60).gif "View and Edit Details")

## Two-phase Create

In this pattern, a list page displays entities of a specific type. The New button in the action pane for the list page opens a task page that lets the user create the header information for the entity. After the user finishes creating the header, a second page is opened that allows the detail information for the entity to be created.

![Two-phase Create](images/Hh812491.EP_PagePatternTwoPhaseCreate(AX.60).gif "Two-phase Create")

## Create and Submit to Workflow

In this pattern, a list page displays entities of a specific type. The New button in the action pane for the list page opens a task page that lets the user create the header information for the entity. After the user finishes creating the header, a second page is opened that lets the user create the detail information for the entity. If workflow is enabled, the entity overview page is displayed, which displays the workflow bar that allows the entity to be submitted to workflow. See [Workflow in Enterprise Portal](workflow-in-enterprise-portal.md) for more information.

![Create and Submit to Workflow](images/Hh812491.EP_PagePatternCreateSubmitWorkflow(AX.60).gif "Create and Submit to Workflow")

In some cases, a simplified version of this pattern is used. In that pattern, the user submits the entity to workflow from the list page or from the entity overview page.

## See also

[List Page Reference](list-page-reference.md)

[Entity Overview Page Reference](entity-overview-page-reference.md)

[Task Page Reference](task-page-reference.md)

