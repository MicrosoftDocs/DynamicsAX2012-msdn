---
title: Passing Parameters to Pages
TOCTitle: Passing Parameters to Pages
ms:assetid: 2ff553c3-6ef9-499b-98fd-e6c87124d0f5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc568832(v=AX.60)
ms:contentKeyID: 28119423
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Passing Parameters to Pages 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When a user performs an action that opens a different page in Enterprise Portal, it is common to use the URL to pass parameter values to the page being opened. The page that is opened can retrieve parameters from the URL and respond appropriately.

## Passing Parameters

Typically, a web menu item defined in the AOT is used to open a page in Enterprise Portal. Each web menu item has a **Parameters** property that enables you to set the parameter values to be passed to the page being opened through the URL. The value for the **Parameters** property must comply with the standard used for passing parameters through a URL. Each parameter must have the following form:

name=value

If multiple parameters are to be passed, they must be separated by an ampersand character:

mode=2\&category=1

## Retrieving a Parameter

The code for User Controls can retrieve the parameters passed through the URL. To retrieve the parameters, the code must examine the QueryString from the HTTP request. The following example shows how the parameter named "mode" is retrieved from the URL.

``` csharp
string mode_value;
mode_value = this.Page.Request.QueryString.Get("mode");
```

## Using Parameters

A common use for URL parameters in Enterprise Portal is to specify the mode for an AxForm component of a User Control. The mode of the form can be changed in code based on the "mode" parameter passed through the URL. This allows for one User Control to be used in web parts that perform different actions, such as creating a new record or editing an existing record.

### Passing the Parameter

The EPFormAction enumeration defines the modes that a form can have. The enumeration is defined in the EPApplicationProxies project. The following table lists the values for the enumeration.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Enumeration value</p></th>
<th><p>Value</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>InfoMode</p></td>
<td><p>0</p></td>
</tr>
<tr class="even">
<td><p>EditMode</p></td>
<td><p>1</p></td>
</tr>
<tr class="odd">
<td><p>CreateMode</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>ListMode</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>DeleteMode</p></td>
<td><p>4</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>To use this enumeration in your code, you must add the EPApplicationProxies project to your EP Web Application project. For more information about how to do this, see <A href="how-to-use-a-predefined-proxy-for-a-web-application-project.md">How to: Use a Predefined Proxy for a Web Application Project</A>.</P>



Web menu items on an action pane or a toolbar are typically used to open the page that will perform actions. The **Parameters** property for each web menu item is set to specify the mode the AxForm component of the User Control will be set to. For example, the web menu item that opens a page which performs an edit action will have its **Parameters** property set to the following:

mode=1

### Retrieving the Parameter

The following function is added to the code for the User Control to retrieve the value of the mode parameter.

``` csharp
private EPFormAction FormMode
{
    get
    {
        // Retrieve the "mode" parameter from the query string for the page.
        queryString = this.Page.Request.QueryString.Get("mode");
        return (EPFormAction)Convert.ToInt16(queryString);
    }
}
```

### Using the parameter

The FormMode() private function defined earlier in this topic is called in the Page\_Load method for the User Control. After the mode has been retrieved, it is used to set the characteristics of the AxForm component of the User Control.

``` csharp
protected void Page_Load(object sender, EventArgs e)
{
    AxBoundField WorkOrderNumField;

    switch (this.FormMode)
    {
        case EPFormAction.EditMode:
            // Set the page title.
            this.PageDefinition.pageTitle = "Edit work order";

            // Set the mode for the AxForm.
            this.WorkOrderForm.DefaultMode = DetailsViewMode.Edit;
            this.WorkOrderForm.AutoGenerateEditButton = true;

            // Make the Work Order Number field read-only.
            WorkOrderNumField = GetField(this.RequestDetailsLeft.DataControlFieldCollection, "WorkOrderNum");
            WorkOrderNumField.ReadOnly = true;
            break;
        case EPFormAction.CreateMode:
            // Set the page title.
            this.PageDefinition.pageTitle = "Add work order";

            // Set the mode for the AxForm.
            this.WorkOrderForm.DefaultMode = DetailsViewMode.Insert;
            this.WorkOrderForm.AutoGenerateInsertButton = true;
            break;
        default:
            // Set the AxForm to read-only.
            this.WorkOrderForm.DefaultMode = DetailsViewMode.ReadOnly;
            break;
        }
    }
}
```

## See also

[How to: Create Web Menu Items](how-to-create-web-menu-items.md)

[Toolbar Web Part](toolbar-web-part.md)

[Action Pane Web Part](action-pane-web-part.md)

