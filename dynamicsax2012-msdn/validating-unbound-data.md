---
title: Validating Unbound Data
TOCTitle: Validating Unbound Data
ms:assetid: 0b75a05f-3305-4857-9f47-a37d23024d71
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc581966(v=AX.60)
ms:contentKeyID: 28119404
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- xml
- jscript
---

# Validating Unbound Data 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When Enterprise Portal displays data in bound fields (fields that come from an AxDataSource) the data is automatically validated based on the underlying data type. User Controls you create may display fields that are not bound to an AxDataSource. Typically, you will want these unbound fields to be validated just like bound fields are. The Enterprise Portal framework contains the AxBaseValidator and the AxValueFormatValidator components to help you validate unbound data.

## AxBaseValidator

The AxBaseValidator component is based on the BaseValidator component defined for ASP.NET. You use the AxBaseValidator component in the ASP.NET code for a User Control just as you would use any standard validator. In addition to the base properties, the AxBaseValidator component has the additional property listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DisplayErrorInInfolog</p></td>
<td><p>Specifies whether the validation message will be displayed in the Infolog for Enterprise Portal.</p></td>
</tr>
</tbody>
</table>


To use an AxBaseValidator component, add the following to the markup for the User Control. Provide a unique value for the ID attribute.

``` xml
<dynamics:AxBaseValidator ID="AXBaseValidator1" runat="server"></dynamics:AxBaseValidator>
```

After the AxBaseValidator component has been added to the markup, you can use the **Properties** list to set the property values for the component. For example, you must set the ControlToValidate property that specifies which control is to be validated.

## AxValueFormatValidator

The AxValueFormatValidator component is based on the AxBaseValidator component. You use the AxValueFormatValidator component in the ASP.NET code for a User Control just as you would use any standard validator. In addition to the base properties, the AxValueFormatValidator component has the additional properties listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DisplayErrorInInfolog</p></td>
<td><p>Specifies whether the validation message will be displayed in the Infolog for Enterprise Portal.</p></td>
</tr>
<tr class="even">
<td><p>ExtendedDataType</p></td>
<td><p>Specifies the extended data type in Microsoft Dynamics AX that defines the characteristics the field value must have to be considered valid.</p></td>
</tr>
</tbody>
</table>


To use an AxValueFormatValidator component, add the following to the markup for the User Control. Provide a unique value for the ID attribute.

``` xml
<dynamics:AxValueFormatValidator ID="AXValueFormatValidator1" runat="server"></dynamics:AxValueFormatValidator>
```

After the AxValueFormatValidator component has been added to the markup, you can use the **Properties** list to set the property values for the component. For example, you must set the ControlToValidate property that specifies which control is to be validated. Use the ExtendedDataType property to specify the extended data type in Microsoft Dynamics AX that defines the characteristics the field must have to be considered valid.

## Validation Examples

The following examples show how to use a validator component in a User Control.

### AxBaseValidator

The following example shows how an AxBaseValidator is used to validate a text box in a User Control. The following code is added to the markup for the User Control to define the validator.

``` xml
<dynamics:AxBaseValidator ID="AxBaseValidator1" runat="server" 
    ValidationGroup="Sample" ControlToValidate="ABCValue" 
    ClientValidationFunction="ABC_Validate" ErrorMessage="Value must be A, B, or C."></dynamics:AxBaseValidator>
```

When the Sample validation group is evaluated, the ABC\_Validate script shown below is run on the client to validate the field. This script was added to the ASP.NET markup for the User Control.

``` jscript
<script id="ABCValidator" type="text/javascript" language="javascript">
 function ABC_Validate(val, args)
 {
    // Does the input value contain only A, B, or C?
    if ((args.Value == "A") || (args.Value == "B") || (args.Value == "C"))
    {
        args.IsValid=true;
    }
    else
    {
        args.IsValid=false;
    }
 }
</script>
```

If the validation script sets the IsValid argument to false, the error message specified in the ErrorMessage property for the AxBaseValidator component is displayed in the Infolog.

### AxValueFormatValidator

The following example shows how an AxValueFormatValidator component is used to validate a text box in a User Control that contains a bank ID. The following code is added to the markup for the User Control to define the validator.

``` xml
<dynamics:AxValueFormatValidator ID="AxValueFormatValidator1" runat="server" 
    ExtendedDataType="BankId" ValidationGroup="Sample" 
    ControlToValidate="BankIDValue" ErrorMessage="Bank ID is not valid"></dynamics:AxValueFormatValidator>
```

When the Sample validation group is evaluated, the value in the text box is compared with the properties of the BankId extended data type. If a validation error is found, such as the text box value being longer than the string size of the extended data type, the error message specified in the ErrorMessage property for the AxValueFormatValidator is displayed in the Infolog.

