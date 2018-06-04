---
title: Adding the AxWorkflowActionBar to a User Control
TOCTitle: Adding the AxWorkflowActionBar to a User Control
ms:assetid: b4165bad-fdbf-40ce-a294-ecdbe4ddfc02
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee677508(v=AX.60)
ms:contentKeyID: 35246118
ms.date: 04/30/2013
mtps_version: v=AX.60
---

# Adding the AxWorkflowActionBar to a User Control 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxWorkflowActionBar is the User Control component used to perform workflow actions in Enterprise Portal. Typically, it is added to a User Control that also has an [AxForm](axform.md) control in it. The AxWorkflowActionBar is not available in the Toolbox in Visual Studio. You must manually add it to the ASP.NET markup for the User Control. See [Designing User Controls](designing-user-controls.md) for more information about how to work directly with the markup.

To reference the AxWorkflowActionBar in ASP.NET code for Enterprise Portal in Microsoft Dynamics AX 2012, you must include the following reference in the markup for the User Control:

    <%@ Register Assembly="Microsoft.Dynamics.Framework.Portal, Version=6.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
        Namespace="Microsoft.Dynamics.Framework.Portal.UI.WebControls.Workflow" TagPrefix="dynamics" %>

To reference the AxWorkflowActionBar in ASP.NET code for Enterprise Portal in Microsoft Dynamics AX 2012 R2, you must include the following reference in the markup for the User Control:

    <%@ Register Assembly="Microsoft.Dynamics.Framework.Portal, Version=6.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
        Namespace="Microsoft.Dynamics.Framework.Portal.UI.WebControls.Workflow" TagPrefix="dynamics" %>

After the reference to the control has been added, the following ASP.NET code example shows the AxWorkflowActionBar that was added to the WorkOrderDetails User Control for the Facility Management sample:

    <dynamics:AxWorkflowActionBar ID="WorkflowActionBar" runat="server" 
        DataSourceID="WorkOrdersDS" DataMember="FCMWorkOrders_Current"
        WorkflowDataSource="WorkOrdersDS" WorkflowType="FCMWorkOrderApproval" />

In the markup, you must specify the AxDataSource in the User Control that is accessing a workflow-enabled table. You must also specify the data member that the AxWorkflowActionBar is accessing from the data source. Typically, these will be the same data source and data member that the AxForm component in the User Control accesses. You also need to specify the workflow data source and the workflow type. Set the workflow data source to the same rood data source specified in the query used for the Document property on the workflow type. Set the workflow type to the name of the workflow type that you want to use.


> [!NOTE]
> <P>The AxWorkflowActionBar does not have a working renderer in the Design view for the User Control. The control will still work correctly when it is used in Enterprise Portal.</P>


