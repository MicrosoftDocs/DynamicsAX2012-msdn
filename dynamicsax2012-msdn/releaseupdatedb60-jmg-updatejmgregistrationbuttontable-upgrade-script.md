---
title: ReleaseUpdateDB60_Jmg.updateJmgRegistrationButtonTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.updateJmgRegistrationButtonTable Upgrade Script
ms:assetid: 5999a037-afe4-35b9-87a3-982ea0e82a98
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736284(v=AX.60)
ms:contentKeyID: 49708459
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.updateJmgRegistrationButtonTable Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Jmg</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateJmgRegistrationButtonTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the JmgRegistrationSetup, JmgRegistrationButtonTable, and JmgRegistrationActionPaneTable tables to support the new button system for the registration client.</p></td>
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
<td><p>JmgRegistrationSetup</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationButtonTable</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationActionPaneTable</p></td>
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
<td><p>JmgRegistrationButtonTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationActionPaneTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>ActionPaneSetupId</p></td>
<td><p>JmgActionPaneSetupRecId</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>ShowActivities</p></td>
<td><p>JmgFastTabAppearance</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>ShowMessages</p></td>
<td><p>JmgFastTabAppearance</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationsetup</p></td>
<td><p>ShowPreview</p></td>
<td><p>JmgFastTabAppearance</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>ShowStatus</p></td>
<td><p>JmgFastTabAppearance</p></td>
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
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton1</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton2</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton3</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton4</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton5</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton6</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton7</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton8</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton9</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton10</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton11</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>PrimaryButton12</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton1</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton2</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton3</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton4</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton5</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton6</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton7</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton8</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton9</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton10</p></td>
</tr>
<tr class="odd">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton11</p></td>
</tr>
<tr class="even">
<td><p>JmgRegistrationSetup</p></td>
<td><p>SecondaryButton12</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

