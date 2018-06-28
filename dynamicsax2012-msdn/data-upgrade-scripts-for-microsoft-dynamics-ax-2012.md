---
title: Data Upgrade Scripts for Microsoft Dynamics AX 2012
TOCTitle: Data Upgrade Scripts for Microsoft Dynamics AX 2012
ms:assetid: 30eee91e-6b1d-44ce-8cac-b6a6e89bc954
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736078(v=AX.60)
ms:contentKeyID: 49707492
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Data Upgrade Scripts for Microsoft Dynamics AX 2012 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic provides information about upgrade scripts in the SYS or GLS layer that are implemented in Microsoft Dynamics AX 2012. Upgrade scripts are run as part of the data upgrade process to upgrade data from a source Microsoft Dynamics AX database to Microsoft Dynamics AX 2012. For information about how to define data upgrade scripts, see the [How to: Write Data Upgrade Script white paper](http://go.microsoft.com/fwlink/?linkid=212587). You may find a later version of this content on the download center, see [Data Upgrade Script Reference](http://go.microsoft.com/fwlink/?linkid=234380).

The following table provides terms and definitions related to the upgrade framework:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Term</p></th>
<th><p>Definition</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Source environment or source system</p></td>
<td><p>The Microsoft Dynamics AX system that is to be upgraded.</p>
<p>The supported source systems for direct upgrade to Microsoft Dynamics AX 2012 are as follows:</p>
<ul>
<li><p>Microsoft Dynamics AX 4.0</p></li>
<li><p>Microsoft Dynamics AX 2009</p></li>
</ul>

> [!note]  
> <P>The upgrade starts and the source environment is still live, but there is minimal effect to the live system.</P>

</td>
</tr>
<tr class="even">
<td><p>Target environment or target system</p></td>
<td><p>Microsoft Dynamics AX 2012</p></td>
</tr>
<tr class="odd">
<td><p>Transformation</p></td>
<td><p>Data is transformed between the source and target environment by using field mapping and joins between necessary tables.</p>
<p>Examples include conversion of the CustTable table to the DirParty* tables.</p></td>
</tr>
<tr class="even">
<td><p>Shadow table</p></td>
<td><p>Auxiliary table created in the source environment. The shadow tables will contain all fields from the source tables which have to be upgraded.</p></td>
</tr>
<tr class="odd">
<td><p>Dictionary table</p></td>
<td><p>New target Microsoft Dynamics AX 2012 tables. Dictionary tables are imported into the source environment for the application pre-upgrade checklist, and upgrade script execution as needed. The definition of the table must match the target system. The dictionary tables will be copied to the target as they are. Dictionary tables are also named upgrade staging tables.</p></td>
</tr>
</tbody>
</table>


The data upgrade framework runs the data upgrade scripts that transform an earlier version of the Microsoft Dynamics AX database to the current version. There are two categories of upgrade scripts:

  - Preprocessing upgrade scripts
    
    The X++ method is implemented by using the upgrade framework APIs to run on the source system (Microsoft Dynamics AX 4.0 or Microsoft Dynamics AX 2009). Preprocessing upgrade scripts prepare the data within staging tables in preparation for the final data upgrade. Preprocessing upgrade scripts are installed when you import the preprocessing upgrade XPO from the installation media in the source environment. These upgrade scripts are run by using the preprocessing upgrade framework.

  - Target upgrade script
    
    X++ methods are implemented by using the attribute based upgrade framework to run on the target system (Microsoft Dynamics AX 2012). Target upgrade scripts are run to do the final transformation to data before the Microsoft Dynamics AX system is available to users. Target upgrade scripts are installed on the Microsoft Dynamics AX 2012 system as a part of the installation for upgrade.

## Preprocessing Upgrade Scripts

The preprocessing upgrade checklist is a navigation pane that guides you through the preprocessing of the data upgrade steps in the source environment. For information about starting the preprocessing upgrade checklist, see the **Start the Preprocessing upgrade checklist** topic in the [Upgrade Guide](http://go.microsoft.com/fwlink/?linkid=212541).

Preprocessing upgrade scripts are derived from the class ReleaseUpdateTransformDB. Preprocessing upgrade script classes have the following naming convention: ReleaseUpdateTransformDBxx\_\<module name\>. The **DBxx** corresponds to which source version of Microsoft Dynamics AX that the script applies to. For example, the ReleaseUpdateTransformDB40\_Bank upgrade script applies to Microsoft Dynamics AX 4.0 as indicated by the DB40 in the name. When an upgrade script has DB50 in the name, the script corresponds to both Microsoft Dynamics AX 4.0 and Microsoft Dynamics AX 2009.

The following list describes the types of preprocessing upgrade scripts:

  - Live preprocessing script that is implemented to run on a live source system. The Microsoft Dynamics AX system is available to the user and the upgrade occurs in the background. Live preprocessing scripts write prepared data into the shadow and dictionary tables that were created by importing the preprocessing XPOs. These scripts must be implemented by using row-by-row operations, and commit after a predetermined number of transactions. To schedule live preprocessing scripts, in the preprocessing upgrade checklist, click **Run live preprocessing scripts**. The scripts that run are specified in the initTransformationJobs method with a definition of SetLivePreProcessingScript in ReleaseUpdateTransformDB40\_ and ReleaseUpdateTransformDB50\_ classes.

  - Delta preprocessing scripts are implemented to check for changes to the production data that have occurred since you started running the live preprocessing scripts. Similar to the live preprocessing scripts, the delta scripts processes the updated data into the shadow and dictionary tables. Delta scripts are designed to run multiple times before entering into the single-user mode. To schedule Delta preprocessing scripts, in the preprocessing upgrade checklist, click **Run delta preprocessing scripts**. The scripts that run are specified in the initTransformationJobs method with a definition of SetDeltaPreProcessingScript in the ReleaseUpdateTransformDB40\_ and ReleaseUpdateTransformDB50\_ classes.

  - Single-User preprocessing scripts are implemented to run on the source system during single-user mode. Single-user mode occurs on the source system to make sure that the system is unavailable for business use. In single-user mode, only an upgrade user who has administrative permissions is connected. No other users can start a client session when the source system is in final preprocessing and source data is being bulk copied to the Microsoft Dynamics AX 2012 target system. Single-user preprocessing scripts must be written as set-based operations. To schedule single-user preprocessing scripts, in the preprocessing upgrade checklist, click **Run single-user mode preprocessing scripts**. The scripts that run are specified in the initTransformationJobs method with a definition of SetSingleuserPreProcessingScript in ReleaseUpdateTransformDB40\_ and ReleaseUpdateTransformDB50\_ classes.

  - Upgrade Readiness scripts are implemented to help identify the issues that cause an upgrade to fail. These scripts read AOT metadata or data and then categorize the results into an error or advisory in the upgrade validation result. Errors must be fixed before you continue with the upgrade. Advisory are designed to improve the upgrade experience by pointing out issues which may improve the efficiency of upgrade, or issues which require manual actions. To schedule upgrade readiness scripts, in the preprocessing upgrade checklist, click on the **Upgrade Readiness check**. The scripts that run are specified in the initTransformationJobs method with a definition of SetValidatePreProcessingScript in ReleaseUpdateTransformDB40\_ and ReleaseUpdateTransformDB50\_ classes.

## Target Upgrade Scripts

Upgrade script methods that upgrade data from Microsoft Dynamics AX 4.0 or Microsoft Dynamics AX 2009 to Microsoft Dynamics AX 2012 are in the ReleaseUpdateDB60\_\<module name\> class. These classes are derived from the ReleaseUpdateDB base class.

The following list describes the types of target upgrade scripts:

  - Presynchronize upgrade scripts are implemented to make metadata changes before the step to create tables. For example, presynchronize scripts are used to map the database table or fields on the source Microsoft Dynamics AX system to the database table or fields on the target system. This table-to-table and column-to-column mapping prepares the source-to-target upgrade model for data copy from source to target. Other kinds of presynchronize scripts disable unique index in preparation for data upgrade and avoid duplicate key error. This action is undone during the postsynchronize step. The scripts that run are methods with an UpgradeScriptStageAttribute of PreSync. They are specified in the in ReleaseUpdateDB401\_, ReleaseUpdateDB41\_ and ReleaseUpdateDB60\_ classes.

  - Postsynchronization upgrade scripts contain the bulk of the data upgrade. Company-specific business data is upgraded in postsynchronization upgrade scripts. Postsynchronization also reverses the metadata changes that were made during the presynchronize step.
    
    During postsynchronization, upgrade scripts run to update existing data when it is required and populate new tables and columns. Running upgrade scripts and any inter-dependencies are controlled by the upgrade framework. Upgrade scripts are implemented for any major version change. If you upgrade from Microsoft Dynamics AX 4.0 with a supported service pack to Microsoft Dynamics AX 2012, the upgrade framework will execute the following three sets of upgrade scripts:
    
      - Upgrade scripts associated with Microsoft Dynamics AX 4.0 to Microsoft Dynamics AX 4.0 SP1 that is represented by version 4.01 or v401.
    
      - Upgrade scripts associated with Microsoft Dynamics AX 4.01 to Microsoft Dynamics AX 2009 that is represented by version 4.1 or v41.
    
      - Upgrade scripts associated with Microsoft Dynamics AX 2009 to Microsoft Dynamics AX 2012 that is represented by version 6.0 or v60.
    
    The scripts that run are methods with an UpgradeScriptStageAttribute of PostSync, the ones specified in the in ReleaseUpdateDB401\_, ReleaseUpdateDB41\_ and ReleaseUpdateDB60\_ classes.

  - Additional upgrade scripts are implemented to run outside the core data upgrade. Thus reduces the upgrade downtime for the core data upgrade. An example is upgrading metadata that is related to AIF endpoints. The scripts that run are methods with an UpgradeScriptStageAttribute of Additional, the scripts are specified in the ReleaseUpdateDB401\_, ReleaseUpdateDB41\_ and ReleaseUpdateDB60\_ classes.

## Reasons for Data Upgrade Scripts

Upgrade scripts are implemented for the following operations:

  - Deleting a table and saving data

  - Deleting a field and saving data

  - Adding or changing unique indexes

  - Changing a non-unique index into a unique index

  - Restructuring where data is stored. For example, moving data from one field to another

  - Correcting old data inconsistencies

  - Populating new tables with existing data

  - Populating new fields with existing data or a default value that differs from the default value for the data type

## Finding Upgrade Script Documentation

There are several ways that the upgrade scripts are documented in this Help file. You can view them in the following ways:

  - [Tables Affected, Listed by Table](tables-affected-listed-by-table.md): If you want to see how a particular table is affected by upgrade, use this topic. It lists the affected tables and the scripts that affect them.

  - [Tables Affected, Listed by Script](tables-affected-listed-by-script.md): If you want to see which tables a particular script affects, use this topic. It lists each script and the tables they affect.

  - [Modules Affected, Listed by Module](modules-affected-listed-by-module.md): If you want to see how a particular module is affected by upgrade, use this topic. It lists the affected modules and the scripts that affect them.

  - [Modules Affected, Listed by Script](modules-affected-listed-by-script.md): If you want to see which modules a particular script affects, use this topic. It lists each script and the modules they affect.

  - [Preprocessing Data Upgrade Scripts](preprocessing-data-upgrade-scripts.md): If you want to see which scripts are run before the upgrade to prepare the data, use this topic. It lists all scripts that belong to the preprocessing category.

  - **Script detail**: Each script is also documented and sorted under the topic that has the same name as the class name of the script. These topics are useful if you want to see the actions that a script performs.


> [!NOTE]
> <P>If you are upgrading directly from Microsoft Dynamics AX 4.0 to Microsoft Dynamics AX 2012, upgrade scripts from the ReleaseUpdateDB41_&lt;module name&gt; class will also be run. For more information about the upgrade scripts from these classes, see <A href="http://go.microsoft.com/fwlink/?linkid=191490">Microsoft Dynamics AX 2009 Upgrade Script Reference</A>. A PartnerSource logon is required to view these pages.</P>



## See also

[Upgrade Guide](http://go.microsoft.com/fwlink/?linkid=212541)

[How to: Write Data Upgrade Script whitepaper](http://go.microsoft.com/fwlink/?linkid=212587)

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

