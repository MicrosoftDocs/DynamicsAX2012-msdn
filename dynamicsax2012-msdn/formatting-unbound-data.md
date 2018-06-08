---
title: Formatting Unbound Data
TOCTitle: Formatting Unbound Data
ms:assetid: 2f7492d3-0d7a-431c-9537-de45276bb536
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc551965(v=AX.60)
ms:contentKeyID: 28119420
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Formatting Unbound Data 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When Enterprise Portal displays data in bound fields (fields that come from an AxDataSource) the data is automatically formatted based on the underlying data type, the current locale, and the system settings for the user. User Controls you create may display fields that are not bound to an AxDataSource. Typically, you will want these unbound fields to be formatted just like bound fields are. The Framework Services in Microsoft Dynamics AX contains the AxValueFormatter class to help you format unbound data. The class can be used with the following types of data:

  - Date

  - Time

  - DateTime

  - Number

  - Real

  - String

  - GUID

  - Enum (Defined in the AOT)

## Namespace References

To use the AxValueFormatter class and its related classes, you must have a reference to the Microsoft.Dynamics.AX.Framework.Services.Client namespace. You will also need to retrieve context information for Enterprise Portal. The Microsoft.Dynamics.Framework.Portal.UI namespace contains the objects and properties needed for this.

The following using statements reference the namespaces that are required to format data.

``` csharp
using Microsoft.Dynamics.AX.Framework.Services.Client;
using Microsoft.Dynamics.Framework.Portal.UI;
```

## Displaying Formatted Data

The formatting information for fields can come from either the underlying data type or from the extended data type on which the field is based. Additional formatting information can come from the culture information retrieved from the context in which the data will be displayed. The CreateFormatter method of the AxValueFormatterFactory class requires these various inputs, depending on the type of formatter you are using.

### Formatting With Standard Types

You can create a formatter based on standard data types in Microsoft Dynamics AX. The types are contained in the Types enumeration defined in the Microsoft.Dynamics.Framework.BusinessConnector.Proxy namespace. The following example shows how the AxValueFormatterFactory is used to create an AxNumberValueFormatter object based on the Real type in Microsoft Dynamics AX. The formatter is configured to display negative values as surrounding parentheses. Then it is used to display a numeric value in a text box. In this example, a hard-coded value is being displayed, but the value could come from any source.

``` csharp
AxNumberValueFormatter numberValueFormatter;

// Create the formatter object.
numberValueFormatter = (AxNumberValueFormatter)AxValueFormatterFactory.CreateFormatter(AxSession, Types.Real);

// Specify that any negative value will be displayed with parentheses
numberValueFormatter.SignDisplay = SignDisplay.Parentheses;

// Use the formatter to display a number value
TextBox1.Text = numberValueFormatter.FormatValue(-469.64);
```

### Formatting With Extended Data Types

You can create a formatter based on an extended data type in Microsoft Dynamics AX. The metadata object for the extended data type is retrieved. This object is used with the culture information from the context to create the value formatter object. The following example shows how an AxNumberValueFormatter object is created based on the AmountCurNoDecimals extended data type defined in Microsoft Dynamics AX. This extended data type rounds the value it displays and removes the decimal part of the number. The formatter displays a number in a text box for the User Control. In this example, a hard-coded decimal value is being formatted. The string displayed will be rounded and the decimal portion removed.

``` csharp
int EDTNum;
ExtendedDataTypeMetadata edt;
AxNumberValueFormatter numberValueFormatter;

// Get the metadata for the extended data type.
EDTNum = ExtendedDataTypeMetadata.TypeNum(AxSession, "AmountCurNoDecimals");
edt = MetadataCache.GetExtendedDataTypeMetadata(AxSession, EDTNum);

// Get context from the system.
IAxContext context = AxContextHelper.FindIAxContext(this);

// Create the formatter object.
numberValueFormatter = (AxNumberValueFormatter)AxValueFormatterFactory.CreateFormatter(AxSession, edt, context.CultureInfo);

// Use the formatter to display a number value.
TextBox1.Text = numberValueFormatter.FormatValue(469.64);
```

## Reading Formatted Data

Formatter objects have a Parse method that can be used to convert a string value back into the underlying data type. For example, the string representation of a numeric value can be converted back into the numeric value. As the formatter object parses the string, it can account for special characters such as negative symbols and decimal separators. Be sure that you handle the AxValueFormatException that can occur if the value cannot be found from the string supplied.

The following example shows how the formatter object for the ActionType enumeration can convert the label of one of the enumeration values back into the corresponding numeric value. The following table shows the values and labels for the ActionType enumeration.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Enumeration Value</p></th>
<th><p>Label</p></th>
<th><p>Integer</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>None</p></td>
<td><p>None</p></td>
<td><p>0</p></td>
</tr>
<tr class="even">
<td><p>Advance</p></td>
<td><p>Advance</p></td>
<td><p>1</p></td>
</tr>
<tr class="odd">
<td><p>Postpone</p></td>
<td><p>Postpone</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Appreciate</p></td>
<td><p>Increase</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>Depreciate</p></td>
<td><p>Decrease</p></td>
<td><p>4</p></td>
</tr>
<tr class="even">
<td><p>AdvanceAppreciate</p></td>
<td><p>Advance+Increase</p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p>AdvanceDepreciate</p></td>
<td><p>Advance+Decrease</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>PostponeAppreciate</p></td>
<td><p>Postpone+Increase</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>PostponeDepreciate</p></td>
<td><p>Postpone+Decrease</p></td>
<td><p>8</p></td>
</tr>
<tr class="even">
<td><p>Cancel</p></td>
<td><p>Cancel</p></td>
<td><p>9</p></td>
</tr>
</tbody>
</table>


The formatter object for the ActionType enumeration is used to parse a string value. If the string matches the label of one of the values of the enumeration, the corresponding integer value of the enumeration is returned and displayed. Notice that the AxValueFormatException is thrown when an enumeration value cannot be determined from the input string.

``` csharp
int enumNum;
int enumValue = (-1);
EnumMetadata enumData;

// Retrieve the metadata for the enum.
enumNum = EnumMetadata.EnumNum("ActionType");
enumData = MetadataCache.GetEnumMetadata(enumNum);

// Get context from the system.
IAxContext context = AxContextHelper.FindIAxContext(this);

// Create the formatter for the enum.
AxEnumValueFormatter enumFormatter;
enumFormatter = (AxEnumValueFormatter)AxValueFormatterFactory.CreateFormatter(AxSession, enumData, context.CultureInfo);

// Parse the string, looking for one of the enum values.
try
{
    // Indicate that the enum value has not been retrieved.
    enumValue = -1;

    // Try to get the enum value that corresponds to the string.
    enumValue = (int)enumFormatter.Parse(TextBox1.Text);
}
catch (AxValueFormatException ex)
{
    // The enum value could not be found from the string.
    TextBox2.Text = "Cannot get enum value";
}

if (enumValue != (-1))
{
    // The enum value was found, so display it.
    TextBox2.Text = enumValue.ToString();
}
```

## See also

[Session Object](session-object.md)

