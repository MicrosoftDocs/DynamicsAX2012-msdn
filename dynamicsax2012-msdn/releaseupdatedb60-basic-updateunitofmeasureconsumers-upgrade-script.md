---
title: ReleaseUpdateDB60_Basic.updateUnitOfMeasureConsumers Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateUnitOfMeasureConsumers Upgrade Script
ms:assetid: 896ab361-3210-26b1-fac9-f3c60361f649
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736381(v=AX.60)
ms:contentKeyID: 49709572
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateUnitOfMeasureConsumers Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateUnitOfMeasureConsumers</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates all references to the UnitOfMeasure table in the other tables.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>DEL_UnitUnitOfMeasureUpgrade</p></td>
</tr>
<tr class="even">
<td><p>InventItemGTIN</p></td>
</tr>
<tr class="odd">
<td><p>InventPackagingUnit</p></td>
</tr>
<tr class="even">
<td><p>InventPackagingUnitMaterial</p></td>
</tr>
<tr class="odd">
<td><p>AssetAddition</p></td>
</tr>
<tr class="even">
<td><p>AssetTable</p></td>
</tr>
<tr class="odd">
<td><p>BOM</p></td>
</tr>
<tr class="even">
<td><p>BOMCalcTable</p></td>
</tr>
<tr class="odd">
<td><p>BOMCalcTrans</p></td>
</tr>
<tr class="even">
<td><p>COSAllocation</p></td>
</tr>
<tr class="odd">
<td><p>COSCostDistribution</p></td>
</tr>
<tr class="even">
<td><p>COSLedgerTable</p></td>
</tr>
<tr class="odd">
<td><p>COSReference</p></td>
</tr>
<tr class="even">
<td><p>COSWorkDistribution</p></td>
</tr>
<tr class="odd">
<td><p>CustConfirmTrans</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceBackorderLine</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTrans</p></td>
</tr>
<tr class="even">
<td><p>CustPackingSlipBackorderLine</p></td>
</tr>
<tr class="odd">
<td><p>CustPackingSlipTrans</p></td>
</tr>
<tr class="even">
<td><p>CustQuotationConfirmTrans</p></td>
</tr>
<tr class="odd">
<td><p>CustQuotationTrans</p></td>
</tr>
<tr class="even">
<td><p>ForecastPurch</p></td>
</tr>
<tr class="odd">
<td><p>ForecastSales</p></td>
</tr>
<tr class="even">
<td><p>HRMGoal</p></td>
</tr>
<tr class="odd">
<td><p>IntrastatToProdcom</p></td>
</tr>
<tr class="even">
<td><p>InventFiscalLIFOJournalTrans</p></td>
</tr>
<tr class="odd">
<td><p>InventItemPrice</p></td>
</tr>
<tr class="even">
<td><p>InventItemPriceSim</p></td>
</tr>
<tr class="odd">
<td><p>InventJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>InventJournalTrans_Tag</p></td>
</tr>
<tr class="odd">
<td><p>InventNonConformanceTable</p></td>
</tr>
<tr class="even">
<td><p>InventPackagingMaterialCode</p></td>
</tr>
<tr class="odd">
<td><p>InventPackagingMaterialTrans</p></td>
</tr>
<tr class="even">
<td><p>InventPackagingMaterialTransPurch</p></td>
</tr>
<tr class="odd">
<td><p>InventParameters</p></td>
</tr>
<tr class="even">
<td><p>InventProdComLineDetail</p></td>
</tr>
<tr class="odd">
<td><p>InventProdComLineWithCode</p></td>
</tr>
<tr class="even">
<td><p>InventProdComLineWithoutCode</p></td>
</tr>
<tr class="odd">
<td><p>InventQualityOrderLine</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
</tr>
<tr class="odd">
<td><p>InventTableModule</p></td>
</tr>
<tr class="even">
<td><p>InventTestCertOfAnalysisLine</p></td>
</tr>
<tr class="odd">
<td><p>InventTestGroupMember</p></td>
</tr>
<tr class="even">
<td><p>InventTestInstrument</p></td>
</tr>
<tr class="odd">
<td><p>InventTestTable</p></td>
</tr>
<tr class="even">
<td><p>InventTransferJourLine</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferLine</p></td>
</tr>
<tr class="even">
<td><p>LedgerTable</p></td>
</tr>
<tr class="odd">
<td><p>PBATreeBOM</p></td>
</tr>
<tr class="even">
<td><p>PriceDiscAdmTrans</p></td>
</tr>
<tr class="odd">
<td><p>PriceDiscTable</p></td>
</tr>
<tr class="even">
<td><p>ProdBOM</p></td>
</tr>
<tr class="odd">
<td><p>ProdBOMTransProj</p></td>
</tr>
<tr class="even">
<td><p>ProdCalcTrans</p></td>
</tr>
<tr class="odd">
<td><p>ProdJournalBOM</p></td>
</tr>
<tr class="even">
<td><p>ProdParmSplit</p></td>
</tr>
<tr class="odd">
<td><p>ProdTable</p></td>
</tr>
<tr class="even">
<td><p>ProdTableProj</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceItem</p></td>
</tr>
<tr class="even">
<td><p>ProjItemTrans</p></td>
</tr>
<tr class="odd">
<td><p>PurchLine</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQCaseLine</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQLine</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQReplyLine</p></td>
</tr>
<tr class="odd">
<td><p>ReqPO</p></td>
</tr>
<tr class="even">
<td><p>RFIDTrans</p></td>
</tr>
<tr class="odd">
<td><p>SalesBasketLine</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
</tr>
<tr class="odd">
<td><p>SalesParmLine</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationBasketLine</p></td>
</tr>
<tr class="odd">
<td><p>SalesQuotationLine</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationParmLine</p></td>
</tr>
<tr class="odd">
<td><p>ShipCarrierCODPackage</p></td>
</tr>
<tr class="even">
<td><p>ShipCarrierPackage</p></td>
</tr>
<tr class="odd">
<td><p>ShipCarrierShippingRequest</p></td>
</tr>
<tr class="even">
<td><p>SMAAgreementLine</p></td>
</tr>
<tr class="odd">
<td><p>SMAServiceBOMTable</p></td>
</tr>
<tr class="even">
<td><p>SMAServiceOrderLine</p></td>
</tr>
<tr class="odd">
<td><p>SuppItemTable</p></td>
</tr>
<tr class="even">
<td><p>TaxTable</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceTrans</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipTrans</p></td>
</tr>
<tr class="odd">
<td><p>VendReceiptsListTrans</p></td>
</tr>
<tr class="even">
<td><p>VendRFQTrans</p></td>
</tr>
</tbody>
</table>

  


