---
title: Event Method Sequences when a Form is Opened
TOCTitle: Event Method Sequences when a Form is Opened
ms:assetid: 5fe6f874-d51a-4b83-949a-b25a74a3940c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa608211(v=AX.60)
ms:contentKeyID: 35244459
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Event Method Sequences when a Form is Opened 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An event method sequence is executed when a form is opened. The specific sequence depends on the set of controls and data sources that are associated with the form.

## Open a Form

In this example, the user opens a form that contains a grid control, which is bound to a data source.

The executed events are distributed across two threads. The timing of event method execution between threads can vary.

The following table shows the sequence that event methods are executed in when a user opens a form.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Where</p></th>
<th><p>Thread number</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>new</p></td>
<td><p>Form</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>init</p></td>
<td><p>Form</p></td>
<td><p>1</p></td>
</tr>
<tr class="odd">
<td><p>loadUserSetting</p></td>
<td><p>Form</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>run</p></td>
<td><p>Form</p></td>
<td><p>1</p></td>
</tr>
<tr class="odd">
<td><p>init</p></td>
<td><p>Data source</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>executeQuery</p></td>
<td><p>Data source</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>leaveRecord</p></td>
<td><p>Data source</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>leave</p></td>
<td><p>Data source</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>leaveRecord</p></td>
<td><p>Data source</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>firstField</p></td>
<td><p>Form</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>firstField</p></td>
<td><p>Form</p></td>
<td><p>1</p></td>
</tr>
</tbody>
</table>


## See also

[Event Method Sequences in Form Scenarios](event-method-sequences-in-form-scenarios.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

