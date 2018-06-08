---
title: Methods on a Form Data Source
TOCTitle: Methods on a Form Data Source
ms:assetid: ff683de9-bf37-4c00-87bc-13ab2fde9cc3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa893931(v=AX.60)
ms:contentKeyID: 35254215
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Methods on a Form Data Source 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Each form data source has a set of standard methods. You override these methods when you want to change the behavior for validation, caching, and so on. These methods are a subset of the methods in the FormDataSource system class.

You use the AOT to access the standard methods:

1.  Expand the node for the form data source on the form.

2.  Right-click the **Methods** node.

3.  Select **Override Method**.


> [!NOTE]
> <P>Code written on forms cannot be re-used or inherited. If possible, write your code on the underlying table or in a class.</P>



The following table lists the methods that are available for form data sources and explains when they are executed. For more information about each method, click the method name.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method name</p></th>
<th><p>Executed when</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857736(v=ax.60)">active</a></p></td>
<td><p>The user selects a new record.</p></td>
<td><p>Retrieves data from joined data sources when a user moves to a new record.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857785(v=ax.60)">create</a></p></td>
<td><p>The user creates a new record in the data source.</p></td>
<td><p>Creates a new record in the data source.</p>
<p>If you use this method to specify field values, the new values are saved to the database when you leave the form.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857791(v=ax.60)">cursorNotify</a></p></td>
<td><p>Not run by the system.</p></td>
<td><p>Used to notify application code of table events.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857795(v=ax.60)">defaultMark</a></p></td>
<td><p>The user clicks the mark area (uppermost left corner) in a grid control.</p></td>
<td><p>Sets the default mark value for records in a form.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857803(v=ax.60)">deleted</a></p></td>
<td><p>The form data source record has been deleted.</p></td>
<td><p>Runs instead of the delete post-super for a form where the <strong>ChangeGroupMode</strong> property of the form <strong>Data Sources</strong> node is set to <strong>ImplicitInnerOuter</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857801(v=ax.60)">delete</a></p></td>
<td><p>The user deletes a record in the data source.</p></td>
<td><p>Deletes the current record from the data source.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857805(v=ax.60)">deleteMarked</a></p></td>
<td><p>The user deletes one or more marked (selected) records in the data source.</p></td>
<td><p>Deletes all marked (selected) records from a data source.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857806(v=ax.60)">deleting</a></p></td>
<td><p>The form data source record is about to be deleted.</p></td>
<td><p>Runs instead of the delete pre-super for a form where the <strong>ChangeGroupMode</strong> property of the form <strong>Data Sources</strong> node is set to <strong>ImplicitInnerOuter</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857813(v=ax.60)">displayOption</a></p></td>
<td><p>Activated before a record is displayed.</p></td>
<td><p>Sets the text color and the background color for a record in the data source.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857815(v=ax.60)">executeQuery</a></p></td>
<td><p>The form is opened for data display.</p></td>
<td><p>Executes the data source query and displays the retrieved records.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857821(v=ax.60)">filter</a></p></td>
<td><p>The user starts one of the Filter commands on the form shortcut menu.</p></td>
<td><p>Filters records in the data source.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857823(v=ax.60)">findRecord</a></p></td>
<td><p>Activated by the findValue method.</p></td>
<td><p>Finds the specified record in the data source and makes it the current one.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857827(v=ax.60)">findValue</a></p></td>
<td><p>The user clicks the <strong>Filter by Field</strong> command in the shortcut menu on a form control.</p></td>
<td><p>Finds the specified value in the data source and makes the record that has the specified value the current one by using the FormDataSource.findRecord method.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857833(v=ax.60)">first</a></p></td>
<td><p>Focus moves to the first record in the data source.</p></td>
<td><p>Moves focus to the first record in the data source.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857836(v=ax.60)">forceWrite</a></p></td>
<td><p>Executed when it is called.</p></td>
<td><p>Enables you to force a write operation on a record.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg892256(v=ax.60)">init</a></p></td>
<td><p>The form is opened.</p></td>
<td><p>Creates a data source query based on the data source properties.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg892258(v=ax.60)">initValue</a></p></td>
<td><p>A new record is created. The purpose is to fill in initial values in the record.</p></td>
<td><p>Initializes field values in a new record.</p>
<p>If you use this method to specify field values, the new values are not automatically saved to the database when you leave the form. To specify values that you want to save when you leave the form, use the Create method.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg892275(v=ax.60)">last</a></p></td>
<td><p>Focus moves to the last record in the data source.</p></td>
<td><p>Moves focus to the last record in the data source.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg892276(v=ax.60)">leave</a></p></td>
<td><p>Focus moves to a new record or to a new data source.</p></td>
<td><p>Provides notification when focus is moved to the next record or moved to another data source.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg892278(v=ax.60)">leaveRecord</a></p></td>
<td><p>Focus moves to a new record.</p></td>
<td><p>Provides notification when focus moves to another record or another item on the form.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg892279(v=ax.60)">linkActive</a></p></td>
<td><p>The user selects a new record in a form that has a data source linked to another data source.</p></td>
<td><p>Calls the FormDataSource.exeuteQuery method on data sources that are linked to the current data source.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg892283(v=ax.60)">mark</a></p></td>
<td><p>A record in the data source is marked.</p></td>
<td><p>Enables you to mark a record in the data source.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg892284(v=ax.60)">markAllLoadedRecords</a></p></td>
<td><p>Not started by the system.</p></td>
<td><p>Enables you to mark or clear all the loaded records.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg892285(v=ax.60)">markChanged</a></p></td>
<td><p>One or more records in the data source are marked or unmarked.</p></td>
<td><p>Enables you to perform an action when there is a change to the number of marked records in the data source.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873708(v=ax.60)">next</a></p></td>
<td><p>Focus moves to the next record in the data source.</p></td>
<td><p>Moves focus to the next record in the data source.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873709(v=ax.60)">nextPage</a></p></td>
<td><p>The user requests the next page of data from the data source.</p></td>
<td><p>Moves a specified number of records forward in the data source. Pulls the next page of data.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873717(v=ax.60)">prev</a></p></td>
<td><p>Focus moves to the previous record in the data source.</p></td>
<td><p>Moves focus to the previous record in the data source.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873718(v=ax.60)">prevPage</a></p></td>
<td><p>The user requests the previous page of data from the data source.</p></td>
<td><p>Moves focus back by a specified number of records in the data source. Pulls the previous page of data.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873719(v=ax.60)">print</a></p></td>
<td><p>The user starts the <strong>Print</strong> command in the <strong>File</strong> menu.</p></td>
<td><p>Prints the current record.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873720(v=ax.60)">prompt</a></p></td>
<td><p>The user starts the <strong>Advanced Filter/Sort</strong> command (either from the <strong>Edit</strong> &gt; <strong>Filter</strong> menu or by pressing CTRL+F3).</p></td>
<td><p>Activates SysQueryForm, which is the standard form used to limit a query range.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873724(v=ax.60)">refresh</a></p></td>
<td><p>Not started by the system.</p></td>
<td><p>Updates the form by refreshing the view of all records in the data source.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873725(v=ax.60)">refreshEx</a></p></td>
<td><p>A form is opened where records have been selected.</p></td>
<td><p>Refreshes the view of the specified records.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873727(v=ax.60)">removeFilter</a></p></td>
<td><p>The user clicks the <strong>Remove Filter/Sort</strong> command in the shortcut menu on a form control.</p></td>
<td><p>Resets the query for the data source.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873728(v=ax.60)">reread</a></p></td>
<td><p>Not started by the system.</p></td>
<td><p>Rereads the current record from the database.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873729(v=ax.60)">rereadReferenceDataSources</a></p></td>
<td><p>The value of a foreign key field is programmatically changed.</p></td>
<td><p>Used to update the joined referenced data source for the current record when the foreign key field is programmatically changed.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873730(v=ax.60)">research</a></p></td>
<td><p>Not started by the system.</p></td>
<td><p>Refreshes the database search defined by the query, specified by the FormDataSource.init method.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873731(v=ax.60)">selectionChanged</a></p></td>
<td><p>The user selects or unselects one or more records in the data source.</p></td>
<td><p>Enables you to change the property values of control when the selected record changes.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873740(v=ax.60)">validateDelete</a></p></td>
<td><p>The user has chosen to delete a record.</p></td>
<td><p>Requests the user to confirm the deletion of a record from the data source.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873741(v=ax.60)">validateWrite</a></p></td>
<td><p>A new or updated record is to be written.</p></td>
<td><p>Determines whether data is valid and ready to be written.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873744(v=ax.60)">write</a></p></td>
<td><p>The user inserts a new record or updates an existing one.</p></td>
<td><p>Calls the FormDataSource.validateWrite method and manages the database write operation.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873745(v=ax.60)">writing</a></p></td>
<td><p>The form data source record is about to be saved to the database.</p></td>
<td><p>Runs instead of the write pre-super for a form where the <strong>ChangeGroupMode</strong> property of the form <strong>Data Sources</strong> node is set to <strong>ImplicitInnerOuter</strong>.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873746(v=ax.60)">written</a></p></td>
<td><p>The form data source record has been saved to the database.</p></td>
<td><p>Runs instead of the write post-super for a form where the <strong>ChangeGroupMode</strong> property of the form <strong>Data Sources</strong> node is set to <strong>ImplicitInnerOuter</strong>.</p></td>
</tr>
</tbody>
</table>


## See also

[FormDataSource Class](https://msdn.microsoft.com/en-us/library/gg892246\(v=ax.60\))

[Methods on a Form](methods-on-a-form.md)

[Methods on Form Controls](methods-on-form-controls.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

