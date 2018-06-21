---
title: Dynamics AX Client Type Library Reference
TOCTitle: Dynamics AX Client Type Library Reference
ms:assetid: 40ff2573-1fc9-47d2-bfe5-48e7f9e5eb8d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677289(v=AX.60)
ms:contentKeyID: 49384060
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- c++
- csharp
---

# Dynamics AX Client Type Library Reference [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

The Dynamics AX Client Type Library is a binary file that stores information about the Dynamics AX COM object. The COM object is a runtime object that provides programmatic access to the Microsoft Dynamics AX client. You can use the methods and enumerations in the type library to open a Microsoft Dynamics AX client form. The type library is created when you install the Microsoft Dynamics AX client application. For more information, see [Using COM to Open a Form from an Application](using-com-to-open-a-form-from-an-application.md).

The following interfaces in the Dynamics AX Client Type Library enable you to use the Dynamics AX COM object:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Interface</p></th>
<th><p>Information</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DynamicsAx.Application</p></td>
<td><p>You use a method from this interface to open a form.</p></td>
</tr>
<tr class="even">
<td><p>DynamicsAx.GeneralLedger</p></td>
<td><p>The interface is used internally. You should not use this interface or the methods that it provides.</p></td>
</tr>
</tbody>
</table>


## DynamicsAx.Application Interface

The Dynamics AX Client Type Library interface enables you to programmatically open a form.

### ![JJ677289.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677289.collapse_all(en-us,AX.60).gif")OpenMenuItem Method

You use the OpenMenuItemmethod to open a specified form. The following code example shows the signature of the method.

``` c++
HRESULT OpenMenuItem ([in] BSTR bstrCompany, [in] BSTR bstrMenuName, [in] AXMENUTYPE axMenuTypeMenuType)
```

The following sections describe the parameters, syntax, and return value for the OpenMenuItem method.

#### ![JJ677289.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677289.collapse_all(en-us,AX.60).gif")Parameters

To specify the form you want to open, use the following parameters.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>Type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>bstrCompany</p></td>
<td><p>[in] BSTR</p></td>
<td><p>A string that specifies a company. You use the company to specify the scope for the form.</p></td>
</tr>
<tr class="even">
<td><p>bstrMenuName</p></td>
<td><p>[in] BSTR</p></td>
<td><p>A string that specifies the name of a menu item.</p></td>
</tr>
<tr class="odd">
<td><p>axMenuTypeMenuType</p></td>
<td><p>[in] AXMENUTYPE</p></td>
<td><p>An enumeration value that specifies the type of the menu item specified by bstrMenuName parameter.</p>
<p>You use a member of the AxMenuType enumeration to specify the type of the menu item.</p></td>
</tr>
</tbody>
</table>


#### ![JJ677289.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677289.collapse_all(en-us,AX.60).gif")Syntax

The following code example shows how to call the OpenMenuItem method from a C\# application.

``` csharp
void OpenMenuItem(string company, string menuitem, AxClientLib.AxMenuType menuitemType);
```

The following code example shows how to use the OpenMenuItem method from Microsoft Visual Basic Scripting Edition.

    Dim instance
    Dim company, menuitem, menuitemType
     
    Set instance = CreateObject("DynamicsAx.Application")
    instance.OpenMenuItem company, menuitem, menuitemType

#### ![JJ677289.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677289.collapse_all(en-us,AX.60).gif")Return Value

The OpenMenuItem method returns a value of type HRESULT. The method returns one of the following values:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>HRESULT</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>S_OK</p></td>
<td><p>The method succeeded.</p></td>
</tr>
<tr class="even">
<td><p>E_INVALIDARG</p></td>
<td><p>An invalid parameter value was supplied to the method.</p></td>
</tr>
<tr class="odd">
<td><p>E_ACCESSDENIED</p></td>
<td><p>The user does not have permission to open the form. The menu item might not be associated with a security key.</p></td>
</tr>
<tr class="even">
<td><p>E_UNEXPECTED</p></td>
<td><p>An unexpected error occurred when you open the specified form.</p></td>
</tr>
</tbody>
</table>


When you use the Dynamics Ax Client Type Library with a .NET application, you use an interop assembly to access the DynamicsAxApplication interface. If the OpenMenuItem method returns any value but S\_OK, the interop converts the HRESULT to an exception.

#### ![JJ677289.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677289.collapse_all(en-us,AX.60).gif")Remarks

For information about how to use the OpenMenuItem with .NET or VBScript, see [How to: Use COM to Open a Form](how-to-use-com-to-open-a-form.md).

## AxMenuType

Use the AxMenuType enumeration to specify the type of a menu item. The enumeration includes the following values:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Constant</p></th>
<th><p>Value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ActionMenu</p></td>
<td><p>2</p></td>
<td><p>Specifies that the menu item is an Action type.</p></td>
</tr>
<tr class="even">
<td><p>DisplayMenu</p></td>
<td><p>0</p></td>
<td><p>Specifies that the menu item is a Display type.</p></td>
</tr>
<tr class="odd">
<td><p>OutputMenu</p></td>
<td><p>1</p></td>
<td><p>Specifies that the menu item is an Output type.</p></td>
</tr>
</tbody>
</table>


The following .NET code example uses AxMenuType for the third parameter of the OpenMenuItem method. Notice how the enumeration identifies that the CustTableListPage menu item is a Display type.

``` csharp
OpenMenuItem("DAT", "CustTableListPage", AxClientLib.AxMenuType.DisplayMenu);
```

## See also

[How to: Specify the Partition for the Form](how-to-specify-the-partition-for-the-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

