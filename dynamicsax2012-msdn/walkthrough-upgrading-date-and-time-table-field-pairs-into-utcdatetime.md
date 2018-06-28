---
title: 'Walkthrough: upgrading date and time table field pairs into UtcDateTime'
TOCTitle: 'Walkthrough: upgrading date and time table field pairs into UtcDateTime'
ms:assetid: c6e4a9b6-aa44-4cbe-a207-4320974d487b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dd362070(v=AX.60)
ms:contentKeyID: 35251131
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: upgrading date and time table field pairs into UtcDateTime 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

If custom **Date** or **Time** fields have been added to Microsoft Dynamics AX, you need to decide whether those fields should be merged into new **UtcDateTime** fields. **UtcDateTime** fields store date/time data in Coordinated Universal Time (UTC).


> [!NOTE]
> <P>This information is relevant when you must upgrade from any version earlier than Microsoft Dynamics AX 2009, to Microsoft Dynamics AX 2009 or later.</P>



During upgrades it is common for a pair of fields, one **Date** and one **Time**, to be merged into a new **UtcDateTime** field. **UtcDateTime** enables every part of your organization to see the date/time value automatically adjusted for their local time zone.

If **Date** and **Time** fields must be merged into **UtcDateTime** fields, you must make certain preparations before you run the upgrade. The **UtcDateTime** preparations are only some of the many preparations that you will make before you run the Microsoft Dynamics AX 2009 upgrade process on your production environment.

This walkthrough illustrates the following tasks:

  - Turning on **SysDeletedObjects41** in production

  - Installing a test database

  - Installing the new version in a test environment

  - Turning on **SysDeletedObjects41** in Test

  - Identifying date and time fields to upgrade

  - Renaming fields to have the prefix DEL\_

  - Assigning **SysDeletedObjects41** to the renamed fields

  - Adding replacement **UtcDateTime** fields

  - Updating X++ code to use the new **UtcDateTime** fields

  - Running the code upgrade on your test environment

  - Overview of the next steps

  - Adding a method to ReleaseUpdateDB41\_\*

  - Registering your new method

  - Summary of method relationships

  - Rerunning the code upgrade on your test environment

  - Handling special cases

  - Running the upgrade on your production environment

  - Consider other details

## Prerequisites

This walkthrough is written for the administrator (or the lead developer) who must upgrade to Microsoft Dynamics AX 2009.

To complete this walkthrough, you will need:

  - A temporary installation of Microsoft Dynamics AX 2009, its Application Object Server (AOS), and its client including the Application Object Tree (AOT)

  - A license file that has access to the Microsoft Dynamics AX 2009 client

  - A database server accessed by the Microsoft Dynamics AX 2009 (AOS)

## Turning On SysDeletedObjects41 in Production

This procedure pertains to your production environment that you have not yet upgraded. You use the configuration key SysDeletedObjects41 to tag items that you want to be able to easily delete after the upgrade completes.

In this procedure you will use the **Navigation Pane** to keep objects that you mark for deletion. Later you can clear this setting and the objects will be deleted.

### To turn SysDeletedObjects41 on

1.  In the **Navigation Pane**, click **Administration**, click **Setup**, click **System**, and then click **Configuration**.

2.  In the **Configuration** form that appears, expand **Administration**, to reveal the **Keep update objects 41** node.

3.  Select the **Keep update objects 41** the check box.

## Installing a Test Database

In this procedure you will create the test database environment that is required to support the preparation steps for the eventual upgrade of your production system. After your production system is upgraded, this test environment can be discarded.

### To install a test database

1.  Create an empty database on a test database server.

2.  As an option, load a copy of your production database into the empty database.

If you choose an empty database, the tables and other structures will be created when you connect the new Microsoft Dynamics AX to it. The synchronization process will create the structures.

## Installing the New Version in a Test Environment

In this procedure you must install Microsoft Dynamics AX 2009 (or a newer version of Microsoft Dynamics AX) that you intend to upgrade your production system to. This installation is to a test environment that can later be discarded.

## Turning On SysDeletedObjects41 in Test

This procedure pertains to the new Microsoft Dynamics AX test environment that your production environment will be upgraded to.

Next, you will use the **Navigation Pane** to keep objects that you mark for deletion. Later you can clear this setting and the objects will be deleted.

The technique is that same as was previously described for the production environment.

