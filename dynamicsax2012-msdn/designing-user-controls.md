---
title: Designing User Controls
TOCTitle: Designing User Controls
ms:assetid: 325696a8-2997-4cb2-b098-86b74df2af98
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc569201(v=AX.60)
ms:contentKeyID: 28119428
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Designing User Controls 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When designing a User Control for use in Enterprise Portal, you will use several techniques in Visual Studio. Most tasks can be performed in the graphical designer. Other design tasks must be performed directly in code for the User Control.

## Working in the Designer

The Designer in Visual Studio shows a graphical representation of the components of the User Control.

### Toolbox

Use the Toolbox to add components to the User Control. Most of the components that you will use are found in the Dynamics AX group in the Toolbox, such as the AxDataSource or AxForm components. Since the User Control will be used in a web browser, you might also use HTML components in the layout. For example, HTML tables can be used to organize the content for a User Control.

### Context Menu

Many of the Dynamics AX components that you add to the layout have characteristics that are controlled by a context menu for the control. This context menu is automatically displayed when you add the component to the layout. For example, when an AxDataSource component is added to the layout, the context menu lets you select the data set from the AOT that will be accessed. The following illustration shows the context menu for an AxDataSource component used to select the FCMWorkOrderDetails data set.

![Component Context Menu](images/Cc569201.EP_ComponentContextMenu(AX.60).gif "Component Context Menu")

To access the context menu for a component, move the pointer over the component and then click the context arrow that appears in the upper-right corner.

### Properties

Most characteristics of the components for a User Control are controlled by properties. Use the Properties window in Visual Studio to set or examine the properties for the components of the User Control. For instance, most components will have an ID property that is used to identify the component.

The properties for each Dynamics AX component are listed with the component in [User Control Components](user-control-components.md).

## Working Directly in Code

In some cases, you will have to work directly in the code for the User Control. For instance, some components for the User Control are not available in the Toolbox. Instead, you will view the source code for the User Control, and add the code that references the component.

As an example, the AxWorkflowActionBar component is used on some User Controls, but is not found in the Toolbox. To add the AxWorkflowActionBar component, you will view the source for the User Control. Next, you will add code that references the assembly the component is defined in. Finally, you will add code that references the AxWorkflowActionBar component.

The following example shows a section of the code for the WorkOrderDetails User Control (WorkOrderDetails.ascx). Notice the lines of code that register the workflow web controls, and the lines of code that define the instance of the AxWorkflowActionBar. These lines were manually added to the code for the User Control.

    <%@ Control Language="C#" AutoEventWireup="true" CodeFile="WorkOrderDetails.ascx.cs" Inherits="WorkOrderDetails" %>
    <%@ Register Assembly="Microsoft.Dynamics.Framework.Portal, Version=6.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
    Namespace="Microsoft.Dynamics.Framework.Portal.UI.WebControls" TagPrefix="dynamics" %>
    <%@ Register Assembly="Microsoft.Dynamics.Framework.Portal, Version=6.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
        Namespace="Microsoft.Dynamics.Framework.Portal.UI.WebControls.Workflow" TagPrefix="dynamics" %>
    <dynamics:AxDataSource ID="WorkOrdersDS" runat="server" 
        ProviderView="FCMWorkOrders" DataSetName="FCMWorkOrderDetails">
    </dynamics:AxDataSource>
    <dynamics:AxWorkflowActionBar ID="WorkflowActionBar" runat="server" 
        DataSourceID="WorkOrdersDS" DataMember="FCMWorkOrders_Current" />
    <dynamics:AxForm ID="WorkOrderForm" runat="server" DataKeyNames="WorkOrderNum" 
        DataMember="FCMWorkOrders_Current" DataSourceID="WorkOrdersDS" 
        AutoGenerateCancelButton="True">

## Specifying the Appearance for Components

The Dynamics AX components that you add to a User Control will automatically match the appearance of Enterprise Portal. When you add other ASP.NET components, such as text boxes or list boxes, these components will not match Enterprise Portal. You can make them match the Enterprise Portal appearance by specifying the appropriate class name for the **CssClass** property. The following table lists the cascading style sheet class names that you can use for the various component types.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>CSS Class</p></th>
<th><p>Use</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AxInputField</p></td>
<td><p>Single-line text boxes</p></td>
</tr>
<tr class="even">
<td><p>AxTextArea</p></td>
<td><p>Multi-line text boxes</p></td>
</tr>
<tr class="odd">
<td><p>AxOptionInput</p></td>
<td><p>Combo boxes and radio buttons</p></td>
</tr>
<tr class="even">
<td><p>AxLookupButtonBF</p></td>
<td><p>AxLookup buttons</p></td>
</tr>
<tr class="odd">
<td><p>AxLookupButtonHoverBF</p></td>
<td><p>AxLookup buttons when mouse is hovering</p></td>
</tr>
</tbody>
</table>


## Embedding User Controls

If the same user interface elements or code are frequently used in your User Controls, you may want to add them to one common User Control. Use the Register directive in the ASP.NET markup to embed the common User Control into other User Controls that you are creating. The code and resources from the common control are available for use without having to re-create them.

The **AxBaseUserControl** that is included with Enterprise Portal contains common code that is used by several other User Controls. For example, the **EPPurchTableInfo** User Control has the AxBaseUserControl and the EPPurchTableUtil controls embedded in it. The following directive in the markup for EPPurchTableInfo reference AxBaseUserControl and EPPurchTableUtil:

\<%@ Register Src="AxBaseUserControl.ascx" TagName="AxBaseUserControl" TagPrefix="Ax" %\>   
 \<%@ Register Src="EPPurchTableUtil.ascx" TagName="EPPurchTableUtil" TagPrefix="PTU" %\>

Be aware of the following issues when you use embedded User Controls:

  - When you add the main User Control to an EP Web Application project, all of the referenced controls are automatically added to the project also.

  - When designing the content of a common User Control, make sure that the resources in the control do not create conflicts. For example, if the common User Control contains an AxDataSource component, make sure that the **Role** property for the data source does not conflict with the **Role** property for any AxDataSource components you add to the main User Control.

  - When defining the security permissions for the main User Control, make sure that you include any embedded User Controls in the Associated Web Controls node. For example, EPPurchTableInfo has the AxBaseUserControl and EPPurchTableUtil User Controls embedded in it. These embedded controls must be included in the Associated Web Controls in the Permissions node.  
    
    ![Embedded User Control Permissions](images/Cc569201.EP_EmbeddedControlPermissions(AX.60).gif "Embedded User Control Permissions")

