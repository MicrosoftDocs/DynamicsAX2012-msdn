---
title: User Control Changes
TOCTitle: User Control Changes
ms:assetid: f9a07ea1-cfcb-4778-b057-5b44d6eb416e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272129(v=AX.60)
ms:contentKeyID: 36542144
ms.date: 04/30/2013
mtps_version: v=AX.60
dev_langs:
- xml
---

# User Control Changes [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Several features and changes in Enterprise Portal for Microsoft Dynamics AX 2012 require that you make updates to User Controls that you had created for your Enterprise Portal application. The following sections discuss the changes you have to make to User Controls so that they can be used with Enterprise Portal.

## Visual Studio Project

Microsoft Visual Studio 2010 is used to create and modify User Controls for Enterprise Portal. In Enterprise Portal for Microsoft Dynamics AX 2009, a Web Site Project was used to work with User Controls. For Microsoft Dynamics AX 2012, an EP Web Application project is used instead. When converting your Enterprise Portal application, you will have to create a new EP Web Application project. See [How to: Create an EP Web Application Project](how-to-create-an-ep-web-application-project.md) for more information. To add your User Controls to this project, use the procedure that is described in [How to: Modify User Controls](how-to-modify-user-controls.md).

## Proxy

In Microsoft Dynamics AX 2009, a proxy was available only for Enterprise Portal. In Microsoft Dynamics AX 2012, proxies can be used in managed code and also in User Controls for Enterprise Portal. The implementation of proxies has also changed significantly.

For Microsoft Dynamics AX 2009, most User Controls referenced the proxy that was used by Enterprise Portal. This proxy provided access to frequently-used resources, such as the EPFormAction enumeration used to indicate the type of action a page will perform. In Microsoft Dynamics AX 2012, User Controls must now reference the EPApplicationProxies project to access these resources. See [How to: Use a Predefined Proxy for a Web Application Project](how-to-use-a-predefined-proxy-for-a-web-application-project.md) for information about referencing a proxy project.

If you had added your own entries to the proxy for Microsoft Dynamics AX 2009, you will have to re-create them using the new technique for Microsoft Dynamics AX 2012. See [Proxies](proxies.md) for more information.

## User Control Layout

It is likely that you will have to change the layout for User Controls that you are converting to work with Enterprise Portal for Microsoft Dynamics AX 2012. Many of these changes can be made in the Design view for the User Control. Other changes must be made in the Source view, where the markup is displayed.

### Field selection

You use the **Bound Field Designer** to select the fields that you want to appear in User Controls. Fields that no longer exist in the AxDataSource for the User Control will cause errors when Enterprise Portal tries to display the control. These missing fields may not appear in the **Bound Field Designer**. You must view the markup for the User Control and remove any fields that are no longer part of the AxDataSource.

If there have been database changes for the tables accessed by your User Control, you may have to re-add the fields to the layout. Table changes that can cause this include tables that implement a surrogate key, store a surrogate key value, or are part of a table hierarchy. To add fields that display surrogate key values, use the AxReferenceBoundField type that is described in [Other Bound Field Types](other-bound-field-types.md).

### Multi-column support

User Controls for Microsoft Dynamics AX 2009 often used HTML tables to control the layout of the components in the control. In Enterprise Portal for Microsoft Dynamics AX 2012, you can use the [AxMultiColumn](axmulticolumn.md) and [AxColumn](axcolumn.md) components to create multi-column layouts for User Controls. Consider using these new components instead of HTML tables to implement a multi-column layout.

### Obsolete User Control components

The AxInfologCtrl component is no longer available for User Controls. Instead of using this component within a User Control, make sure that an [Infolog Web Part](infolog-web-part.md) has been added to the page on which the User Control will appear.

### New User Control components

