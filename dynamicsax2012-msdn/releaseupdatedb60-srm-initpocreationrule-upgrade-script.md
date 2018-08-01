---
title: ReleaseUpdateDB60_Srm.initPOCreationRule Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.initPOCreationRule Upgrade Script
ms:assetid: 208d4b9f-65be-6fb1-e554-fe630f064b3a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684896(v=AX.60)
ms:contentKeyID: 49707098
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.initPOCreationRule Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Srm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>initPOCreationRule</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Initializes records for PO creation related tables.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>PurchReqSourcingPolicyRule</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingSplitRule</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqSourcingPriceToleranceRule</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingHoldRule</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqParameters</p></td>
</tr>
<tr class="even">
<td><p>SysPolicyOrganization</p></td>
</tr>
<tr class="odd">
<td><p>SysPolicySequence</p></td>
</tr>
<tr class="even">
<td><p>SysPolicyTypeSequence</p></td>
</tr>
<tr class="odd">
<td><p>SysPolicy</p></td>
</tr>
<tr class="even">
<td><p>SysPolicyOrganization</p></td>
</tr>
</tbody>
</table>


## Remarks

Policy framework has been introduced in this release. This upgrade script inserts records into tables that are related to PO creation from purchase requisition. The data is being migrated primarily from the PurchReqParameters table and the script will also inserts records in policy framework tables if not found.

## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurchReqSourcingPolicyRule</p></td>
<td><p>IsBatchGenerationEnabled</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingPolicyRule</p></td>
<td><p>DefaultPurchaseRequisitionName</p></td>
<td><p>PurchReqName</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqSourcingPolicyRule</p></td>
<td><p>ErrorOption</p></td>
<td><p>PurchReqPurchOrderGenerationErrorOption</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingSplitRule</p></td>
<td><p>SplitByRequisitioner</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqSourcingSplitRule</p></td>
<td><p>SplitByLineType</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingSplitRule</p></td>
<td><p>SplitByProductCategory</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqSourcingSplitRule</p></td>
<td><p>PolicyRule</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingPriceToleranceRule</p></td>
<td><p>EnablePriceTolerance</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqSourcingPriceToleranceRule</p></td>
<td><p>PercentageLimit</p></td>
<td><p>Percent</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingPriceToleranceRule</p></td>
<td><p>AmountLimit</p></td>
<td><p>Amount</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqSourcingPriceToleranceRule</p></td>
<td><p>PolicyRule</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingPriceToleranceRule</p></td>
<td><p>EnableAmountLimit</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqSourcingPriceToleranceRule</p></td>
<td><p>EnablePercentageLimit</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingHoldRule</p></td>
<td><p>EnableHoldByPrePayment</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqSourcingHoldRule</p></td>
<td><p>EnableManualHold</p></td>
<td><p>PurchReqSourcingManualType</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingHoldRule</p></td>
<td><p>EnableHoldByInternalCatalogItem</p></td>
<td><p>PurchReqSourcingCatalogItemHoldType</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqSourcingHoldRule</p></td>
<td><p>EnableHoldByExternalCatalogItem</p></td>
<td><p>PurchReqSourcingCatalogItemHoldType</p></td>
</tr>
<tr class="even">
<td><p>PurchReqSourcingHoldRule</p></td>
<td><p>EnableHoldByNonCatalogItem</p></td>
<td><p>PurchReqSourcingCatalogItemHoldType</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqSourcingHoldRule</p></td>
<td><p>PolicyRule</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurchReqParameters</p></td>
<td><p>DEL_CatalogType</p></td>
</tr>
<tr class="even">
<td><p>PurchReqParameters</p></td>
<td><p>DEL_ProductGroupIdCategory</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqParameters</p></td>
<td><p>DEL_LockMultiples</p></td>
</tr>
<tr class="even">
<td><p>PurchReqParameters</p></td>
<td><p>DEL_LockMinQty</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqParameters</p></td>
<td><p>DEL_LockMaxQty</p></td>
</tr>
<tr class="even">
<td><p>PurchReqParameters</p></td>
<td><p>DEL_ProductGroupId</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqParameters</p></td>
<td><p>DEL_AutoCreatePurch</p></td>
</tr>
</tbody>
</table>

  