## Identifying Date and Time Fields to Upgrade

In this procedure you will scan all the custom **Date** and **Time** fields that have been added to your installation. You must decide which of those fields will be upgraded to the new **UtcDateTime** type.

Make a list of all the custom **Date** and **Time** fields that must be upgraded.

### To decide whether to upgrade a date or time field to utcdatetime

1.  Identify pairs of Date and Time fields that are used together (in the same table) to store a precise moment. In such pairs, both fields might share the same name distinguished only by their suffix of **Date** or **Time**.
    

    > [!NOTE]
    > <P>An example could be a field pair of <STRONG>YourMeetingDate</STRONG> and <STRONG>YourMeetingTime</STRONG>. A new field <STRONG>YourMeetingDateTime</STRONG> would be a good replacement for this pair.</P>



2.  Identify **Date** fields that are not paired with a **Time** field, but that do imply a local time. Some legal or contractual obligations of due dates might be examples where a time such as (midnight or 00:00) is implied.

3.  Identify **Time** fields that are not paired with a **Date** field, but that would be more useful if represented in UTC. Such time fields are rare.

## Renaming Fields to Have the Prefix DEL\_

In this procedure you will rename the Date and Time fields that you identified earlier. Each must be given the four character prefix DEL\_.

### To rename a field in a table

1.  In the AOT, expand the **Data Dictionary** node, and then expand **Tables**.

2.  Expand the specific table that contains a field that you want to rename, and then expand the **Fields** node.

3.  Right-click the field that you want to rename, and then select **Properties**.

4.  In the **Properties** window, click the text box for the **Name**.

5.  Type the DEL\_ prefix to modify the name, and then press ENTER.

## Assigning SysDeletedObjects41 to the Renamed Fields

In this procedure you will assign the SysDeletedObjects41 configuration key to the **Date** and **Time** fields that you want to upgrade to **UtcDateTime**.

Each version of Microsoft Dynamics AX has a configuration key with a similar name, except the version number at the end differs. Here the version suffix **41** refers to Microsoft Dynamics AX 2009.

By assigning **SysDeletedObjects41** to a field that you renamed with the DEL\_ prefix, you track all the fields that will be obsolete after the production environment is upgraded. The configuration assignment also makes it easy to delete all obsolete fields at one time.

### To assign the SysDeletedObjects41 configuration key to fields

1.  In the AOT, expand **Data Dictionary**, expand your table, and then expand **Fields**.

2.  Right-click the field that has the DEL\_ prefix, and then select **Properties**.

3.  In the **Properties** window, click the drop-down list for the **ConfigurationKey** property, and then select **SysDeletedObjects41**.

## Adding Replacement UtcDateTime Fields

In this procedure you will add a **UtcDateTime** field for every obsolete **Date** field, **Time** field, or field pair that you want to replace during upgrade.

### To add replacement utcDateTime fields

1.  In the AOT, expand **Data Dictionary**, and then expand **Tables**.

2.  Expand the specific table that needs a new **UtcDateTime** field.

3.  Right-click the **Fields** node, click **New**, and then select **UtcDateTime**.

4.  Right-click the new field node, and then select **Properties**.

5.  In the **Properties** window, change the **Name**, and any other properties as needed.

## Updating X++ Code to Use the New UtcDateTime Fields

In this procedure you will scan your X++ code to find all references to the **Date** or **Time** fields that you are replacing.

One way to find the references is to recompile all your X++ code. The compile errors that occur from the earlier field renames indicate the references that must be updated.

You must manually determine the X++ code change that is needed in each case. The new code must reference the new **UtcDateTime** field.

### To update X++ code to use the new utcDateTime fields

1.  Find the references to the old DEL\_ fields by recompiling all your X++ code.

2.  Research each error to determine how to fix the code by referencing the new **UtcDateTime** field.

3.  Recompile your X++ code change.

### ![Dd362070.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd362070.collapse_all(en-us,AX.60).gif")UtcDateTime Functions

