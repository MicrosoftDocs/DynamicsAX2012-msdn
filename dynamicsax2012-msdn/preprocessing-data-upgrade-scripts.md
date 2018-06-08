---
title: Preprocessing Data Upgrade Scripts
TOCTitle: Preprocessing Upgrade Scripts
ms:assetid: e620fee8-656a-426b-aba7-b9c939ff960b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719770(v=AX.60)
ms:contentKeyID: 49711844
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Preprocessing Data Upgrade Scripts 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Preprocessing upgrade scripts are one of two categories of data upgrade scripts. A preprocessing upgrade script is an X++ method implemented by using the upgrade framework APIs to run on the source system (Microsoft Dynamics AX 4.0 or Microsoft Dynamics AX 2009). Preprocessing upgrade scripts prepare the data within staging tables in preparation for the final data upgrade. Preprocessing upgrade scripts are installed when you import the preprocessing upgrade XPO from the installation media in the source environment. These upgrade scripts are run using the preprocessing upgrade framework.

## In This Section

This section contains information on the following preprocessing scripts:

[PmfReleaseUpdateDB30 Upgrade Scripts](pmfreleaseupdatedb30-upgrade-scripts.md)

[PreProcessing60\_Administration Upgrade Scripts](preprocessing60-administration-upgrade-scripts.md)

[ReleaseUpdateDB401\_COS Upgrade Scripts](releaseupdatedb401-cos-upgrade-scripts.md)

[ReleaseUpdateDB401\_Ledger Upgrade Scripts](releaseupdatedb401-ledger-upgrade-scripts.md)

[ReleaseUpdateDB41\_Administration Upgrade Scripts](releaseupdatedb41-administration-upgrade-scripts.md)

[ReleaseUpdateDB41\_Asset Upgrade Scripts](releaseupdatedb41-asset-upgrade-scripts.md)

[ReleaseUpdateDB41\_Basic Upgrade Scripts](releaseupdatedb41-basic-upgrade-scripts.md)

[ReleaseUpdateDB41\_Bank Upgrade Scripts](releaseupdatedb41-bank-upgrade-scripts.md)

[ReleaseUpdateDB41\_Cust Upgrade Scripts](releaseupdatedb41-cust-upgrade-scripts.md)

[ReleaseUpdateDB41\_Invent Upgrade Scripts](releaseupdatedb41-invent-upgrade-scripts.md)

[ReleaseUpdateDB41\_Ledger Upgrade Scripts](releaseupdatedb41-ledger-upgrade-scripts.md)

[ReleaseUpdateDB41\_Prod Upgrade Scripts](releaseupdatedb41-prod-upgrade-scripts.md)

[ReleaseUpdateDB41\_Proj Upgrade Scripts](releaseupdatedb41-proj-upgrade-scripts.md)

[ReleaseUpdateDB41\_Req Upgrade Scripts](releaseupdatedb41-req-upgrade-scripts.md)

[ReleaseUpdateDB41\_smm Upgrade Scripts](releaseupdatedb41-smm-upgrade-scripts.md)

[ReleaseUpdateDB41\_Vend Upgrade Scripts](releaseupdatedb41-vend-upgrade-scripts.md)

[ReleaseUpdateTransform40\_InventPurchAcc Upgrade Scripts](releaseupdatetransform40-inventpurchacc-upgrade-scripts.md)

[ReleaseUpdateTransform50\_InventPurchAcc Upgrade Scripts](releaseupdatetransform50-inventpurchacc-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Admin Upgrade Scripts](releaseupdatetransformdb40-admin-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Administration Upgrade Scripts](releaseupdatetransformdb40-administration-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Asset Upgrade Scripts](releaseupdatetransformdb40-asset-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Bank Upgrade Scripts](releaseupdatetransformdb40-bank-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Basic Upgrade Scripts](releaseupdatetransformdb40-basic-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_CRM Upgrade Scripts](releaseupdatetransformdb40-crm-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Cust Upgrade Scripts](releaseupdatetransformdb40-cust-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_CustBOE\_JP Upgrade Scripts](releaseupdatetransformdb40-custboe-jp-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_EcoResDimG Upgrade Scripts](releaseupdatetransformdb40-ecoresdimg-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_EcoResProduct Upgrade Scripts](releaseupdatetransformdb40-ecoresproduct-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_FimDimGroup Upgrade Scripts](releaseupdatetransformdb40-fimdimgroup-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_FiscalCal Upgrade Scripts](releaseupdatetransformdb40-fiscalcal-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_GAB Upgrade Scripts](releaseupdatetransformdb40-gab-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_HCM Upgrade Scripts](releaseupdatetransformdb40-hcm-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_HRM Upgrade Scripts](releaseupdatetransformdb40-hrm-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Invent Upgrade Scripts](releaseupdatetransformdb40-invent-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_InventPurch Upgrade Scripts](releaseupdatetransformdb40-inventpurch-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_InventTable Upgrade Scripts](releaseupdatetransformdb40-inventtable-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_InventTrans Upgrade Scripts](releaseupdatetransformdb40-inventtrans-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Jmg Upgrade Scripts](releaseupdatetransformdb40-jmg-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Ledger Upgrade Scripts](releaseupdatetransformdb40-ledger-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_LedgerTrx Upgrade Scripts](releaseupdatetransformdb40-ledgertrx-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Prod Upgrade Scripts](releaseupdatetransformdb40-prod-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Prod2 Upgrade Scripts](releaseupdatetransformdb40-prod2-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Proj Upgrade Scripts](releaseupdatetransformdb40-proj-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Transptn Upgrade Scripts](releaseupdatetransformdb40-transptn-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_UnitOfMeasure Upgrade Scripts](releaseupdatetransformdb40-unitofmeasure-upgrade-scripts.md)

