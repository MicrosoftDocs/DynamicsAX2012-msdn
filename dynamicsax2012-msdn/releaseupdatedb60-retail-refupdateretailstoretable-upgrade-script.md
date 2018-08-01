---
title: ReleaseUpdateDB60_Retail.refUpdateRetailStoreTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Retail.refUpdateRetailStoreTable Upgrade Script
ms:assetid: 9a4e9da3-f0aa-414d-80f3-02139ad7754c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686297(v=AX.60)
ms:contentKeyID: 49710000
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Retail.refUpdateRetailStoreTable Upgrade Script 


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
<td><p>refUpdateRetailStoreTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the storeId field with the new ID of the DEL_RetailUpgradedStringID table.</p></td>
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
<td><p>DEL_RETAILSTOREGROUPTRANS</p></td>
</tr>
<tr class="even">
<td><p>DEL_RETAILTRANSACTIONVOIDED</p></td>
</tr>
<tr class="odd">
<td><p>DEL_RETAILUPGRADEDSTRINGID</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONCESSIONCONTRACTAREA</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONCESSIONCONTRACTCOMMISSION</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONCESSIONCONTRACTCOMMISSIONHIST</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONCESSIONCONTRACTINVHISTPAYM</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONCESSIONCONTRACTPAYMENT</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONCESSIONCONTRACTPAYMENTHISTORY</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONCESSIONCONTRACTTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONCESSIONFILELOGTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONCESSIONFILELOGTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONCESSIONPURCHLOGTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONCESSIONPURCHLOGTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCONNDISTRIBUTIONLOCATION</p></td>
</tr>
<tr class="even">
<td><p>RETAILCONSESSIONPARTPAYMENTLINE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILCREDITVOUCHERTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILDATAENTRYTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILGIFTCARDTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILGIFTCARDTRANSACTIONS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILHANDHELDSETUP</p></td>
</tr>
<tr class="even">
<td><p>RETAILINCOMEEXPENSEACCOUNTTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILINVENTERRORNOTIFYTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILINVENTITEMLABEL</p></td>
</tr>
<tr class="odd">
<td><p>RETAILINVENTITEMSECTIONLOCATION</p></td>
</tr>
<tr class="even">
<td><p>RETAILINVRECEIVINGLISTTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILINVTRANSFERPICKINGLISTTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILLOG</p></td>
</tr>
<tr class="odd">
<td><p>RETAILLOYALTYMSRCARDTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILPARAMETERS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILPOSBATCHACCOUNTTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILPOSBATCHTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILPOSBATCHTENDERTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILSALESBYHOURREPORTTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSALESBYSTAFFTABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILSALESPERFORMANCEREPORTTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTAFFLOGINLOG</p></td>
</tr>
<tr class="even">
<td><p>RETAILSTATEMENTJOUR</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTATEMENTLINE</p></td>
</tr>
<tr class="even">
<td><p>RETAILSTATEMENTTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTATEMENTTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILSTORECASHDECLARATIONTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTORESECTION</p></td>
</tr>
<tr class="even">
<td><p>RETAILSTORESHELF</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTORETABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILSTORETENDERTYPECARDTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTORETENDERTYPETABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILSTOREWORKSHIFTTABLE</p></td>
</tr>
<tr class="odd">
<td><p>RETAILSTOREWORKSHIFTTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILSUSPENDEDTRANSACTIONS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILTERMINALRECEIPTTXT</p></td>
</tr>
<tr class="even">
<td><p>RETAILTERMINALTABLE</p></td>
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
<td><p>RETAILTRANSACTIONTABLEEX5</p></td>
</tr>
<tr class="even">
<td><p>RETAILTRANSACTIONTAXTRANS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILTRANSACTIONTENDERDECLARATIONTRANS</p></td>
</tr>
<tr class="even">
<td><p>RETAILUSERS</p></td>
</tr>
<tr class="odd">
<td><p>RETAILUSERSTORETABLE</p></td>
</tr>
<tr class="even">
<td><p>RETAILWORKSHIFTSETUP</p></td>
</tr>
</tbody>
</table>

  


