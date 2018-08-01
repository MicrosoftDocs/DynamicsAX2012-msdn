---
title: ReleaseUpdateTransformDB50_Lean.deleteEBCTablesAndFields Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Lean.deleteEBCTablesAndFields Upgrade Script
ms:assetid: 8726b1a9-2173-8248-901c-224a04b8e2ea
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686068(v=AX.60)
ms:contentKeyID: 49709521
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Lean.deleteEBCTablesAndFields Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Lean</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>deleteEBCTablesAndFields</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Explicitly deletes Lean 2009 tables from the mapping and upgrade processes.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>Manufacture</p></td>
</tr>
<tr class="even">
<td><p>Basic</p></td>
</tr>
<tr class="odd">
<td><p>Production</p></td>
</tr>
<tr class="even">
<td><p>Accounts payable</p></td>
</tr>
<tr class="odd">
<td><p>Accounts receivable</p></td>
</tr>
<tr class="even">
<td><p>Inventory management</p></td>
</tr>
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
<td><p>EBC*</p></td>
</tr>
<tr class="even">
<td><p>Address</p></td>
</tr>
<tr class="odd">
<td><p>BOM</p></td>
</tr>
<tr class="even">
<td><p>BOMVersion</p></td>
</tr>
<tr class="odd">
<td><p>CustTable</p></td>
</tr>
<tr class="even">
<td><p>DlvMode</p></td>
</tr>
<tr class="odd">
<td><p>InventItemGroup</p></td>
</tr>
<tr class="even">
<td><p>InventJournalTable</p></td>
</tr>
<tr class="odd">
<td><p>InventJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>InventLocation</p></td>
</tr>
<tr class="odd">
<td><p>InventTable</p></td>
</tr>
<tr class="even">
<td><p>InventTrans</p></td>
</tr>
<tr class="odd">
<td><p>LedgerJournalTrans</p></td>
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
<td><p>SalesTable</p></td>
</tr>
<tr class="even">
<td><p>WMSOrderTrans</p></td>
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
<td><p>EBCAlertMessage</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCAssemblyStructure</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCATPDateCalc</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCCumulativeTransactions</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCDespatchTemplate</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCDimensions</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCDirectPull</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCFamilyGroups</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCIncomingChangeReason</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCIncomingSchedule</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCIncomingScheduleDetails</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCInternalOrderJournal</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCInventGroup</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCInventGroupHistory</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCInventJournalTransKanBan</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCInventJournalTransKanBanAlloc</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCInventSortType</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCInventTaktTime</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCJournalEntry</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCKanBan</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCKanBanConvertSubcon</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCKanBanDatingProfileTable</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCKanBanDisplayGroup</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCKanBanERO</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCKanBanGenericNumber</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCKanBanGroup</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCKanBanHistory</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCKanBanParameters</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCKanBanPhasedDates</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCKanBanShortage</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCKanBanTargetSchedule</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCKanBanTrans</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCKBOrderExplosion</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCKBReturnWarehouses</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCLeanInventPosting</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCLeanOrderBookedSchedule</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCLeanOrderBookedSchedulePTO</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCLeanOrderParameters</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCLeanOrders</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCLeanOrderScheduleParameters</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCLeanOrderSchedules</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCLeanParameters</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCLeanScheduleLog</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCLeanScheduleOverProduction</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCLeanWarehouse</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCLeanWarehouseParameters</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCLine</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCLosPokaYokaSignoff</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCLOSWarehouse</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCProfileBucketDates</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCProgramme</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCRefreshTable</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCReleasedSchedule</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCReleasedScheduleCallOff</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCReleasedScheduleDetails</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCSalesATP</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCSalesATPAction</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCSalesATPLine</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCSalesCalendar</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCSalesPlanning</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCSalesSchedDefaults</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCSchedItemDetail</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCScheduleParameters</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCScrapReplacementItems</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCSmoothingOrders</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCSortTypes</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCTemporaryLocation</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCTimeBooking</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCTmpReleasedPurchId</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCToteSizeInfo</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>EBCWarehouseJournal</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>EBCKanBanGroupCodes</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Address</p></td>
<td><p>EBCShipToId</p></td>
</tr>
<tr class="even">
<td><p>Address</p></td>
<td><p>EBCShipAcct</p></td>
</tr>
<tr class="odd">
<td><p>Address</p></td>
<td><p>EBCSalesPerson</p></td>
</tr>
<tr class="even">
<td><p>Address</p></td>
<td><p>EBCFreightFree</p></td>
</tr>
<tr class="odd">
<td><p>BOM</p></td>
<td><p>EBCOffset</p></td>
</tr>
<tr class="even">
<td><p>BOM</p></td>
<td><p>EBCLeanOrderSchedule</p></td>
</tr>
<tr class="odd">
<td><p>BOM</p></td>
<td><p>EBCCell</p></td>
</tr>
<tr class="even">
<td><p>BOM</p></td>
<td><p>EBCCritical</p></td>
</tr>
<tr class="odd">
<td><p>BOM</p></td>
<td><p>EBCExcludeBackflush</p></td>
</tr>
<tr class="even">
<td><p>BOM</p></td>
<td><p>EBCPrintDrawing</p></td>
</tr>
<tr class="odd">
<td><p>BOM</p></td>
<td><p>EBCAutoRelease</p></td>
</tr>
<tr class="even">
<td><p>BOM</p></td>
<td><p>EBCLeanLine</p></td>
</tr>
<tr class="odd">
<td><p>BOMVersion</p></td>
<td><p>EBCDrawingPrint</p></td>
</tr>
<tr class="even">
<td><p>CustTable</p></td>
<td><p>EBCCombined</p></td>
</tr>
<tr class="odd">
<td><p>CustTable</p></td>
<td><p>EBCFlowTypeCode</p></td>
</tr>
<tr class="even">
<td><p>CustTable</p></td>
<td><p>EBCLeadTime</p></td>
</tr>
<tr class="odd">
<td><p>CustTable</p></td>
<td><p>EBCSinglePullDelivery</p></td>
</tr>
<tr class="even">
<td><p>DlvMode</p></td>
<td><p>EBCCombined</p></td>
</tr>
<tr class="odd">
<td><p>DlvMode</p></td>
<td><p>EBCScatcode</p></td>
</tr>
<tr class="even">
<td><p>InventItemGroup</p></td>
<td><p>EBCExcludeFromVisual</p></td>
</tr>
<tr class="odd">
<td><p>InventItemGroup</p></td>
<td><p>EBCProductType</p></td>
</tr>
<tr class="even">
<td><p>InventItemGroup</p></td>
<td><p>EBCSwiftOrder</p></td>
</tr>
<tr class="odd">
<td><p>InventItemGroup</p></td>
<td><p>EBCCostItemId</p></td>
</tr>
<tr class="even">
<td><p>InventJournalTable</p></td>
<td><p>EBCProcessed</p></td>
</tr>
<tr class="odd">
<td><p>InventJournalTrans</p></td>
<td><p>EBCKanBanTicket</p></td>
</tr>
<tr class="even">
<td><p>InventJournalTrans</p></td>
<td><p>EBCCustAccount</p></td>
</tr>
<tr class="odd">
<td><p>InventJournalTrans</p></td>
<td><p>EBCDespatchDate</p></td>
</tr>
<tr class="even">
<td><p>InventJournalTrans</p></td>
<td><p>EBCTime</p></td>
</tr>
<tr class="odd">
<td><p>InventLocation</p></td>
<td><p>EBCWMSUpdate</p></td>
</tr>
<tr class="even">
<td><p>InventLocation</p></td>
<td><p>EBCWMSFlag</p></td>
</tr>
<tr class="odd">
<td><p>InventLocation</p></td>
<td><p>EBCCheckWarehouseOnly</p></td>
</tr>
<tr class="even">
<td><p>InventLocation</p></td>
<td><p>EBCPrintLevel</p></td>
</tr>
<tr class="odd">
<td><p>InventLocation</p></td>
<td><p>EBCBlackHole</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
<td><p>EBCRFCalc</p></td>
</tr>
<tr class="odd">
<td><p>InventTable</p></td>
<td><p>EBCInjection</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
<td><p>EBCOwner</p></td>
</tr>
<tr class="odd">
<td><p>InventTable</p></td>
<td><p>EBCKanBanTemplate</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
<td><p>EBCKanBanGenericNumberId</p></td>
</tr>
<tr class="odd">
<td><p>InventTable</p></td>
<td><p>EBCKanBanLeadTime</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
<td><p>EBCExcludeCostItemBackFlush</p></td>
</tr>
<tr class="odd">
<td><p>InventTable</p></td>
<td><p>EBCCostItemBackflush</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
<td><p>EBCKanBanGroupIdEBCKanBanGroupId</p></td>
</tr>
<tr class="odd">
<td><p>InventTable</p></td>
<td><p>EBCLengthCalc</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
<td><p>EBCSCKanBanTemplate</p></td>
</tr>
<tr class="odd">
<td><p>InventTable</p></td>
<td><p>EBCSignOffType</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
<td><p>EBCEmplId</p></td>
</tr>
<tr class="odd">
<td><p>InventTrans</p></td>
<td><p>EBCKanBanOrder</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans</p></td>
<td><p>EBCKanBanTicket</p></td>
</tr>
<tr class="odd">
<td><p>ProdTable</p></td>
<td><p>EBCLeanTransRef</p></td>
</tr>
<tr class="even">
<td><p>ProdTable</p></td>
<td><p>EBCLeanTransType</p></td>
</tr>
<tr class="odd">
<td><p>ProdTable</p></td>
<td><p>EBCLeanTransRefLine</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
<td><p>EBCKanBanOrder</p></td>
</tr>
<tr class="odd">
<td><p>PurchLine</p></td>
<td><p>EBCNbrToSupply</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
<td><p>EBCLength</p></td>
</tr>
<tr class="odd">
<td><p>PurchLine</p></td>
<td><p>EBCTotLength</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
<td><p>EBCSwiftOrder</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
<td><p>EBCKanBanOrder</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
<td><p>EBCLeanOrderSchedule</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
<td><p>EBCDrumbeatRequired</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
<td><p>EBCLength</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
<td><p>EBCNbrToSupply</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
<td><p>EBCTotLength</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
<td><p>EBCShipTo</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
<td><p>EBCTemplateId</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
<td><p>EBCStopLeanOrder</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
<td><p>EBCSinglePull</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
<td><p>EBCSkipATP</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>EBCFlowTypeCode</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
<td><p>EBCSwiftDel</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>EBCShipToId</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
<td><p>EBCEDIMaterialIssuer</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>EBCEDIReceiveLocation</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
<td><p>EBCEDIReceiveDock</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>EBCEDIModelYear</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
<td><p>EBCEDIEngLevel</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>EBCEDIFaciltyCode</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
<td><p>EBCEDIntermConsig</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>EBCShipAcct</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
<td><p>EBCPrintLongDescription</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>EBCCombined</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
<td><p>EBCStopLeanOrder</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>EBCDefSinglePull</p></td>
</tr>
<tr class="odd">
<td><p>WMSOrderTrans</p></td>
<td><p>EBCKanBanOrder</p></td>
</tr>
</tbody>
</table>

  