The following table lists some of the functions that can manipulate **UtcDateTime** values.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Function</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DateTimeUtil class</p></td>
<td><p>This has many methods for manipulating utcDateTime values.</p></td>
</tr>
<tr class="even">
<td><p>Global class</p></td>
<td><p>The Global class has some methods for manipulating utcDateTime values, including the following:</p>
<ul>
<li><p>clrSystemDateTime2UtcDateTime</p></li>
<li><p>dateToBeginUtcDateTime</p></li>
<li><p>dateToEndUtcDateTime</p></li>
<li><p>utcDateTime2SystemDateTime</p></li>
<li><p>utcDateTimeNull</p></li>
</ul>
<p><strong>Note</strong>   utcDateTime2SystemDateTime refers to the .NET Framework class System.DateTime. This function is equivalent to clrSystemDateTime2UtcDateTime (where the prefix clr refers to the common language runtime of the .NET Framework).</p></td>
</tr>
<tr class="odd">
<td><p>Functions</p></td>
<td><p>The system has X++ functions for manipulating utcDateTime values, including the following:</p>
<ul>
<li><p>datetime2Str</p></li>
<li><p>str2Datetime</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Running the Code Upgrade on Your Test Environment

In this procedure you will run the code upgrade function on your test environment from the Microsoft Dynamics AX 2009 client. This produces an .AOD file that is used when you perform the upgrade on your production system.

This procedure can be run many times. You might rerun this procedure after each change, instead of waiting until after you make all changes. Repeated runs after smaller sets of changes might make problems easier to diagnose or fix.

For more information, see the documentation for the Microsoft Dynamics AX upgrade.

### To run the code upgrade

1.  In the client's menu, click **Tools**, click **Development tools**, and then click **Code upgrade**.

2.  You will see four upgrade related actions. Run each of these actions, one at a time, in the sequence that they appear in the menu.
    
    1.  **Detect code upgrade conflicts**
    
    2.  **Compare layers**
    
    3.  **Estimation report**
    
    4.  **Parameters**

## Overview of the Next Steps

In the next procedures you will write the X++ code necessary for the upgrade. You will add a method to a class that is provided by Microsoft Dynamics AX 2009. Your method will not be called during the phase of manual preparations. Instead you will register your new method, which will cause the production upgrade process to start your new method.

## Adding a Method to ReleaseUpdateDB41\_\*

In this procedure you will add a method to one of the classes that is named by the ReleaseUpdateDB41\_\* pattern. There are several such classes, each intended for a particular module. Each table is assigned a configuration key. The configuration key indicates the module that the table belongs to. The trailing asterisk (\*) in the name pattern is a placeholder for a module identifier. You should add your method to the class that corresponds to the module of the affected table. If you are unsure of which class to use, you can use the ReleaseUpdateDB41\_Basic class.

By convention and for consistency, the method name should begin with updateToDateTime\_\*. Include your name as the suffix for easy identification.


> [!NOTE]
> <P>Notice that some method names that look the same at first glance actually begin with different words, either update or upgrade. They are not the same method.</P>



The method that you add calls a system-provided method named upgradeToDateTime. The upgradeToDateTime method performs an SQL insert into the DEL\_SysUpgradeTimeZone table. Your method can make several such calls.

### To add a method to ReleaseUpdateDB41\_Basic

1.  In the AOT, expand the **Classes** node, and then expand **ReleaseUpdateDB41\_Basic**.

2.  Right-click **Methods**, and then select **New Method**.

3.  Add a new instance method that resembles the following example. The name of your method can be anything unique. You new method must call upgradeToDateTime, as shown in the example.
    

    > [!NOTE]
    > <P>Pass zero (0) as the value for the fieldId of your time column if your date column is not paired with a time column.</P>

    

    > [!NOTE]
    > <P>The final parameter shown is optional, and the default is the value shown (classnum for ReleaseUpdateDB_TimezoneUpgrade).</P>

    
        void updateToDateTime_Jane
        {
            ReleaseUpdateDB41_Basic ::upgradeToDateTime
                (
                tableNum( YourActivitiesTable )
                ,fieldNum( YourActivitiesTable ,YourMeetingStartDateTime )
                ,fieldNum( YourActivitiesTable ,DEL_YourMeetingStartDate )
                ,fieldNum( YourActivitiesTable ,DEL_YourMeetingStartTime )
                ,classNum( ReleaseUpdateDB_TimezoneUpgrade )
                );
        }

4.  In the code editor window, click the save icon, and then close the window.

#### ![Dd362070.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd362070.collapse_all(en-us,AX.60).gif")Class ReleaseUpdateDB\_TimezoneUpgrade

