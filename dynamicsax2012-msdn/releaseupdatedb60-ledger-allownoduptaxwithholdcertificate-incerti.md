---
title: ReleaseUpdateDB60_Ledger.allowNoDupTaxWithholdCertificate_INCerti
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupTaxWithholdCertificate_INCerti
ms:assetid: 104f0426-b3a4-4b61-90a8-cc739d032d96
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735779(v=AX.60)
ms:contentKeyID: 49706689
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupTaxWithholdCertificate\_INCerti 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupTaxWithholdCertificate_INCerti</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;CertificateNoIdx&lt;/c&gt; in the table &lt;c&gt;TaxWithholdCertificate_IN&lt;/c&gt; to allow duplicate records.</p></td>
</tr>
</tbody>
</table>


## Affected Modules and Tables

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Modules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>General ledger</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Tables</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TAXWITHHOLDCERTIFICATE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

As per standard method name should be allowNoDupTaxWithholdCertificate\_INCertificateNoIdx(), since the name exceeds the maximum charecters allowed some of the charectres from the index part has been truncated, so method name after truncating the charetcters is allowNoDupTaxWithholdCertificate\_INCerti().

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

