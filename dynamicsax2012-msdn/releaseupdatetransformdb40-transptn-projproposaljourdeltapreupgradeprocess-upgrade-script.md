---
title: ReleaseUpdateTransformDB40_Transptn.projProposalJourDeltaPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Transptn.projProposalJourDeltaPreUpgradeProcess Upgrade Script
ms:assetid: c05c860c-9fb4-2169-0264-867505f62e62
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686763(v=AX.60)
ms:contentKeyID: 49710961
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Transptn.projProposalJourDeltaPreUpgradeProcess Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Transptn</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>projProposalJourDeltaPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms transportation data from the ProjProposalJour and PurchAdditionalProperties_W tables to the TransportationDocument and TransportationVehicle tables.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>ProjProposalJour</p></td>
</tr>
<tr class="even">
<td><p>PurchAdditionalProperties_W</p></td>
</tr>
<tr class="odd">
<td><p>TransportationDocument</p></td>
</tr>
<tr class="even">
<td><p>TransportationVehicle</p></td>
</tr>
</tbody>
</table>


## Remarks

This method inserts records into the TransportationDocument and TransportationVehicle tables from the ProjProposalJour and PurchAdditionalProperties\_W tables, updates existing records in the TransportationDocument and TransportationVehicle tables, and deletes records from the TransportationDocument and TransportationVehicle tables that no longer have an associated record from the ProjProposalJour or PurchAdditionalProperties\_W tables. It also updates the ProjProposalJour table to reference the inserted TransportationDocument record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchAdditionalProperties_W</p></th>
<th><p>To Table: TransportationDocument</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TrTransportationProperties_LT</p></td>
<td><p>DoPrintTransportationDocument</p></td>
</tr>
<tr class="even">
<td><p>CarrierCode</p></td>
<td><p>CarrierCode</p></td>
</tr>
<tr class="odd">
<td><p>CarrierType</p></td>
<td><p>CarrierType</p></td>
</tr>
<tr class="even">
<td><p>TrResponsible_LT</p></td>
<td><p>IssuedBy</p></td>
</tr>
<tr class="odd">
<td><p>TrPackage_LT</p></td>
<td><p>PackageDescription</p></td>
</tr>
<tr class="even">
<td><p>TrDangerDegree_LT</p></td>
<td><p>PackageDangerDegree</p></td>
</tr>
<tr class="odd">
<td><p>TrLoadDate_LT</p></td>
<td><p>LoadedDateTime</p></td>
</tr>
<tr class="even">
<td><p>TrLoadTime_LT</p></td>
<td><p>LoadedDateTime</p></td>
</tr>
<tr class="odd">
<td><p>TrLoadAddrName_LT</p></td>
<td><p>LoadedAddressName</p></td>
</tr>
<tr class="even">
<td><p>TrLoadAddress_LT</p></td>
<td><p>LoadedPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>TrLoadAddrCountryRegionId_LT</p></td>
<td><p>LoadedPostalAddress</p></td>
</tr>
<tr class="even">
<td><p>TrLoadAddrCounty_LT</p></td>
<td><p>LoadedPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>TrLoadAddrZipCode_LT</p></td>
<td><p>LoadedPostalAddress</p></td>
</tr>
<tr class="even">
<td><p>TrLoadAddrState_LT</p></td>
<td><p>LoadedPostalAddress</p></td>
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
<th><p>From Table: PurchAdditionalProperties_W</p></th>
<th><p>To Table: TransportationVehicle</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Driver</p></td>
<td><p>Driver</p></td>
</tr>
<tr class="even">
<td><p>DriverName</p></td>
<td><p>DriverName</p></td>
</tr>
<tr class="odd">
<td><p>TruckModel</p></td>
<td><p>Model</p></td>
</tr>
<tr class="even">
<td><p>TruckPlateNum</p></td>
<td><p>PlateNumber</p></td>
</tr>
<tr class="odd">
<td><p>TruckTrailerNum</p></td>
<td><p>TrailerNumber</p></td>
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
<td><p>ProjProposalJour</p></td>
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
<td><p>PurchAdditionalProperties_W</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

