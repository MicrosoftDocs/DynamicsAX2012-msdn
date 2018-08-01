---
title: Workflow Provider Interfaces
TOCTitle: Workflow Provider Interfaces
ms:assetid: f6961d46-7036-4037-9deb-572d391c436d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528513(v=AX.60)
ms:contentKeyID: 37835260
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Provider Interfaces [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Each workflow provider instance implements a provider class that defines how the provider works. The provider class must implement the methods for the interface that defines each provider type. The following sections describe the interfaces that must be implemented for each workflow provider type.

## Hierarchy Assignment Provider

You can use a hierarchy assignment provider to provide a specific end item, when a particular starting item is provided. Microsoft Dynamics AX workflow provides the [WorkflowLimitHierarchyProvider Class](https://msdn.microsoft.com/en-us/library/gg813881\(v=ax.60\)) that returns a user ID based the organizational hierarchy set up in Microsoft Dynamics AX

The [WorkflowLimitHierarchyProvider Class](https://msdn.microsoft.com/en-us/library/gg813881\(v=ax.60\)) implements the [WorkflowHierarchyProvider Interface](https://msdn.microsoft.com/en-us/library/gg831524\(v=ax.60\)) which contains the following methods:

  - [WorkflowHierarchyProvider.getDataSource Method](https://msdn.microsoft.com/en-us/library/gg831520\(v=ax.60\))

  - [WorkflowHierarchyProvider.getNextNode Method](https://msdn.microsoft.com/en-us/library/gg831521\(v=ax.60\))

  - [WorkflowHierarchyProvider.getNodeDataType Method](https://msdn.microsoft.com/en-us/library/gg831522\(v=ax.60\))

  - [WorkflowHierarchyProvider.convertToNodeDataType Method](https://msdn.microsoft.com/en-us/library/gg831518\(v=ax.60\))

  - [WorkflowHierarchyProvider.convertUserIdToNodeDataType Method](https://msdn.microsoft.com/en-us/library/gg831519\(v=ax.60\))

  - [WorkflowHierarchyProvider.getSupportedDataType Method](https://msdn.microsoft.com/en-us/library/gg831523\(v=ax.60\))

The WorkflowHierarchyProvider.getDataSource method is called when an approval or task is started to resolve the filtering and stop conditions defined in the configuration user interface.

The WorkflowHierarchyProvider.getNextNode method is called when an approval or task is started to retrieve the identity of the user in the hierarchy that should be assigned a work item.

The WorkflowHierarchyProvider.getNodeDataType method is called when the approval or task is started to return an object of the type the hierarchy provider expects as input. Since each hierarchy provider implementation can have a different input type, the input type is based on the type of hierarchy. For example, an organizational hierarchy provider might return an employee, whereas a product hierarchy provider might return a product ID.

The WorkflowHierarchyProvider.convertToNodeDataType method is called at runtime when an extended data type value must be converted to a data type that the hierarchy supports as the start node.

The WorkflowHierarchyProvider.convertUserIdToNodeDataType method is called at runtime to convert a user ID value to a data type that the hierarchy supports. When a reserved word is selected, such as workflow owner or workflow originator, a user ID is passed.

The WorkflowHierarchyProvider.getSupportedDataType method is called to return the set of supported extended data types that the hierarchy provider can convert into node data types. The set is displayed as a drop-down list in the user interface.

## Due Date Calculation Provider

You can use a due date calculation provider to determine a specific due date for a task or approval based on a specified start date. Microsoft Dynamics AX workflow provides the [WorkflowWorkCalendarDueDateProvider Class](https://msdn.microsoft.com/en-us/library/gg815397\(v=ax.60\)) that returns the required completion date of the workflow work item.

The due date provider can use the company calendar defined in **Organization administration** to resolve a time span for a task or approval into a date that takes non-workdays into consideration. Any holidays or non-working days specified in the calendar setup in **Organization administration** \> **Calendars** are calculated into the approval completion date.

The [WorkflowWorkCalendarDueDateProvider Class](https://msdn.microsoft.com/en-us/library/gg815397\(v=ax.60\)) implements the [WorkflowDueDateProvider Interface](https://msdn.microsoft.com/en-us/library/gg830948\(v=ax.60\)) which contains the following methods:

  - [WorkflowDueDateProvider.getCalendarTokens Method](https://msdn.microsoft.com/en-us/library/gg830947\(v=ax.60\))

  - [WorkflowDueDateProvider.resolve Method](https://msdn.microsoft.com/en-us/library/gg830949\(v=ax.60\))

  - [WorkflowDueDateProvider.resolveNonUser Method](https://msdn.microsoft.com/en-us/library/gg830952\(v=ax.60\))

The WorkflowDueDateProvider.getCalendarTokens method is called from the workflow configuration user interface to enable the user to select a calendar from the list of supported calendars. This method provides a list of the calendars IDs from a calendar system.

The WorkflowDueDateProvider.resolve method is called when a task or approval step is started to determine the completion date of the step. For example, the workflow configuration is set up to require a requisition approval within 10 work days. When the approval step or task is started, the due date provider's resolve method is called to return the actual due date. The calendar ID specified in the configuration user interface is passed into this method in order to resolve the time span for a workflow work item into the completion due date for the work item based on the calendar ID.

The WorkflowDueDateProvider.resolveNonUser method is called to determine the due date for the workflow element itself. In the configuration user interface, this is the due date for **Set a time limit for the workflow element**. This method is implemented when you do not have a user to determine the maximum duration for a work item.

## Participant Assignment Provider

You can use a participant assignment provider to provide a list of users from any role abstraction, such as a user group or security role. Microsoft Dynamics AX workflow provides the [WorkflowUserGroupParticipantProvider Class](https://msdn.microsoft.com/en-us/library/gg815310\(v=ax.60\)) that returns a list of users based on a Microsoft Dynamics AX user group. Microsoft Dynamics AX workflow also provides the [WorkflowRoleParticipantProvider Class](https://msdn.microsoft.com/en-us/library/gg813937\(v=ax.60\)) that returns a list of users based on a Microsoft Dynamics AX security role.

The [WorkflowUserGroupParticipantProvider Class](https://msdn.microsoft.com/en-us/library/gg815310\(v=ax.60\)) and [WorkflowRoleParticipantProvider Class](https://msdn.microsoft.com/en-us/library/gg813937\(v=ax.60\)) implement the [WorkflowParticipantProvider Interface](https://msdn.microsoft.com/en-us/library/gg813892\(v=ax.60\)) which contains the following methods:

  - [WorkflowParticipantProvider.getParticipantTokens Method](https://msdn.microsoft.com/en-us/library/gg813891\(v=ax.60\))

  - [WorkflowParticipantProvider.resolve Method](https://msdn.microsoft.com/en-us/library/gg813893\(v=ax.60\))

The WorkflowParticipantProvider.GetParticipantTokens method is called from the workflow configuration user interface to display a list of supported participant tokens. Participant tokens are IDs of user roles or user group names.

The WorkflowParticipantProvider.resolve method is called when a task or approval step is started to determine the specific user to complete the step. For example, the workflow configuration is set up to require the approver of a step to be the purchasing manager. When the approval step is started, the participant provider resolve method is called to return the user ID of a specific purchasing manager.

## Queue Assignment Provider

You can use a queue assignment provider to resolve a work item to an appropriate workflow queue. Microsoft Dynamics AX workflow provides the [WorkflowWorkItemQueueProvider Class](https://msdn.microsoft.com/en-us/library/gg815906\(v=ax.60\)) and [WorkflowWorkItemQueueCustomProvider Class](https://msdn.microsoft.com/en-us/library/gg815891\(v=ax.60\)) that return a queue for the work item.

The [WorkflowWorkItemQueueProvider Class](https://msdn.microsoft.com/en-us/library/gg815906\(v=ax.60\)) and [WorkflowWorkItemQueueCustomProvider Class](https://msdn.microsoft.com/en-us/library/gg815891\(v=ax.60\)) implement the [WorkflowQueueProvider Interface](https://msdn.microsoft.com/en-us/library/gg813925\(v=ax.60\)) which contains the following methods:

  - [WorkflowQueueProvider.getQueueTokens Method](https://msdn.microsoft.com/en-us/library/gg813924\(v=ax.60\))

  - [WorkflowQueueProvider.queueIdToQueueName Method](https://msdn.microsoft.com/en-us/library/gg813926\(v=ax.60\))

  - [WorkflowQueueProvider.queueNameToQueueId Method](https://msdn.microsoft.com/en-us/library/gg813927\(v=ax.60\))

  - [WorkflowQueueProvider.resolve Method](https://msdn.microsoft.com/en-us/library/gg813928\(v=ax.60\))

The WorkflowQueueProvider.getQueueTokens method is called from the workflow configuration user interface to display a list of available queues.

The WorkflowQueueProvider.queueIdToQueueName method converts a queue ID value to a queue name.

The WorkflowQueueProvider.queueNameToQueueId method converts a queue name to a queue ID value.

The WorkflowQueueProvider.resolve method is called when a workflow step is started and should be assigned to a specific workflow queue.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