In the previous code example, the ReleaseUpdateDB\_TimezoneUpgrade class is given as a parameter. The class has a method named runSQLCode\_UpdateDateToUTCDateTime. This method updates your new **UtcDateTime** type field by assigning a UTC time value to it (and a time zone to a hidden related field). The UTC value is derived from your obsolete **Date** and **Time** field pair, and from the local time zone of your AOS.

The example call to upgradeToDateTime leads to a call of one of the two methods.

#### ![Dd362070.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dd362070.collapse_all(en-us,AX.60).gif")Consider the Affected Module

The ReleaseUpdateDB41\_Basic class is not specific to any one module. There are several classes that resemble this class, but that are intended to hold code that is specific to a particular module. One such class is ReleaseUpdateDB41\_smm. The others classes follow the naming convention of ReleaseUpdateDB41\_\*. Your new method can be added to the \*\_Basic class. However, you are encouraged to add it to the similar class named for the module that contains the items that your method is upgrading.

## Registering Your New Method

In this procedure you will write X++ code to register your new method for the eventual production upgrade process. In the example, you call the method addSharedJob. The parameters will be the name of the new method that you added, and the class on which you added your method.

### To register your new method

1.  In the AOT, expand the **Classes**, expand **ReleaseUpdateDB41\_Basic**, and then expand **Methods**.

2.  Right-click **initPreSyncJobs**, and then select **Edit**.

3.  In the editor window, inside the method, write the call that is shown in the following example.
    
    ``` 
        this .addSharedJob
            (
            methodStr( ReleaseUpdateDB41_Basic
                ,updateToDateTime_Jane
                )
            ,"Handles new fields like YourMeetingStartDateTime."
            )
    ```

4.  Click the save icon, and close the editor.

