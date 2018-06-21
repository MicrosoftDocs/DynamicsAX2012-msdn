---
title: Business Overview Web Part
TOCTitle: Business Overview
ms:assetid: abaaf44f-c37e-4880-96a8-06871724baa0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862274(v=AX.60)
ms:contentKeyID: 35245606
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Business Overview Web Part [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Business overview web part displays measures or key performance indicators (KPIs). Measures are data calculations across various time periods. KPIs are business metrics that are summarized in terms of a comparison, goal, value, or status. A Business Overview web part is shown in the following illustration.

![Business Overview](images/Gg862274.EP_BusinessOverview(AX.60).gif "Business Overview")

## Page Types Used On

Role center pages

## Business Overview Properties

The following properties specific to the Business overview web part are available.

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
<td><p>Select mode</p></td>
<td><p>Specifies the type of content that the Business overview web part will display. Business Overview indicates that measures will be displayed, and KPI List indicates that KPIs will be displayed.</p></td>
</tr>
<tr class="even">
<td><p>Data Connection</p></td>
<td><p>If the KPIs or measures to be displayed in the web part are not accessed from the default Microsoft Dynamics AX Analysis Services database, you must use this property to specify the ODC (Office Data Connection) file that defines the connection to the Analysis Services database you want to access. The ODC file is created by using Microsoft Excel. Typically, the ODC file is added to a document library named <strong>Data Connections</strong> that you add to the main Enterprise Portal SharePoint site. Refer to <a href="https://msdn.microsoft.com/en-us/library/hh128831(v=ax.60)">How to: Create an ODC file for a Business Overview Web Part</a> for more information about how to create ODC files.</p>
<p>The Data Connection property specifies the relative path of the ODC file that you want to use from this document library. For example, if you want to access the measures defined in the SalesAnalysis.odc file that you had added to the Data Connections document library, you enter this value:</p>
<p>Data Connections/SalesAnalysis.odc</p></td>
</tr>
<tr class="odd">
<td><p>Title Label</p></td>
<td><p>Specifies the label that will be used as the title for the web part.</p></td>
</tr>
<tr class="even">
<td><p>Title</p></td>
<td><p>When a label is not used for the title, specifies the title of the web part.</p></td>
</tr>
</tbody>
</table>


## Connections

Can subscribe to a Filter published by any of the filter web parts included in SharePoint Server.

