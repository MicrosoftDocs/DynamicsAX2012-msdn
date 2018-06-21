﻿---
title: ReleaseUpdateTransformDB50_Transptn.custInvoiceJourDeltaPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Transptn.custInvoiceJourDeltaPreUpgradeProcess Upgrade Script
ms:assetid: 5c5eae27-5203-f761-9eca-fcb5d62d5402
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736331(v=AX.60)
ms:contentKeyID: 49708506
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Transptn.custInvoiceJourDeltaPreUpgradeProcess Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Transptn</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>custInvoiceJourDeltaPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms transportation data from the CustInvoiceJour table to the TransportationDocument and TransportationVehicle tables.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>CustInvoiceJour</p></td>
</tr>
<tr class="even">
<td><p>TransportationDocument</p></td>
</tr>
<tr class="odd">
<td><p>TransportationVehicle</p></td>
</tr>
</tbody>
</table>


## Remarks

This method inserts records into the TransportationDocument and TransportationVehicle tables from the CustInvoiceJour table, updates existing records in the TransportationDocument and TransportationVehicle tables, and deletes records from the TransportationDocument and TransportationVehicle tables that no longer have an associated record from the CustInvoiceJour table. It also updates the CustInvoiceJour table to reference the inserted TransportationDocument record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustInvoiceJour</p></th>
<th><p>To Table: TransportationDocument</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TrTransportationProperties_LT</p></td>
<td><p>DoPrintTransportationDocument</p></td>
</tr>
<tr class="even">
<td><p>TrLoadDateTime_LT</p></td>
<td><p>LoadedDateTime</p></td>
</tr>
<tr class="odd">
<td><p>TrResponsible_LT</p></td>
<td><p>IssuedBy</p></td>
</tr>
<tr class="even">
<td><p>TrCarrierType_LT</p></td>
<td><p>CarrierType</p></td>
</tr>
<tr class="odd">
<td><p>TrCarrierCode_LT</p></td>
<td><p>CarrierCode</p></td>
</tr>
<tr class="even">
<td><p>TrPackage_LT</p></td>
<td><p>PackageDescription</p></td>
</tr>
<tr class="odd">
<td><p>TrDangerDegree_LT</p></td>
<td><p>PackageDangerDegree</p></td>
</tr>
<tr class="even">
<td><p>TrLoadAddrName_LT</p></td>
<td><p>LoadedAddressName</p></td>
</tr>
<tr class="odd">
<td><p>TrLoadAddress_LT</p></td>
<td><p>LoadedPostalAddress</p></td>
</tr>
<tr class="even">
<td><p>TrLoadAddrCountry_LT</p></td>
<td><p>LoadedPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>TrLoadAddrState_LT</p></td>
<td><p>LoadedPostalAddress</p></td>
</tr>
<tr class="even">
<td><p>EconomicActivity_LV</p></td>
<td><p>EconomicActivityType</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustInvoiceJour</p></th>
<th><p>To Table: TransportationVehicle</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TrDriverName_LT</p></td>
<td><p>DriverName</p></td>
</tr>
<tr class="even">
<td><p>TrTruckPlateNr_LT</p></td>
<td><p>PlateNumber</p></td>
</tr>
<tr class="odd">
<td><p>TruckTrailerNum_LT</p></td>
<td><p>TrailerNumber</p></td>
</tr>
<tr class="even">
<td><p>TruckModel_LT</p></td>
<td><p>Model</p></td>
</tr>
</tbody>
</table>


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
<td><p>TransportationDocument</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TransportationVehicle</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceJour</p></td>
<td><p>TransportationDocument</p></td>
<td><p>TransportationDocumentRecId</p></td>
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
<td><p>CustInvoiceJour</p></td>
<td><p>TrTransportationProperties_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
<td><p>TrLoadDateTime_LT</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceJour</p></td>
<td><p>TrResponsible_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
<td><p>TrCarrierType_LT</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceJour</p></td>
<td><p>TrCarrierCode_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
<td><p>TrPackage_LT</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceJour</p></td>
<td><p>TrDangerDegree_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
<td><p>TrLoadAddrName_LT</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceJour</p></td>
<td><p>TrLoadAddress_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
<td><p>TrLoadAddrCountry_LT</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceJour</p></td>
<td><p>TrLoadAddrState_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
<td><p>EconomicActivity_LV</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceJour</p></td>
<td><p>DriverName</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
<td><p>PlateNumber</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceJour</p></td>
<td><p>TrailerNumber</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
<td><p>Model</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

