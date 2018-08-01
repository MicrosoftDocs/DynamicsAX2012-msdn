---
title: ReleaseUpdateTransformDB50_Transptn.custInvoiceTablePreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Transptn.custInvoiceTablePreUpgradeProcess Upgrade Script
ms:assetid: 90b5044f-8bb8-86ef-47ee-d7fc2c363f31
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736567(v=AX.60)
ms:contentKeyID: 49709755
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Transptn.custInvoiceTablePreUpgradeProcess Upgrade Script 


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
<td><p>custInvoiceTablePreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms transportation data from the CustInvoiceTable table to the TransportationDocument and TransportationVehicle tables.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
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
<td><p>CustInvoiceTable</p></td>
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

This method inserts records into the TransportationDocument and TransportationVehicle tables from the CustInvoiceTable table. It also updates the CustInvoiceTable table to reference the inserted TransportationDocument record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustInvoiceTable</p></th>
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
<td><p>CarrierType_W</p></td>
<td><p>CarrierType</p></td>
</tr>
<tr class="odd">
<td><p>CarrierCode_W</p></td>
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
<td><p>TrLoadAddrCountryRegionId_LT</p></td>
<td><p>LoadedPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>TrLoadAddrZipCode_LT</p></td>
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
<th><p>From Table: CustInvoiceTable</p></th>
<th><p>To Table: TransportationVehicle</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Driver_W</p></td>
<td><p>Driver</p></td>
</tr>
<tr class="even">
<td><p>DriverName_W</p></td>
<td><p>DriverName</p></td>
</tr>
<tr class="odd">
<td><p>TruckPlateNum_W</p></td>
<td><p>PlateNumber</p></td>
</tr>
<tr class="even">
<td><p>TruckTrailerNum_W</p></td>
<td><p>TrailerNumber</p></td>
</tr>
<tr class="odd">
<td><p>TruckModel_W</p></td>
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
<td><p>CustInvoiceTable</p></td>
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
<td><p>CustInvoiceTable</p></td>
<td><p>TrTransportationProperties_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
<td><p>TrLoadDateTime_LT</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTable</p></td>
<td><p>TrResponsible_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
<td><p>CarrierType_W</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTable</p></td>
<td><p>CarrierCode_W</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
<td><p>TrPackage_LT</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTable</p></td>
<td><p>TrDangerDegree_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
<td><p>TrLoadAddrName_LT</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTable</p></td>
<td><p>TrLoadAddress_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
<td><p>TrLoadAddrCountry_LT</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTable</p></td>
<td><p>TrLoadAddrState_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
<td><p>TrLoadAddrCountryRegionId_LT</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTable</p></td>
<td><p>TrLoadAddrZipCode_LT</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
<td><p>Driver_W</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTable</p></td>
<td><p>DriverName_W</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
<td><p>TruckPlateNum_W</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTable</p></td>
<td><p>TruckTrailerNum_W</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTable</p></td>
<td><p>TruckModel_W</p></td>
</tr>
</tbody>
</table>

  


