---
title: Using Template Fields in User Controls
TOCTitle: Using Template Fields in User Controls
ms:assetid: e3c3a9af-2273-4720-84ae-9eeeaf204fe1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee677511(v=AX.60)
ms:contentKeyID: 35246170
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- xml
---

# Using Template Fields in User Controls [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The data in [AxBoundField](axboundfield.md) components in User Controls is controlled by the Enterprise Portal framework and ASP.NET. You may want to have code that interacts with or controls this bound field data. You can use a template field to do this.

## Creating a Template Field

You use the **Bound Field Designer** to add bound fields to a User Control. When you view the bound field in the ASP.NET markup, it resembles the following example:

``` xml
<dynamics:AxBoundField DataField="Cost" DataSet="FCMWorkOrderList" 
    DataSetView="FCMWorkOrders" HeaderText="Cost" SortExpression="Cost">
</dynamics:AxBoundField>
```

In the **Bound Field Designer**, you can select the bound field and then click **Convert to Template Field**. This will change the ASP.NET markup and convert the bound field to a template field. The following example shows the ASP.NET markup after the bound field in the previous example was converted to a template field:

``` xml
<asp:TemplateField ConvertEmptyStringToNull="False" 
    HeaderText="Cost" SortExpression="Cost">
    <EditItemTemplate>
        <asp:TextBox ID="TextBox1" runat="server" 
            Columns="<%$ AxDataSet:FCMWorkOrderList.FCMWorkOrders.Cost.DisplayLength %>" 
            Enabled="<%$ AxDataSet:FCMWorkOrderList.FCMWorkOrders.Cost.AllowEdit %>" 
            Text='<%# Bind("Cost") %>'></asp:TextBox>
    </EditItemTemplate>
    <ItemTemplate>
        <asp:Label ID="Label1" runat="server" Text='<%# Bind("Cost") %>'></asp:Label>
    </ItemTemplate>
</asp:TemplateField>
```

The template field will still function like the bound field. However, the ASP.NET markup for the field has been split into two sections. The EditItemTemplate section contains the code that is run when the template field is shown in edit mode. The ItemTemplate section contains the code that is run when the template field is shown in view-only mode. You can use standard ASP.NET code to perform actions based on the value of the template field.

## Example

The following example shows how an AxBoundField can be converted to a template field so additional code can be added for it. In this example, the Cost bound field is part of the WorkOrderList User Control. When the cost is larger than or equal to 100, a red circle will be displayed next to the distance value. The WorkOrderList User Control is shown in the following illustration.

![User Control with Template Field](images/Ee677511.EP_TemplateFieldExample(AX.60).gif "User Control with Template Field")

The **Bound Field Designer** was used to convert the Cost bound field into a template field. In the ItemTemplate section of the template field, the following ASP.NET markup code was added:

``` xml
<asp:Image runat="server" src="/_layouts/ep/images/Red.gif" 
    Visible='<%# Convert.ToInt32(DataBinder.Eval(Container.DataItem,"Cost")) >= 100 ? true : false %>'></asp:Image>
```

This code references the Red.gif image, which is deployed with Enterprise Portal. The code examines the value of the Cost field. If it is larger than or equal to 100, the image is displayed. The following example shows all of the ASP.NET code for the template field:

``` xml
<asp:TemplateField ConvertEmptyStringToNull="False" 
    HeaderText="Cost" SortExpression="Cost">
    <EditItemTemplate>
        <asp:TextBox ID="TextBox1" runat="server" 
            Columns="<%$ AxDataSet:FCMWorkOrderList.FCMWorkOrders.Cost.DisplayLength %>" 
            Enabled="<%$ AxDataSet:FCMWorkOrderList.FCMWorkOrders.Cost.AllowEdit %>" 
            Text='<%# Bind("Cost") %>'></asp:TextBox>
    </EditItemTemplate>
    <ItemTemplate>
        <asp:Label ID="Label1" runat="server" Text='<%# Bind("Cost") %>'></asp:Label>
        <asp:Image ID="Image1" runat="server" src="/_layouts/ep/images/Red.gif" 
        Visible='<%# Convert.ToInt32(DataBinder.Eval(Container.DataItem,"Cost")) >= 100 ? true : false %>'></asp:Image>
    </ItemTemplate>
</asp:TemplateField>
```

## See also

[Designing User Controls](designing-user-controls.md)

