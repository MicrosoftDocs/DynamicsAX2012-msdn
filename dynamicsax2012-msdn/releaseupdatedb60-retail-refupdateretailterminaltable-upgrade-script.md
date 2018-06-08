---
title: ReleaseUpdateDB60_Retail.refUpdateRetailTerminalTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Retail.refUpdateRetailTerminalTable Upgrade Script
ms:assetid: 7ceacde4-f3a6-e453-f84a-8028df2a2a90
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719471(v=AX.60)
ms:contentKeyID: 49709261
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.refUpdateRetailTerminalTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Retail</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>refUpdateRetailTerminalTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the terminalId field of retail tables that have the new ID of the DEL_RetailTerminalTableUpgrade table.</p></td>
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
<td><p>Retail</p></td>
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
<td><p>CUSTINVOICEJOUR</p></td>
</tr>
<tr class="even">
<td><p>CUSTTRANS</p></td>
</tr>
<tr class="odd">
<td><p>DEL_RETAILTERMINALTABLEUPGRADE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCREDITVOUCHERTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILDATAENTRYTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILFILES</p></td>
</tr>
<tr class="odd">
<td><p>RETAILGIFTCARDTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILGIFTCARDTRANSACTIONS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILLOG</p></td>
</tr>
<tr class="even">
<td><p>RETAILLOYALTYMSRCARDTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILOFFLINESYNCLOG</p></td>
</tr>
<tr class="even">
<td><p>RETAILPOSBATCHACCOUNTTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILPOSBATCHTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILPOSBATCHTENDERTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTATEMENTLINE</p></td>
</tr>
<tr class="even">
<td><p>RETAILSTATEMENTTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSUSPENDEDTRANSACTIONS</p></td>
</tr>
<tr class="even">
<td><p>RETAILTERMINALRECEIPTTXT</p></td>
</tr>
<tr class="odd">
<td><p>RETAILTRANSACTIONBANKEDTENDERTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILTRANSACTIONDISCOUNTTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILTRANSACTIONINCOMEEXPENSETRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILTRANSACTIONINFOCODETRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILTRANSACTIONLOYALTYPOINTSTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILTRANSACTIONORDERINVOICETRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILTRANSACTIONPAYMENTTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILTRANSACTIONSAFETENDERTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILTRANSACTIONSALESTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILTRANSACTIONTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILTRANSACTIONTAXTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILTRANSACTIONTENDERDECLARATIONTRANS</p></td>
</tr>
<tr class="odd">
<td><p>SALESTABLE</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

