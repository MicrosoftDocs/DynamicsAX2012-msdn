---
title: ReleaseUpdateDB401_COS.updateCOSCalcTrans
TOCTitle: ReleaseUpdateDB401_COS.updateCOSCalcTrans
ms:assetid: cb0678b6-c7bf-2edb-35d9-a2cfa8873d58
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719652(v=AX.60)
ms:contentKeyID: 49711219
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB401\_COS.updateCOSCalcTrans [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB401_COS</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCOSCalcTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Removes duplicates from the COSCalcTrans table.</p></td>
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
<td><p>Cost accounting</p></td>
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
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>COSCalcTrans</p></td>
</tr>
<tr class="odd">
<td><p>COSCalculation</p></td>
</tr>
<tr class="even">
<td><p>COSCostBalances</p></td>
</tr>
<tr class="odd">
<td><p>COSLedgerLine</p></td>
</tr>
<tr class="even">
<td><p>COSLedgerTable</p></td>
</tr>
<tr class="odd">
<td><p>COSPlanAccounts</p></td>
</tr>
<tr class="even">
<td><p>COSPlanLines</p></td>
</tr>
<tr class="odd">
<td><p>COSPlanModel</p></td>
</tr>
<tr class="even">
<td><p>COSPlanTable</p></td>
</tr>
<tr class="odd">
<td><p>COSPlanWorkLoad</p></td>
</tr>
<tr class="even">
<td><p>DirNameSequence</p></td>
</tr>
<tr class="odd">
<td><p>DirParameters</p></td>
</tr>
<tr class="even">
<td><p>DirPartyLocation</p></td>
</tr>
<tr class="odd">
<td><p>DirPartyTable</p></td>
</tr>
<tr class="even">
<td><p>DirPrivacyGroup</p></td>
</tr>
<tr class="odd">
<td><p>FiscalCalendarPeriod</p></td>
</tr>
<tr class="even">
<td><p>FiscalCalendarYear</p></td>
</tr>
<tr class="odd">
<td><p>KMConnectionType</p></td>
</tr>
<tr class="even">
<td><p>LogisticsElectronicAddress</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsElectronicAddressType</p></td>
</tr>
<tr class="even">
<td><p>LogisticsLocation</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsLocationElectronicAddress</p></td>
</tr>
<tr class="even">
<td><p>LogisticsLocationPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsLocationRole</p></td>
</tr>
<tr class="even">
<td><p>LogisticsPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>NumberSequenceHistory</p></td>
</tr>
<tr class="even">
<td><p>NumberSequenceList</p></td>
</tr>
<tr class="odd">
<td><p>NumberSequenceReference</p></td>
</tr>
<tr class="even">
<td><p>NumberSequenceTable</p></td>
</tr>
<tr class="odd">
<td><p>NumberSequenceTTS</p></td>
</tr>
<tr class="even">
<td><p>Tax1099ValidationErrors</p></td>
</tr>
</tbody>
</table>


## Remarks

The quantities and amounts from duplicate records are accumulated into one single record and postings are corrected using the COSCalcTrans::postTrans method.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

