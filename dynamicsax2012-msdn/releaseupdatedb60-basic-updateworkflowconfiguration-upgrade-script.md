---
title: ReleaseUpdateDB60_Basic.updateWorkflowConfiguration Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateWorkflowConfiguration Upgrade Script
ms:assetid: 881bae00-7330-0228-75da-b92511bdf509
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686086(v=AX.60)
ms:contentKeyID: 49709537
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateWorkflowConfiguration Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateWorkflowConfiguration</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the Microsoft Dynamics AX 2009 workflow configurations into Microsoft Dynamics AX 2012 workflow models. Moves packed structures into new tables, resolves duplicate sequence numbers and configuration IDs by using ID mapping table, generates links between workflow elements, and upgrade sub-workflows by introducing conditional gateways and parallel branch containers.</p></td>
</tr>
</tbody>
</table>


## Affected Modules and Tables

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Modules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Basic</p></td>
</tr>
<tr class="even">
<td><p>CRM</p></td>
</tr>
<tr class="odd">
<td><p>Expense management</p></td>
</tr>
<tr class="even">
<td><p>General ledger</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Tables</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WorkflowConfigurationTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowConfigurationTableNotes</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowVersionTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowVersionTableNotes</p></td>
</tr>
<tr class="even">
<td><p>WorkflowVersionNotificationTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementNotificationTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowStepTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementLinkTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementOutcomeTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowSubWorkflowTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowSubWorkflow</p></td>
</tr>
<tr class="even">
<td><p>WorkflowMessageText</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowIdRelationshipMapping</p></td>
</tr>
<tr class="even">
<td><p>WorkflowAssignmentTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTimeSpanTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowEscalationPathTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowEscalationTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowMaxRuntimeTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowActionTable</p></td>
</tr>
<tr class="even">
<td><p>ExpressionTable</p></td>
</tr>
<tr class="odd">
<td><p>SysWorkflowTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowWorkItemDelegationParameters</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingStatusTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowWorkItemTable</p></td>
</tr>
<tr class="even">
<td><p>TrvPolicyTable</p></td>
</tr>
<tr class="odd">
<td><p>SmmProcessStage</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalName</p></td>
</tr>
</tbody>
</table>


## Remarks