[ReleaseUpdateTransformDB40\_Vend Upgrade Scripts](releaseupdatetransformdb40-vend-upgrade-scripts.md)

[ReleaseUpdateTransformDB41\_Basic Upgrade Scripts](releaseupdatetransformdb41-basic-upgrade-scripts.md)

[ReleaseUpdateTransformDB41\_Prod Upgrade Scripts](releaseupdatetransformdb41-prod-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Admin Upgrade Scripts](releaseupdatetransformdb50-admin-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Administration Upgrade Scripts](releaseupdatetransformdb50-administration-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Asset Upgrade Scripts](releaseupdatetransformdb50-asset-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Bank Upgrade Scripts](releaseupdatetransformdb50-bank-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Basic Upgrade Scripts](releaseupdatetransformdb50-basic-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_CRM Upgrade Scripts](releaseupdatetransformdb50-crm-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Cust Upgrade Scripts](releaseupdatetransformdb50-cust-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_CustBOE\_JP Upgrade Scripts](releaseupdatetransformdb50-custboe-jp-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_EcoResDimG Upgrade Scripts](releaseupdatetransformdb50-ecoresdimg-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_EcoResProduct Upgrade Scripts](releaseupdatetransformdb50-ecoresproduct-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_EnterprisePortl Upgrade Scripts](releaseupdatetransformdb50-enterpriseportl-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_FimDimGroup Upgrade Scripts](releaseupdatetransformdb50-fimdimgroup-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_FiscalCal Upgrade Scripts](releaseupdatetransformdb50-fiscalcal-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_GAB Upgrade Scripts](releaseupdatetransformdb50-gab-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_GLS Upgrade Scripts](releaseupdatetransformdb50-gls-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_HCM Upgrade Scripts](releaseupdatetransformdb50-hcm-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_HRM Upgrade Scripts](releaseupdatetransformdb50-hrm-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Invent Upgrade Scripts](releaseupdatetransformdb50-invent-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_InventPurch Upgrade Scripts](releaseupdatetransformdb50-inventpurch-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_InventTable Upgrade Scripts](releaseupdatetransformdb50-inventtable-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_InventTrans Upgrade Scripts](releaseupdatetransformdb50-inventtrans-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Jmg Upgrade Scripts](releaseupdatetransformdb50-jmg-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Ledger Upgrade Scripts](releaseupdatetransformdb50-ledger-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_LedgerTrx Upgrade Scripts](releaseupdatetransformdb50-ledgertrx-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Prod Upgrade Scripts](releaseupdatetransformdb50-prod-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Proj Upgrade Scripts](releaseupdatetransformdb50-proj-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Req Upgrade Scripts](releaseupdatetransformdb50-req-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_SMA Upgrade Scripts](releaseupdatetransformdb50-sma-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Transptn Upgrade Scripts](releaseupdatetransformdb50-transptn-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Trv Upgrade Scripts](releaseupdatetransformdb50-trv-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_UnitOfMeasure Upgrade Scripts](releaseupdatetransformdb50-unitofmeasure-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_User Upgrade Scripts](releaseupdatetransformdb50-user-upgrade-scripts.md)

[ReleaseUpdateTransformDB50\_Vend Upgrade Scripts](releaseupdatetransformdb50-vend-upgrade-scripts.md)

## See also

[Data Upgrade Scripts for Microsoft Dynamics AX 2012](data-upgrade-scripts-for-microsoft-dynamics-ax-2012.md)

[Target Upgrade Scripts](target-upgrade-scripts.md)

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

