---
title: ReleaseUpdateDB60_Trv.updateExpenseCategories Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateExpenseCategories Upgrade Script
ms:assetid: 350bda39-cae5-288d-2057-8f86e3c5e6e9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685142(v=AX.60)
ms:contentKeyID: 49707595
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateExpenseCategories Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Trv</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateExpenseCategories</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the expense categories to populate the corresponding global categories.</p></td>
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
<td><p>Expense management</p></td>
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
<td><p>TrvGlobalSubCategory</p></td>
</tr>
<tr class="even">
<td><p>TrvExpSubCategory</p></td>
</tr>
<tr class="odd">
<td><p>TrvCostType</p></td>
</tr>
<tr class="even">
<td><p>ProjCategory</p></td>
</tr>
<tr class="odd">
<td><p>ProjExpPolicies</p></td>
</tr>
<tr class="even">
<td><p>TrvExpTrans</p></td>
</tr>
<tr class="odd">
<td><p>TrvValidatePayment</p></td>
</tr>
<tr class="even">
<td><p>TrvCostTypeRates</p></td>
</tr>
<tr class="odd">
<td><p>TrvPBSCatCodes</p></td>
</tr>
<tr class="even">
<td><p>TrvPBSMaindata</p></td>
</tr>
<tr class="odd">
<td><p>CostControlTransCommittedCost</p></td>
</tr>
<tr class="even">
<td><p>InventJournalTrans</p></td>
</tr>
<tr class="odd">
<td><p>ProdBOM</p></td>
</tr>
<tr class="even">
<td><p>ProdTable</p></td>
</tr>
<tr class="odd">
<td><p>PurchLine</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
</tr>
<tr class="odd">
<td><p>ProjControlCategory</p></td>
</tr>
<tr class="even">
<td><p>ForecastSales</p></td>
</tr>
<tr class="odd">
<td><p>InventTable</p></td>
</tr>
<tr class="even">
<td><p>ProjActivity</p></td>
</tr>
<tr class="odd">
<td><p>InventTrans</p></td>
</tr>
<tr class="even">
<td><p>JmgEmployee</p></td>
</tr>
<tr class="odd">
<td><p>JmgStampJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>JmgTimecardTrans</p></td>
</tr>
<tr class="odd">
<td><p>JmgStampTrans</p></td>
</tr>
<tr class="even">
<td><p>JmgTermReg</p></td>
</tr>
<tr class="odd">
<td><p>JmgTermRegArchive</p></td>
</tr>
<tr class="even">
<td><p>ProjForecastEmpl</p></td>
</tr>
<tr class="odd">
<td><p>JmgTmpJobBundleProjStartup</p></td>
</tr>
<tr class="even">
<td><p>MarkupTrans</p></td>
</tr>
<tr class="odd">
<td><p>ProdBOMTransProj</p></td>
</tr>
<tr class="even">
<td><p>ProdJournalBOM</p></td>
</tr>
<tr class="odd">
<td><p>ProdParmSplit</p></td>
</tr>
<tr class="even">
<td><p>ProdTableProj</p></td>
</tr>
<tr class="odd">
<td><p>ProjAllocateTrans</p></td>
</tr>
<tr class="even">
<td><p>ProjJournalTable</p></td>
</tr>
<tr class="odd">
<td><p>ProjBegBalJournalTrans_Fee</p></td>
</tr>
<tr class="even">
<td><p>ProjGroup</p></td>
</tr>
<tr class="odd">
<td><p>ProjCostPriceExpense</p></td>
</tr>
<tr class="even">
<td><p>ProjCostSalesPrice</p></td>
</tr>
<tr class="odd">
<td><p>ProjCostTrans</p></td>
</tr>
<tr class="even">
<td><p>ProjDefaultOffsetSetup</p></td>
</tr>
<tr class="odd">
<td><p>ProjEmplTrans</p></td>
</tr>
<tr class="even">
<td><p>ProjJournalTrans</p></td>
</tr>
<tr class="odd">
<td><p>ProjForecastRevenue</p></td>
</tr>
<tr class="even">
<td><p>ProjFundingLimit</p></td>
</tr>
<tr class="odd">
<td><p>ProjFundingRule</p></td>
</tr>
<tr class="even">
<td><p>ProjHourCostPrice</p></td>
</tr>
<tr class="odd">
<td><p>ProjHourSalesPrice</p></td>
</tr>
<tr class="even">
<td><p>ProjInvoiceCost</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceEmpl</p></td>
</tr>
<tr class="even">
<td><p>ProjInvoiceItem</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceRevenue</p></td>
</tr>
<tr class="even">
<td><p>ProjItemTrans</p></td>
</tr>
<tr class="odd">
<td><p>ProjParameters</p></td>
</tr>
<tr class="even">
<td><p>ProjRevenueTrans</p></td>
</tr>
<tr class="odd">
<td><p>ProjRevenueSalesPrice</p></td>
</tr>
<tr class="even">
<td><p>SMASubscriptionTable</p></td>
</tr>
<tr class="odd">
<td><p>ProjTransBudget</p></td>
</tr>
<tr class="even">
<td><p>ProjTransPosting</p></td>
</tr>
<tr class="odd">
<td><p>ProjValEmplCategorySetUp</p></td>
</tr>
<tr class="even">
<td><p>ProjValProjCategorySetUp</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQLine</p></td>
</tr>
<tr class="even">
<td><p>PurchLineDelete</p></td>
</tr>
<tr class="odd">
<td><p>PurchParmLine_Project</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQCaseLine</p></td>
</tr>
<tr class="even">
<td><p>SalesLineDelete</p></td>
</tr>
<tr class="odd">
<td><p>SMAAgreementLine</p></td>
</tr>
<tr class="even">
<td><p>SMASalesPriceSubscription</p></td>
</tr>
<tr class="odd">
<td><p>SMAServiceOrderLine</p></td>
</tr>
<tr class="even">
<td><p>TaxJournalTrans</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceInfoLine_Project</p></td>
</tr>
</tbody>
</table>

  


