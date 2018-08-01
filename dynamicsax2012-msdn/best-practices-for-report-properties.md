---
title: Best Practices for Report Properties
TOCTitle: Report Properties
ms:assetid: b3129d3c-c9f5-441a-a263-2afd44dd4772
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa857352(v=AX.60)
ms:contentKeyID: 35249761
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Report Properties [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_


> [!NOTE]
> <P>SQL Server&nbsp;Reporting Services is now the primary reporting platform for Microsoft Dynamics AX. The X++ reporting framework is being deprecated in Microsoft Dynamics AX 2012. Use the Visual Studio tools for Microsoft Dynamics AX to define reports. For more information, see <A href="https://msdn.microsoft.com/en-us/library/cc653472(v=ax.60)">Development Tasks for Reporting</A>.</P>



This topic describes the best practices for:

  - X++ Report Properties

  - X++ Report Design Properties

  - X++ Report Section Properties

  - X++ Report Control Properties

## Report Properties

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>The name must comply with general <a href="naming-conventions.md">Naming Conventions</a>.</p>
<p>Prefix: Module short name</p>
<p>Infix: Logical description of contents</p></td>
</tr>
</tbody>
</table>


## Report Design Properties


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Call the report 'Design', or use a logical name if you have more than one design.</p></td>
</tr>
<tr class="even">
<td><p>Caption</p></td>
<td><p>Use a label to indicate the contents or purpose of the report. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /> If the report is country/region-specific, you do not have to use a label.</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>You must use a label for the Description property, unless it is a country/region-specific report. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p>ReportTemplate</p></td>
<td><p>Use one. In generated design reports, Report Templates are only used at generation time. Template-generated sections must be manually maintained afterwards.</p>
<p>Use the following predefined templates:</p>
<div class="caption">
</div>
<div class="tableSection">
<div class="mtps-table">
<div class="mtps-row">
<span> <span> </span> </span> Internal use External use
</div>
<div class="mtps-row">
List InternalList ExternalList
</div>
<div class="mtps-row">
Form InternalForm ExternalForm
</div>
</div>
</div>
<p></p></td>
</tr>
<tr class="odd">
<td><p>Orientation</p></td>
<td><p>Typically set to Auto <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /> to exploit all the IntelliMorph features.</p>
<p>Set it to Portrait or Landscape for a report with specific format requirements.</p></td>
</tr>
</tbody>
</table>


## Report Section Properties

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ColumnHeadingStrategy</p></td>
<td><p>Use the default, WordWrap, if possible.</p></td>
</tr>
</tbody>
</table>


## Report Control Properties

Do not change the properties of report controls for controls that are based on fields, extended data types, and display methods, with respect to

  - Width

  - Label

  - Width of label

  - Formatting information, such as the kind of decimal point, and so on

If you change these report controls, you will not be able to use IntelliMorph.

The Left and Top properties should be set to Auto on most reports, but they should have a specific value on reports that are likely to be adjusted to the needs of individual customers.

## See also

[Reports Best Practices](reports-best-practices.md)

[Best Practices for Use of Reports](best-practices-for-use-of-reports.md)

[Best Practices for Report Design](best-practices-for-report-design.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