The WorkflowConfigurationTable table is re-factored into the WorkflowTable and WorkflowVersionTable tables. All duplicate sequence numbers in the WorkflowConfigurationTable table are resolved in the new WorkflowTable by setting the WorkflowTable.SequenceNumber value equal to the WorkflowConfigurationTable.RecID value. All duplicate configuration IDs in the WorkflowConfigurationTable table are resolved in the WorkflowVersionTable table by setting a new GUID. New GUIDs are also generated for all elements, such as the WorkflowElementTable table, and steps, such as the WorkflowStepTable table, for all configurations that have duplicate IDs. Fields in any other table that references the configuration IDs, sequence numbers, or expressions are also updated with the new IDs. The old and new values are maintained in a mapping table to be used by the runtime to complete in-flight workflow instances. The upgrade also removes any packed structures that are present in any of the workflow tables and writes them into new tables. Some of the de-normalized data was also normalized into new tables. Links relationships are created between every element in a configuration. Sub-workflows are upgraded by introducing conditional gateways that represent the guard conditions for the container or line and parallel branch container elements if the sub-workflows are to be executed in parallel.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowConfigurationTable</p></th>
<th><p>To Table: WorkflowTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TemplateName</p></td>
<td><p>TemplateName</p></td>
</tr>
<tr class="even">
<td><p>Name</p></td>
<td><p>Name</p></td>
</tr>
<tr class="odd">
<td><p>Module</p></td>
<td><p>Module</p></td>
</tr>
<tr class="even">
<td><p>SequenceNumber</p></td>
<td><p>SequenceNumber</p></td>
</tr>
<tr class="odd">
<td><p>Type</p></td>
<td><p>Type</p></td>
</tr>
<tr class="even">
<td><p>DefaultConfiguration</p></td>
<td><p>DefaultConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>CategoryName</p></td>
<td><p>CategoryName</p></td>
</tr>
<tr class="even">
<td><p>DocumentTableName</p></td>
<td><p>DocumentTableName</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowConfigurationTable</p></th>
<th><p>To Table: WorkflowVersionTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConfigurationID</p></td>
<td><p>ConfigurationID</p></td>
</tr>
<tr class="even">
<td><p>Enabled</p></td>
<td><p>Enabled</p></td>
</tr>
<tr class="odd">
<td><p>Owner</p></td>
<td><p>Owner</p></td>
</tr>
<tr class="even">
<td><p>ActivationConditionType</p></td>
<td><p>ActivationConditionType</p></td>
</tr>
<tr class="odd">
<td><p>ActivationConditionID</p></td>
<td><p>ActivationConditionID</p></td>
</tr>
<tr class="even">
<td><p>VersionIDMajor</p></td>
<td><p>VersionIDMajor</p></td>
</tr>
<tr class="odd">
<td><p>VersionIDMinor</p></td>
<td><p>VersionIDMinor</p></td>
</tr>
<tr class="even">
<td><p>VersionIDBuild</p></td>
<td><p>VersionIDBuild</p></td>
</tr>
<tr class="odd">
<td><p>VersionIDRevision</p></td>
<td><p>VersionIDRevision</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowConfigurationTable</p></th>
<th><p>To Table: WorkflowVersionNotificationTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>Enabled</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>Action</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowConfigurationTable</p></th>
<th><p>To Table: WorkflowAssignmentTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>AssignmentType</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>ActorValue</p></td>
</tr>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>UserValue</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>ParticipantProviderName</p></td>
</tr>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>ParticipantTokenName</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>HierarchyProviderName</p></td>
</tr>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>HierarchyTokenName</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>HierarchyFilterType</p></td>
</tr>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>HierarchyFilterId</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>HierarchyStopId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowConfigurationTableNotes</p></th>
<th><p>To Table: WorkflowVersionTableNotes</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConfigurationID</p></td>
<td><p>ConfigurationID</p></td>
</tr>
<tr class="even">
<td><p>Notes</p></td>
<td><p>Notes</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowElementTable</p></th>
<th><p>To Table: WorkflowActionTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ElementOutcomes</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>ElementOutcomes</p></td>
<td><p>Enabled</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowElementTable</p></th>
<th><p>To Table: WorkflowElementNotificationTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>Action</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>Enabled</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowElementTable</p></th>
<th><p>To Table: WorkflowAssignmentTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>AssignmentType</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>ActorValue</p></td>
</tr>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>UserValue</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>ParticipantProviderName</p></td>
</tr>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>ParticipantTokenName</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>HierarchyProviderName</p></td>
</tr>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>HierarchyTokenName</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>HierarchyFilterType</p></td>
</tr>
<tr class="odd">
<td><p>NotificationList</p></td>
<td><p>HierarchyFilterId</p></td>
</tr>
<tr class="even">
<td><p>NotificationList</p></td>
<td><p>HierarchyStopId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowElementTable</p></th>
<th><p>To Table: WorkflowMaxRuntimeTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UseMaxRuntime</p></td>
<td><p>Enabled</p></td>
</tr>
<tr class="even">
<td><p>MaxRuntimeTime</p></td>
<td><p>Time</p></td>
</tr>
<tr class="odd">
<td><p>MaxRuntimeTimezone</p></td>
<td><p>Timezone</p></td>
</tr>
<tr class="even">
<td><p>MaxRuntimeOutcome</p></td>
<td><p>Outcome</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowElementTable</p></th>
<th><p>To Table: WorkflowTimespanTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>MaxRuntime</p></td>
<td><p>DateType</p></td>
</tr>
<tr class="even">
<td><p>MaxRuntime</p></td>
<td><p>HourValue</p></td>
</tr>
<tr class="odd">
<td><p>MaxRuntime</p></td>
<td><p>HourCalendar</p></td>
</tr>
<tr class="even">
<td><p>MaxRuntime</p></td>
<td><p>DailyValue</p></td>
</tr>
<tr class="odd">
<td><p>MaxRuntime</p></td>
<td><p>DailyCalendar</p></td>
</tr>
<tr class="even">
<td><p>MaxRuntime</p></td>
<td><p>MonthlyDayOfWeek</p></td>
</tr>
<tr class="odd">
<td><p>MaxRuntime</p></td>
<td><p>MonthlyWeekInMonth</p></td>
</tr>
<tr class="even">
<td><p>MaxRuntime</p></td>
<td><p>WeeklyDayOfWeek</p></td>
</tr>
<tr class="odd">
<td><p>MaxRuntime</p></td>
<td><p>WeeklyValue</p></td>
</tr>
<tr class="even">
<td><p>MaxRuntime</p></td>
<td><p>YearlyDayOfWeek</p></td>
</tr>
<tr class="odd">
<td><p>MaxRuntime</p></td>
<td><p>YearlyMonthInYear</p></td>
</tr>
<tr class="even">
<td><p>MaxRuntime</p></td>
<td><p>YearlyWeekInMonth</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowStepTable</p></th>
<th><p>To Table: WorkflowAssignmentTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AssignTo</p></td>
<td><p>AssignmentType</p></td>
</tr>
<tr class="even">
<td><p>AssignTo</p></td>
<td><p>ActorValue</p></td>
</tr>
<tr class="odd">
<td><p>AssignTo</p></td>
<td><p>UserValue</p></td>
</tr>
<tr class="even">
<td><p>AssignTo</p></td>
<td><p>ParticipantProviderName</p></td>
</tr>
<tr class="odd">
<td><p>AssignTo</p></td>
<td><p>ParticipantTokenName</p></td>
</tr>
<tr class="even">
<td><p>AssignTo</p></td>
<td><p>HierarchyProviderName</p></td>
</tr>
<tr class="odd">
<td><p>AssignTo</p></td>
<td><p>HierarchyTokenName</p></td>
</tr>
<tr class="even">
<td><p>AssignTo</p></td>
<td><p>HierarchyFilterType</p></td>
</tr>
<tr class="odd">
<td><p>AssignTo</p></td>
<td><p>HierarchyFilterId</p></td>
</tr>
<tr class="even">
<td><p>AssignTo</p></td>
<td><p>HierarchyStopId</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>AssignmentType</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>ActorValue</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>UserValue</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>ParticipantProviderName</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>ParticipantTokenName</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>HierarchyProviderName</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>HierarchyTokenName</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>HierarchyFilterType</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>HierarchyFilterId</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>HierarchyStopId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowStepTable</p></th>
<th><p>To Table: WorkflowTimespanTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Duration</p></td>
<td><p>DateType</p></td>
</tr>
<tr class="even">
<td><p>Duration</p></td>
<td><p>HourValue</p></td>
</tr>
<tr class="odd">
<td><p>Duration</p></td>
<td><p>HourCalendar</p></td>
</tr>
<tr class="even">
<td><p>Duration</p></td>
<td><p>DailyValue</p></td>
</tr>
<tr class="odd">
<td><p>Duration</p></td>
<td><p>DailyCalendar</p></td>
</tr>
<tr class="even">
<td><p>Duration</p></td>
<td><p>MonthlyDayOfWeek</p></td>
</tr>
<tr class="odd">
<td><p>Duration</p></td>
<td><p>MonthlyWeekInMonth</p></td>
</tr>
<tr class="even">
<td><p>Duration</p></td>
<td><p>WeeklyDayOfWeek</p></td>
</tr>
<tr class="odd">
<td><p>Duration</p></td>
<td><p>WeeklyValue</p></td>
</tr>
<tr class="even">
<td><p>Duration</p></td>
<td><p>YearlyDayOfWeek</p></td>
</tr>
<tr class="odd">
<td><p>Duration</p></td>
<td><p>YearlyMonthInYear</p></td>
</tr>
<tr class="even">
<td><p>Duration</p></td>
<td><p>YearlyWeekInMonth</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>DateType</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>HourValue</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>HourCalendar</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>DailyValue</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>DailyCalendar</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>MonthlyDayOfWeek</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>MonthlyWeekInMonth</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>WeeklyDayOfWeek</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>WeeklyValue</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>YearlyDayOfWeek</p></td>
</tr>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>YearlyMonthInYear</p></td>
</tr>
<tr class="even">
<td><p>EscalationPath</p></td>
<td><p>YearlyWeekInMonth</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowStepTable</p></th>
<th><p>To Table: WorkflowEscalationTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EscalationAction</p></td>
<td><p>Action</p></td>
</tr>
<tr class="even">
<td><p>EscalationPathAction</p></td>
<td><p>PathAction</p></td>
</tr>
<tr class="odd">
<td><p>EscalationType</p></td>
<td><p>EscalationType</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowStepTable</p></th>
<th><p>To Table: WorkflowEscalationPathTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EscalationPath</p></td>
<td><p>Level</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowSubWorkflowTable</p></th>
<th><p>To Table: WorkflowSubWorkflow</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>DocumentKeyField</p></td>
<td><p>DocumentKeyField</p></td>
</tr>
<tr class="odd">
<td><p>DocumentKeyTable</p></td>
<td><p>DocumentKeyTable</p></td>
</tr>
<tr class="even">
<td><p>WaitForComplete</p></td>
<td><p>WaitForComplete</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowElementTable</p></th>
<th><p>To Table: WorkflowElementTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>ConfigurationID</p></td>
<td><p>ConfigurationID</p></td>
</tr>
<tr class="odd">
<td><p>ExecuteSubWorkflowID</p></td>
<td><p>ConditionalID</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowSubWorkflowTable</p></th>
<th><p>To Table: WorkflowElementTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExecuteWorkflowID</p></td>
<td><p>ConditionalID</p></td>
</tr>
</tbody>
</table>


## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WorkflowTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkflowVersionTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>WorkflowVersionTableNotes</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkflowVersionNotificationTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>WorkflowAssignmentTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkflowActionTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>WorkflowMaxRuntimeTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkflowTimespanTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>WorkflowEscalationTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkflowEscalationPathTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementLinkTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementOutcomeTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementNotificationTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkflowSubWorkflow</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>WorkflowParallelBranchTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkflowIDRelationshipMapping</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementTable</p></td>
<td><p>ConditionalID</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementTable</p></td>
<td><p>ParallelBranchTable</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WorkflowConfigurationTable</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>WorkflowConfigurationTableNotes</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementTable</p></td>
<td><p>UseMaxRuntime</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementTable</p></td>
<td><p>ElementOutcomes</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementTable</p></td>
<td><p>NotificationList</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementTable</p></td>
<td><p>MaxRuntime</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementTable</p></td>
<td><p>MaxRuntimeOutcome</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementTable</p></td>
<td><p>MaxRuntimeTime</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementTable</p></td>
<td><p>MaxRuntimeTimezone</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementTable</p></td>
<td><p>DataAreaID</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowStepTable</p></td>
<td><p>AssignTo</p></td>
</tr>
<tr class="even">
<td><p>WorkflowStepTable</p></td>
<td><p>EscalationType</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowStepTable</p></td>
<td><p>EscalationAction</p></td>
</tr>
<tr class="even">
<td><p>WorkflowStepTable</p></td>
<td><p>EscalationPathAction</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowStepTable</p></td>
<td><p>EscalationPath</p></td>
</tr>
<tr class="even">
<td><p>WorkflowStepTable</p></td>
<td><p>Duration</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowStepTable</p></td>
<td><p>DataAreaID</p></td>
</tr>
<tr class="even">
<td><p>WorkflowSubWorkflowTable</p></td>
<td><p>DataAreaID</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

