---
title: Activating a Workflow
TOCTitle: Activating a Workflow
ms:assetid: 37c319a1-4d0c-4afb-bfb9-c436ead1df4a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc586793(v=AX.60)
ms:contentKeyID: 35242066
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Activating a Workflow [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

After you create a workflow in Microsoft Dynamics AX, you must implement a way to activate the workflow at runtime to display the workflow in your application.

Application users start a workflow when they click the **Submit** button on forms that are enabled for workflow and have a valid workflow configuration.

The **Submit** button is controlled by an action menu item set on the SubmitToWorkflowMenuItem property for the workflow type. The action menu item references the class that you must implement to activate the workflow and other business logic associated with activating a workflow.

Depending on the needs of your application, you can activate a workflow by using any of the methods listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg812416(v=ax.60)">Workflow::activateFromWorkflowType Method</a></p></td>
<td><p>Used to activate a specific workflow type without knowing which configuration to use.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg812414(v=ax.60)">Workflow::activateFromWorkflowConfigurationId Method</a></p></td>
<td><p>Used to activate a specific version of a configuration.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg812415(v=ax.60)">Workflow::activateFromWorkflowSequenceNumber Method</a></p></td>
<td><p>Used to activate a configuration without knowing the specific version.</p></td>
</tr>
</tbody>
</table>


For more information about how to activate a workflow, see [Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md).

## In This Section

  - [How to: Activate a Workflow from a Workflow Type](how-to-activate-a-workflow-from-a-workflow-type.md)  
    Use this activation method to run the default configuration for a workflow type, or when a specific configuration is not needed or specified.

  - [How to: Activate a Workflow using the Configuration ID](how-to-activate-a-workflow-using-the-configuration-id.md)  
    Use this activation method when there are several versions of the same configuration and you need to select a specific version of that configuration.

  - [How to: Activate a Workflow using the Sequence Number](how-to-activate-a-workflow-using-the-sequence-number.md)  
    Use this activation method when there are several versions of the same configuration and you always want to run the active version of that configuration, regardless of the version.

## See also

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

