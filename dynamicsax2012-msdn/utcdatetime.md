---
title: utcdatetime
TOCTitle: utcdatetime
ms:assetid: 3d6171a2-3341-4153-9437-d11bf3df01c0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc597805(v=AX.60)
ms:contentKeyID: 35242934
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# utcdatetime [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The utcdatetime data type is intrinsic to X++. It combines date and timeOfDay types into one type. A utcdatetime variable also holds time zone information, though this information is not accessible to X++ code.

## Range and Precision

The following table describes the range and precision of the utcdatetime data type.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Attribute of utcdatetime</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Precision</p></td>
<td><p>The smallest unit of time in utcdatetime is one second.</p></td>
</tr>
<tr class="even">
<td><p>Default and Null</p></td>
<td><p>1900-01-01T00:00:00</p>
<p>A utcdatetime variable that has been declared but not initialized has the default value of 1900-01-01T00:00:00. This is the value returned by DateTimeUtil ::minValue().</p>
<p>Some functions treat an input parameter of this minimum value as null. For instance, the DateTimeUtil ::toStr method returns an empty string, however, the DateTimeUtil ::addSeconds method returns a fully usable utcdatetime value.</p></td>
</tr>
<tr class="odd">
<td><p>Minimum Value</p></td>
<td><p>1900-01-01T00:00:00</p></td>
</tr>
<tr class="even">
<td><p>Maximum Value</p></td>
<td><p>2154-12-31T23:59:59</p>
<p>This matches the upper range of date and timeOfDay.</p></td>
</tr>
</tbody>
</table>


## Benefits of Using an Extended Data Type for utcdatetime

When you add a utcdatetime field to a table, we recommend that you base the field on an extended data type (EDT). In MorphX, when you set the **TimezonePreference** property to **Auto** or **User** on the EDT, all fields based on the EDT are treated in the same consistent manner. The proper time zone offset is applied to all displays and to all filtering. A plain utcdatetime field has no **TimezonePreference** property.

The **Table Browser** form that the Application Object Tree (AOT) provides for each table can add and display utcdatetime values. This form treats utcdatetime fields differently depending on whether the fields are based on an EDT. Unless you understand and want that kind of different treatment among your utcdatetime fields, you should base all your utcdatetime fields on an EDT.

## X++ Literals for utcdatetime

The format for a utcdatetime literal is yyyy-mm-ddThh:mm:ss, with the uppercase T being a required literal character. This format is understood by X++ without quotes, as shown in these examples:

  - utcdatetime myUtc2 = 1988-07-20T13:34:45;

  - int iDay = DateTimeUtil ::day(1988-07-20T13:34:45)

This same format is expected as a quoted string parameter into the DateTimeUtil ::parse method:

  - utcdatetime myUtc4 = DateTimeUtil ::parse("1988-07-20T13:34:45");

## Conversions for utcdatetime

There are no automatic or implicit conversions for the utcdatetime data type.

The DateTimeUtil class provides many methods for manipulating utcdatetime values. The Microsoft Dynamics AX system provides the conversion functions str2datetime and datetime2str. Also, the Global class provides the conversion methods utcDateTime2SystemDateTime and CLRSystemDateTime2UtcDateTime to support common language runtime (CLR) interop.

## Operators for utcdatetime

Comparison operators are the only kind of operators that can be used with the utcdatetime data type. The following operators can compare two utcdatetime values:

  - \!=

  - \<

  - \<=

  - \==

  - \>

  - \>=

## See also

[DateTimeUtil Class](https://msdn.microsoft.com/en-us/library/gg837448\(v=ax.60\))

[Time Zone Overview and Terminology](time-zone-overview-and-terminology.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

