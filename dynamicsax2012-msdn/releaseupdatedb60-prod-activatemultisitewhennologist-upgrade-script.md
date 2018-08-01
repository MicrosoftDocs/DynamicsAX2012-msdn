---
title: ReleaseUpdateDB60_Prod.activateMultisiteWhenNoLogist Upgrade Script
TOCTitle: ReleaseUpdateDB60_Prod.activateMultisiteWhenNoLogist Upgrade Script
ms:assetid: 250ded63-6695-a0ab-2385-d7bbe75dba5f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685015(v=AX.60)
ms:contentKeyID: 49707215
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Prod.activateMultisiteWhenNoLogist Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Prod</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>activateMultisiteWhenNoLogist</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Activates multisite functionality during the upgrade without a Logistics license.</p></td>
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
<td><p>Production</p></td>
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
<td><p>CustVendExternalItem</p></td>
</tr>
<tr class="even">
<td><p>ECPPresentation</p></td>
</tr>
<tr class="odd">
<td><p>EPPriceCalc</p></td>
</tr>
<tr class="even">
<td><p>InventCountJour</p></td>
</tr>
<tr class="odd">
<td><p>InventDim</p></td>
</tr>
<tr class="even">
<td><p>InventItemBarcode</p></td>
</tr>
<tr class="odd">
<td><p>InventItemGTIN</p></td>
</tr>
<tr class="even">
<td><p>InventItemLocation</p></td>
</tr>
<tr class="odd">
<td><p>InventPackagingMaterialTrans</p></td>
</tr>
<tr class="even">
<td><p>InventPackagingUnit</p></td>
</tr>
<tr class="odd">
<td><p>InventProductGroupItem</p></td>
</tr>
<tr class="even">
<td><p>JmgProdParametersDim</p></td>
</tr>
<tr class="odd">
<td><p>PriceDiscAdmTrans</p></td>
</tr>
<tr class="even">
<td><p>PriceDiscTable</p></td>
</tr>
<tr class="odd">
<td><p>ProdUnitTable</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQCaseLine</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQLine</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQParmLine</p></td>
</tr>
<tr class="odd">
<td><p>ReqItemJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>ReqItemTable</p></td>
</tr>
<tr class="odd">
<td><p>ReqProcessItemDimList</p></td>
</tr>
<tr class="even">
<td><p>ReturnActionDefaults</p></td>
</tr>
<tr class="odd">
<td><p>ReturnReplaceItemRef</p></td>
</tr>
<tr class="even">
<td><p>RFIDTrans</p></td>
</tr>
<tr class="odd">
<td><p>SMAAgreementLine</p></td>
</tr>
<tr class="even">
<td><p>SMAServiceBOMTable</p></td>
</tr>
<tr class="odd">
<td><p>SMAServiceObjectRelation</p></td>
</tr>
<tr class="even">
<td><p>SMAServiceObjectTable</p></td>
</tr>
<tr class="odd">
<td><p>SMAServiceOrderLine</p></td>
</tr>
<tr class="even">
<td><p>SMATemplateBOMTable</p></td>
</tr>
<tr class="odd">
<td><p>SuppItemTable</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfo</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceInfoLine</p></td>
</tr>
<tr class="even">
<td><p>DEL_VendReqTrans</p></td>
</tr>
<tr class="odd">
<td><p>VendRFQTrans</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrParametersDim</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrTable</p></td>
</tr>
</tbody>
</table>

  


