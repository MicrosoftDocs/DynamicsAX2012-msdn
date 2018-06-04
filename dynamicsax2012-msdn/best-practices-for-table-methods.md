---
title: Best Practices for Table Methods
TOCTitle: Table Methods
ms:assetid: 2f59ad11-c256-42d5-9576-75a664a5400a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa602944(v=AX.60)
ms:contentKeyID: 35241965
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Table Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Following are the types of [table methods](https://msdn.microsoft.com/en-us/library/aa625830\(v=ax.60\)):

  - Application-defined methods – created by a developer specifically for a particular table.

  - System-defined methods – automatically available on every table. These methods are from the xRecord system class.

## Application-Defined Methods

Use the properties available on tables and table fields rather than creating code for the same purpose. If you do need to create a method on a table, it must be directly related to that table.

By default, these methods run on both the client and the server. You can state this explicitly in the method declaration (client server), but don't specify a single tier (client or server). It is a best practice to create these methods on tables. A best practices error does not occur if the method is not called.

## System-Defined Methods

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>System-defined method</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>clear</p></td>
<td><p>Called by the kernel—you do not need to call this method from the application.</p></td>
</tr>
<tr class="even">
<td><p>delete</p></td>
<td><p>Secure any related transactions.</p>
<p>If you have DeleteActions on one table set to Cascade delete on another table, avoid writing code on the delete method on the second table (for performance reasons).</p>
<p><span id="yb12dfwhilsel"></span>If you don't add code here, the database management system can quickly do cascading deletes by using direct SQL deletes (DELETE_FROM).</p>
<p>If you do add code here, the system creates a while select statement, and then executes the delete method on all child tables. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p>
<p>If you are deleting from the buffer, use skipDelete.</p></td>
</tr>
<tr class="odd">
<td><p>doInsert, doUpdate, doDelete</p></td>
<td><p>Avoid using these methods.</p>
<p>These methods should only be used under strict control because they bypass the following:</p>
<ul>
<li><p>Any validations that have been set up.</p></li>
<li><p>Any code that was written in the insert, update, and delete methods.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>helpField</p></td>
<td><p>When manipulating an array, use the standard methods on the Global application class as follows:</p>
<ul>
<li><p>fieldExt2Id</p></li>
<li><p>fieldId2Ext</p></li>
<li><p>fieldExt2Id</p></li>
</ul>
<p>For more information about the field ID of an array, see <a href="extended-field-ids.md">Extended Field IDs</a>.</p></td>
</tr>
<tr class="odd">
<td><p>initValue</p></td>
<td><p>The call to super() assigns the default values that you have set by using the record template.</p>
<p>Use the method to assign initial/default values to a new record.</p></td>
</tr>
<tr class="even">
<td><p>insert</p></td>
<td><p>Secure any related transactions with tts.</p>
<p>If insert is overridden, <a href="optimizing-record-inserts.md">array inserts</a> reverts to record-by-record insert.</p></td>
</tr>
<tr class="odd">
<td><p>isFormDataSource</p></td>
<td><p>Called by the kernel—you do not need to call this method from the application.</p></td>
</tr>
<tr class="even">
<td><p>merge</p></td>
<td><p>Called by the kernel—you do not need to call this method from the application.</p></td>
</tr>
<tr class="odd">
<td><p>modifiedField</p></td>
<td><p>Called by the kernel—you do not need to call this method from the application.</p></td>
</tr>
<tr class="even">
<td><p>postLoad</p></td>
<td><p>Avoid placing any code here. Instead, use display methods.</p>
<p>The postLoad method is called every time a record is fetched from the database. Avoid creating any code on this method that will have an impact on performance. For example, avoid adding code that involves calls between the client and server, or any code that results in a database operation.</p></td>
</tr>
<tr class="odd">
<td><p>reRead</p></td>
<td><p>Called by the kernel—you don't need to call this method from the application.</p></td>
</tr>
<tr class="even">
<td><p>toolTipField</p></td>
<td><p>When manipulating an array, use the standard methods on the Global application class as follows:</p>
<ul>
<li><p>fieldExt2Id</p></li>
<li><p>fieldId2Ext</p></li>
<li><p>fieldExt2Id</p></li>
</ul>
<p>For more information about the field ID of an array, see <a href="extended-field-ids.md">Extended Field IDs</a>.</p></td>
</tr>
<tr class="odd">
<td><p>toolTipRecord</p></td>
<td><p>Enables you to append additional information to the standard tooltip text. For example, use the toolTipRecord method to include a message to display a &quot;customer out of credit&quot; message.</p></td>
</tr>
<tr class="even">
<td><p>update</p></td>
<td><p>Secure any related transactions with tts.</p>
<p>If update is overridden, <a href="optimizing-record-inserts.md">array inserts</a> cannot be used, and automatically reverts to record-by-record insert.</p></td>
</tr>
<tr class="odd">
<td><p>validateDelete</p></td>
<td><p>Do not delete the super() call if you override this method.</p>
<p>The method should return a Boolean—don't throw an exception here.</p></td>
</tr>
<tr class="even">
<td><p>validateField</p></td>
<td><p>You should respect the task performed by the super() call.</p>
<p>The method should return a Boolean—don't throw an exception here.</p>
<p>When manipulating an array, use the standard methods on the Global application class as follows:</p>
<ul>
<li><p>fieldExt2Id</p></li>
<li><p>fieldId2Ext</p></li>
<li><p>fieldExt2Id</p></li>
</ul>
<p>For more information about the field ID of an array, see <a href="extended-field-ids.md">Extended Field IDs</a>.</p></td>
</tr>
<tr class="odd">
<td><p>validateWrite</p></td>
<td><p>Respect the task performed by the super() call.</p>
<p>The method should return a Boolean. Don't throw an exception here.</p></td>
</tr>
<tr class="even">
<td><p>xml</p></td>
<td><p>Called by the kernel—you don't need to call this method from the application.</p></td>
</tr>
</tbody>
</table>


## See also

[Table Methods](https://msdn.microsoft.com/en-us/library/aa625830\(v=ax.60\))

[Best Practices for Methods](best-practices-for-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

