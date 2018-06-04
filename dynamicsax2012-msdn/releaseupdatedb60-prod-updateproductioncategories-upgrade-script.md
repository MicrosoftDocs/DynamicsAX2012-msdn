---
title: ReleaseUpdateDB60_Prod.updateProductionCategories Upgrade Script
TOCTitle: ReleaseUpdateDB60_Prod.updateProductionCategories Upgrade Script
ms:assetid: 089ee26d-a221-159c-4670-6255aa4b5e2b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684789(v=AX.60)
ms:contentKeyID: 49706485
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Prod.updateProductionCategories Upgrade Script 


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
<td><p>updateProductionCategories</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the production categories to populate the corresponding global categories.</p></td>
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
<tr class="even">
<td><p>Project</p></td>
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
<td><p>CategoryTable</p></td>
</tr>
<tr class="even">
<td><p>GlobalCategory</p></td>
</tr>
<tr class="odd">
<td><p>GlobalCategoryRoles</p></td>
</tr>
<tr class="even">
<td><p>GlobalCategoryRoleType</p></td>
</tr>
<tr class="odd">
<td><p>ProjCategory</p></td>
</tr>
<tr class="even">
<td><p>RouteCostCategory</p></td>
</tr>
<tr class="odd">
<td><p>COSLedgerTable</p></td>
</tr>
<tr class="even">
<td><p>ProdJournalRoute</p></td>
</tr>
<tr class="odd">
<td><p>ProdRouteTrans</p></td>
</tr>
<tr class="even">
<td><p>RouteCostCategoryPrice</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrTable</p></td>
</tr>
<tr class="even">
<td><p>ProdRoute</p></td>
</tr>
<tr class="odd">
<td><p>RouteOpr</p></td>
</tr>
<tr class="even">
<td><p>PBATreeRouteOpr</p></td>
</tr>
<tr class="odd">
<td><p>DEL_COSWorkUnits</p></td>
</tr>
<tr class="even">
<td><p>CostControlTransCommittedCost</p></td>
</tr>
<tr class="odd">
<td><p>InventJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>ProdBOM</p></td>
</tr>
<tr class="odd">
<td><p>ProdTable</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
</tr>
<tr class="even">
<td><p>ProjControlCategory</p></td>
</tr>
<tr class="odd">
<td><p>ForecastSales</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
</tr>
<tr class="odd">
<td><p>ProjActivity</p></td>
</tr>
<tr class="even">
<td><p>InventTrans</p></td>
</tr>
<tr class="odd">
<td><p>JmgEmployee</p></td>
</tr>
<tr class="even">
<td><p>JmgStampJournalTrans</p></td>
</tr>
<tr class="odd">
<td><p>JmgTimecardTrans</p></td>
</tr>
<tr class="even">
<td><p>JmgStampTrans</p></td>
</tr>
<tr class="odd">
<td><p>JmgTermReg</p></td>
</tr>
<tr class="even">
<td><p>JmgTermRegArchive</p></td>
</tr>
<tr class="odd">
<td><p>ProjForecastEmpl</p></td>
</tr>
<tr class="even">
<td><p>JmgTmpJobBundleProjStartup</p></td>
</tr>
<tr class="odd">
<td><p>MarkupTrans</p></td>
</tr>
<tr class="even">
<td><p>ProdBOMTransProj</p></td>
</tr>
<tr class="odd">
<td><p>ProdJournalBOM</p></td>
</tr>
<tr class="even">
<td><p>ProdParmSplit</p></td>
</tr>
<tr class="odd">
<td><p>ProdTableProj</p></td>
</tr>
<tr class="even">
<td><p>ProjAllocateTrans</p></td>
</tr>
<tr class="odd">
<td><p>ProjJournalTable</p></td>
</tr>
<tr class="even">
<td><p>ProjBegBalJournalTrans_Fee</p></td>
</tr>
<tr class="odd">
<td><p>ProjGroup</p></td>
</tr>
<tr class="even">
<td><p>ProjCostPriceExpense</p></td>
</tr>
<tr class="odd">
<td><p>ProjCostSalesPrice</p></td>
</tr>
<tr class="even">
<td><p>ProjCostTrans</p></td>
</tr>
<tr class="odd">
<td><p>ProjDefaultOffsetSetup</p></td>
</tr>
<tr class="even">
<td><p>ProjEmplTrans</p></td>
</tr>
<tr class="odd">
<td><p>ProjJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>ProjForecastRevenue</p></td>
</tr>
<tr class="odd">
<td><p>ProjFundingLimit</p></td>
</tr>
<tr class="even">
<td><p>ProjFundingRule</p></td>
</tr>
<tr class="odd">
<td><p>ProjHourCostPrice</p></td>
</tr>
<tr class="even">
<td><p>ProjHourSalesPrice</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceCost</p></td>
</tr>
<tr class="even">
<td><p>ProjInvoiceEmpl</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceItem</p></td>
</tr>
<tr class="even">
<td><p>ProjInvoiceRevenue</p></td>
</tr>
<tr class="odd">
<td><p>ProjItemTrans</p></td>
</tr>
<tr class="even">
<td><p>ProjParameters</p></td>
</tr>
<tr class="odd">
<td><p>ProjRevenueTrans</p></td>
</tr>
<tr class="even">
<td><p>ProjRevenueSalesPrice</p></td>
</tr>
<tr class="odd">
<td><p>SMASubscriptionTable</p></td>
</tr>
<tr class="even">
<td><p>ProjTransBudget</p></td>
</tr>
<tr class="odd">
<td><p>ProjTransPosting</p></td>
</tr>
<tr class="even">
<td><p>ProjValEmplCategorySetUp</p></td>
</tr>
<tr class="odd">
<td><p>ProjValProjCategorySetUp</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQLine</p></td>
</tr>
<tr class="odd">
<td><p>PurchLineDelete</p></td>
</tr>
<tr class="even">
<td><p>PurchParmLine_Project</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqLine</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQCaseLine</p></td>
</tr>
<tr class="odd">
<td><p>SalesLineDelete</p></td>
</tr>
<tr class="even">
<td><p>SMAAgreementLine</p></td>
</tr>
<tr class="odd">
<td><p>SMASalesPriceSubscription</p></td>
</tr>
<tr class="even">
<td><p>SMAServiceOrderLine</p></td>
</tr>
<tr class="odd">
<td><p>TaxJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoLine_Project</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

