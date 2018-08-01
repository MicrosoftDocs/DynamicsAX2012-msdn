---
title: Data Model for New Microsoft Dynamics AX Modules
TOCTitle: Data Model for New Microsoft Dynamics AX Modules
ms:assetid: bae2a75b-2d5e-4915-8702-05e958a212a0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa860987(v=AX.60)
ms:contentKeyID: 35249930
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Data Model for New Microsoft Dynamics AX Modules [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When creating a new module, create a data model that has the following criteria:

  - Has a structure similar to the one in the standard application

  - Can be normalized to the third normal form
    
    For a description of the third normal form, see the Microsoft Knowledge Base article about [Data Normalization Basics](http://go.microsoft.com/fwlink/?linkid=70739).

The following figure shows a simplification of the basic structure of the data model found in most Microsoft Dynamics AX modules. This structure can be used as a template for setting up the properties of your tables.

![Data model in most Dynamics AX modules](images/Aa860987.Image2(en-us,AX.60).gif "Data model in most Dynamics AX modules")

**Data model found in most modules**

The following table shows typical values for the various types of tables used in the previous figure. (All values shown in these tables are only guidelines and might not be exactly as found in the actual tables.)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>CustGroup</p></th>
<th><p>CustTable</p></th>
<th><p>CustTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name postfix</p></td>
<td><p>Group.</p></td>
<td><p>Table.</p></td>
<td><p>Trans.</p></td>
</tr>
<tr class="even">
<td><p>TableGroup</p></td>
<td><p>Group.</p></td>
<td><p>Main.</p></td>
<td><p>Transaction.</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>Stores information that categorizes the records.</p></td>
<td><p>Stores some base data in the application.</p></td>
<td><p>Stores some transactions in the application.</p></td>
</tr>
<tr class="even">
<td><p>Number of records</p></td>
<td><p>Typically relatively low with relatively static information.</p></td>
<td><p>Typically high with relatively static information.</p></td>
<td><p>Typically very high.</p></td>
</tr>
<tr class="odd">
<td><p>Key</p></td>
<td><p>There is always a key.</p></td>
<td><p>There is always a key.</p></td>
<td><p>There is always a key.</p></td>
</tr>
<tr class="even">
<td><p>Delete actions</p></td>
<td><p>The information is sometimes so non-vital that records can be deleted from the table, even if there are other records in the system that relate to the table.</p></td>
<td><p>Restricted against CustTrans and SalesTable.</p></td>
<td><p>Not applicable.</p></td>
</tr>
<tr class="odd">
<td><p>CacheLookup</p></td>
<td><p>Entire table.</p></td>
<td><p>Found, NotInTTS.</p></td>
<td><p>None.</p></td>
</tr>
<tr class="even">
<td><p>ClusterIndex</p></td>
<td><p>On the key.</p></td>
<td><p>On the key.</p></td>
<td><p>Consider.</p></td>
</tr>
</tbody>
</table>


The following table shows additional typical values for the various types of tables used in the previous figure.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>CustParameters</p></th>
<th><p>SalesTable</p></th>
<th><p>SalesLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name postfix</p></td>
<td><p>Parameter.</p></td>
<td><p>Table.</p></td>
<td><p>Trans or Line.</p></td>
</tr>
<tr class="even">
<td><p>TableGroup</p></td>
<td><p>Parameter.</p></td>
<td><p>WorkSheetHeader.</p></td>
<td><p>WorkSheetLine.</p></td>
</tr>
<tr class="odd">
<td><p>Description</p></td>
<td><p>Stores some basic parameters in the application.</p>
<p>There is one field per parameter.</p></td>
<td><p>Stores some header information for the related worksheet transactions.</p></td>
<td><p>Stores worksheet lines in the application.</p></td>
</tr>
<tr class="even">
<td><p>Number of records</p></td>
<td><p>Typically only one, or very few, with very static information.</p></td>
<td><p>Typically high with relatively static information.</p></td>
<td><p>Typically very high.</p></td>
</tr>
<tr class="odd">
<td><p>Key</p></td>
<td><p>There is a key to make the found cache work.</p></td>
<td><p>There is always a key.</p></td>
<td><p>There is sometimes a key.</p></td>
</tr>
<tr class="even">
<td><p>Delete actions</p></td>
<td><p>Not applicable.</p></td>
<td><p>Cascading SalesLine.</p></td>
<td><p>Not applicable.</p></td>
</tr>
<tr class="odd">
<td><p>CacheLookup</p></td>
<td><p>Found.</p></td>
<td><p>NotInTTS.</p></td>
<td><p>None.</p></td>
</tr>
<tr class="even">
<td><p>ClusterIndex</p></td>
<td><p>Not applicable.</p></td>
<td><p>On the key.</p></td>
<td><p>Consider.</p></td>
</tr>
</tbody>
</table>


## See also

[Designing a Microsoft Dynamics AX Application](designing-a-microsoft-dynamics-ax-application.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