Several new User Control components are available. Consider whether these components would be useful in the User Controls that you are converting for use with Enterprise Portal for Microsoft Dynamics AX 2012. The following is a list of the new components:

  - AxMultiColumn

  - AxColumn

  - AxReportViewer

  - AxHierarchicalGanttView

  - AxHierarchicalGridView

  - AxPartContentArea

  - AxFormPart

  - AxInfoPart

  - CueGroupPartControl

## Version Numbers

The version numbers for the assemblies referenced by User Controls have changed for Microsoft Dynamics AX 2012. You will have to modify the markup for the .ascx files of your User Controls to reference the new versions of the assemblies. The version number has changed from 5.0.0.0 to 6.0.0.0. For example, the following code is from the WorkOrderAddEdit.ascx User Control that was created for Microsoft Dynamics AX 2009. Notice that it references version 5.0.0.0 of the Microsoft.Dynamics.Framework.Portal assembly.

``` xml
<%@ Control Language="C#" AutoEventWireup="true" CodeFile="WorkOrderAddEdit.ascx.cs" Inherits="WorkOrderAddEdit" %>
<%@ Register Assembly="Microsoft.Dynamics.Framework.Portal, Version=5.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
Namespace="Microsoft.Dynamics.Framework.Portal.UI.WebControls" TagPrefix="dynamics" %>
```

The following code is the same User Control after it was updated to work in Enterprise Portal for Microsoft Dynamics AX 2012.

``` xml
<%@ Control Language="C#" AutoEventWireup="true" CodeFile="WorkOrderAddEdit.ascx.cs" Inherits="WorkOrderAddEdit" %>
<%@ Register Assembly="Microsoft.Dynamics.Framework.Portal, Version=6.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
Namespace="Microsoft.Dynamics.Framework.Portal.UI.WebControls" TagPrefix="dynamics" %>
```

The following code is the same User Control after it was updated to work in Enterprise Portal for Microsoft Dynamics AX 2012 R2.

``` xml
<%@ Control Language="C#" AutoEventWireup="true" CodeFile="WorkOrderAddEdit.ascx.cs" Inherits="WorkOrderAddEdit" %>
<%@ Register Assembly="Microsoft.Dynamics.Framework.Portal, Version=6.2.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
Namespace="Microsoft.Dynamics.Framework.Portal.UI.WebControls" TagPrefix="dynamics" %>
```

## Namespaces

Some of the namespaces have changed for Enterprise Portal. If the code for your User Controls reference resources from these namespaces, you will have to update the using statements in your code to indicate the correct namespaces. The following table lists the namespaces that have changed. The first column indicates the namespace in Microsoft Dynamics AX 2009, and the second column indicates the corresponding namespace in Microsoft Dynamics AX 2012.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Microsoft Dynamics AX 2009 Namespace</p></th>
<th><p>Microsoft Dynamics AX 2012 Namespace</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft.Dynamics.Framework.Data.Ax</p></td>
<td><p>Microsoft.Dynamics.AX.Framework.Portal.Data</p></td>
</tr>
<tr class="even">
<td><p>Microsoft.Dynamics.Framework.Metadata.Ax</p></td>
<td><p>Microsoft.Dynamics.AX.Framework.Services.Client</p></td>
</tr>
</tbody>
</table>


## Metadata

Several methods that are used to access metadata from within User Control code are now obsolete. The Microsoft Dynamics AX 2009 version of these methods required a session object to be passed in. The Microsoft Dynamics AX 2012 version of these methods does not require the session object. If you continue to use the obsolete methods, compiler warnings will be generated when you build the code for your User Control. We recommend that you use the new versions of these methods. See [Metadata](metadata.md) for information about how to use the new methods.

## Page Redirection

The modal dialog support provided by SharePoint 2010 and later can affect how page redirection is performed for User Controls in Enterprise Portal. The redirection code must now handle the case where the page was opened in a modal dialog. See [Page Redirection](page-redirection.md) for an example of redirection code that works for both in-line and modal dialog pages.