For more information, see [How to write upgrade scripts](http://go.microsoft.com/fwlink/?linkid=115169&clcid=0x409).

## Summary of Method Relationships

The following table provides a summary of the relationships between the classes and their methods, and other objects that are discussed in the previous sections.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Initiator</p></th>
<th><p>Operand</p></th>
<th><p>Relationship</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_YourMeetingStartDate, DEL_YourMeetingStartTime (table fields)</p></td>
<td><p>YourMeetingStartDateTime</p></td>
<td><p>Data:</p>
<p>Data is read from DEL_YourMeetingStartDate and DEL_YourMeetingStartTime. Time zone information is applied, and then the data is stored in the new field YourMeetingStartDateTime.</p></td>
</tr>
<tr class="even">
<td><p>.updateToDateTime_You method (on class ReleaseUpdateDB41_Basic)</p></td>
<td><p>ReleaseUpdateDB41_Basic ::upgradeToDateTime</p></td>
<td><p>Call:</p>
<p>updateToDateTime_You calls upgradeToDateTime.</p></td>
</tr>
<tr class="odd">
<td><p>ReleaseUpdateDB41_Basic ::upgradeToDateTime</p></td>
<td><p>ReleaseUpdateDB_TimezoneUpgrade</p>
<p>/* .runSQLCode_UpdateDateToUTCDateTime</p>
<p>*/</p></td>
<td><p>Parameter:</p>
<p>The operand class is a parameter into upgradeToDateTime. An important method on the operand class is runSQLCode_UpdateDateToUTCDateTime. When you provide this operand class as a parameter, it is this method that is ultimately run.</p></td>
</tr>
<tr class="even">
<td><p>ReleaseUpdateDB41_Basic ::upgradeToDateTime</p></td>
<td><p>DEL_SysUpgradeTimeZone (table)</p></td>
<td><p>SQL insert:</p>
<p>The method performs an insert into the operand table. This table is read by the processes that upgrade your production environment.</p></td>
</tr>
<tr class="odd">
<td><p>ReleaseUpdateDB41_Basic .initPreSyncJobs</p></td>
<td><p>ReleaseUpdateDB41_Basic .addSharedJob</p></td>
<td><p>Call:</p>
<p>initPreSyncJobs calls addSharedJob.</p></td>
</tr>
<tr class="even">
<td><p>ReleaseUpdateDB41_Basic .addSharedJob</p></td>
<td><p>updateToDateTime_You method (on class ReleaseUpdateDB41_Basic or on a similar class that is more specific to a module)</p></td>
<td><p>Parameter:</p>
<p>updateToDateTime_You (a method name) is a parameter into addSharedJob.</p></td>
</tr>
</tbody>
</table>


## Rerunning the Code Upgrade on Your Test Environment

This procedure was described previously.

## Handling Special Cases

It is possible that your customized **Date** and **Time** fields might be designed to work with specialized X++ code. Special application rules might be involved.

The following table describes how to handle special cases.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Special case</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Extend the class</p>
<p>ReleaseUpdateDB_TimezoneUpgrade</p></td>
<td><p>You can extend this class to provide the specialized logic that is required to handle your special case <strong>Date</strong> and <strong>Time</strong> fields.</p>
<p>The class ReleaseUpdateDB_TimezoneActivityUpgrade is a sample that you can mimic. This derived class contains an override of the runSQLCode_UpdateDateToUTCDateTime method.</p></td>
</tr>
<tr class="even">
<td><p>Add your method to a class similar to but different from ReleaseUpdateDB41_Basic</p></td>
<td><p>The AOT shows there are several classes named by the pattern ReleaseUpdateDB41_*. Some correspond to different modules in Microsoft Dynamics AX. You can add your method to one of those classes</p></td>
</tr>
<tr class="odd">
<td><p>Bypass the upgrade of application <strong>Date</strong> and <strong>Time</strong> fields that ship with Microsoft Dynamics AX</p></td>
<td><p>It is possible that external systems access a <strong>Date</strong> and <strong>Time</strong> field pair. It might not yet be plausible to modify the external system to switch to a replacement <strong>UtcDateTime</strong> field.</p>
<p>You can bypass the upgrade of a particular <strong>Date</strong> and <strong>Time</strong> pair by commenting out the appropriate calls in one of the ReleaseUpdateDB41_* classes.</p></td>
</tr>
<tr class="even">
<td><p>Administrator has added a table for synchronization at application startup</p></td>
<td><p>You may have added a call to the syncTable method in Application .syncApplTables. This practice is not recommended.</p>
<p>Tables that you have added to syncApplTables are not properly upgraded for <strong>UtcDateTime</strong>. One solution is to comment out the call in syncApplTables for the table that you added. Another solution is to manually upgrade your table after the automated upgrade has completed.</p></td>
</tr>
</tbody>
</table>


## Running the Upgrade on Your Production Environment

It can take a while to prepare the test environment before your organization is ready to upgrade its production environment. The **UtcDateTime** portion of the overall upgrade preparation is relatively small.

Now you are ready to upgrade your production environment. The following table describes the two phases of upgrade that directly relate to the **UtcDateTime** upgrades.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Phase of upgrade</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Pre-synchronization</p></td>
<td><p>The initPreSyncJobs method is run, as the last step of pre-synchronization. Upgrade does no other processing while this step runs. The processing during this step takes table locks in the SQL database.</p>
<p>This adds your method to a list of methods that the system will run during the post-synchronization phase.</p>

> [!note]  
> <P>Any executions of the method ReleaseUpgradeDB41_Basic ::upgradeToDateTime after post-synchronization has begun are ignored.</P>

</td>
</tr>
<tr class="even">
<td><p>Post-synchronization</p></td>
<td><p>The runSQLCode_UpdateDateToUTCDateTime method is run, as the first step of post-synchronization. This updates the UTC values for your new <strong>UtcDateTime</strong> column.</p></td>
</tr>
</tbody>
</table>


## Consider Other Details

Additional details about the **UtcDateTime** upgrade are as follows:

  - During the upgrade checklist, you are prompted to enter the time zone that you want set for your AOS. Select the time zone that most of your Date and Time data matches.
    

    > [!WARNING]
    > <P>After the upgrade begins to use your selected time zone, there is no way to change to a different time zone. Be sure to select the correct time zone. You must make a backup copy of your database before beginning the upgrade.</P>



  - Null **Date** values will still be null after the upgrade to **UtcDateTime**. For these data types, their lowest possible value is treated as null.

  - When upgrade occurs for a **Date** field that is not paired with a **Time** field, the time part of the **UtcDateTime** value is set to 12:00 (at the midpoint of the day). Next, the time zone offset is applied, which changes the 12:00 time setting. The expectation is that the modified time is still within the same day.

  - If the upgrade stops in mid-process, the upgrade to **UtcDateTime** will complete when the upgrade is restarted. The system tracks status during each step of the upgrade.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

