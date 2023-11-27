---
title: 'How to: Create Delete Actions'
TOCTitle: 'How to: Create Delete Actions'
ms:assetid: c1d914d2-e2f8-463f-b9ac-4e2114520c5e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb315018(v=AX.60)
ms:contentKeyID: 35250099
ms.date: 05/18/2015
mtps_version: v=AX.60
description: Learn how to create and delete actions in Microsoft Dynamics AX 2012. Maintain database consistency and manage customer data effectively.
---

# How to: Create Delete Actions 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The DeleteAction element helps maintain database consistency when a record is deleted. Define delete actions to specify what should occur when data being deleted in the current table is related to data in another table.

For example, use a cascading delete action to specify that the system is to delete a customer's address when that customer is deleted from the CustTable table. Another example is to use a restricted delete action to prevent a customer from being deleted from the CustTable if one or more transactions exist for the customer in the CustTrans table.

Use the following best practices.

  - Have a delete action on every relation between two tables.

  - Use table delete actions instead of writing code to specify whether deletes are restricted or cascaded.
    

    > [!NOTE]
    > <P>Delete actions for groups usually don’t exist except when two groups are related. If there are delete actions on a table and DELETE_FROM is in use, performance will be slow.</P>



## Add a Delete Action

1.  In the Application Object Tree (AOT), expand the **Data Dictionary**.

2.  Expand **Tables**, and then locate the table that you want to add a delete action to.

3.  Click the table, right-click **DeleteActions**, and then click **New DeleteAction**.

4.  Right-click the new delete action, and then click **Properties**.

5.  Select a related table from the **Table** property list.

6.  Set the **DeleteAction** property. The following table describes the available values.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Delete Action</p></th>
<th><p>Description</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>None</p></td>
<td><p>Delete action disabled</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Cascade</p></td>
<td><p>Deletes related records.</p></td>
<td><p>Setting the DeleteAction property to Cascade extends the functionality of the table's delete method. As a result, super(), in delete, initiates a cascaded deletion, propagating the delete from table to table.</p>
<p>A cascaded delete is implicitly protected by tts. Database changes aren't committed until the entire transaction is complete.</p>
<p>Example</p>
<p>On the CustTable table, a cascading delete action has been defined for the CustBankAccount table. When a customer is deleted from the CustTable table, the delete method also ensures that the corresponding bank account information is automatically deleted.</p></td>
</tr>
<tr class="odd">
<td><p>Restricted</p></td>
<td><p>Restricts deletion in the current table if data is present in related tables.</p></td>
<td><p>Setting the DeleteAction property to Restricted extends the functionality of the table's validateDelete method.</p>
<p>As a result, super(), in validateDelete, checks whether records exist on related tables. If records do exist, validateDelete returns false. The forms system ensures that the deletion is not performed. In your own X++ code, check the return value of validateDelete. Don't delete the primary or related records if the method returns false.</p>
<p>Example</p>
<p>On the CustTable table, a restricted delete action has been defined for the CustTrans table. When a customer is deleted in the CustTable table, the validateDelete method ascertains whether transactions exist for the customer in the CustTrans table. If so, validateDelete returns false.</p></td>
</tr>
<tr class="even">
<td><p>Cascade+Restricted</p></td>
<td><p>Cascade the delete, even though records exist on related tables.</p></td>
<td><p>Setting the DeleteAction property to Cascade+Restricted extends the functionality of the table's validateDelete and delete methods.</p>
<p>As a result, super(), in validateDelete, ascertains whether records exist on related tables. Whether deleting records from forms or X++, if validateDelete returns false, the primary record isn't deleted and the cascading delete isn't performed. You should first delete the records in the related table before deleting the primary record.</p>
<p>If the primary record is being deleted as part of a cascading delete, the primary record and the records in the related table will be deleted.</p>
<p>Example</p>
<p>The Cascade+Restricted delete action is used in the standard application for LedgerJournalTrans on LedgerJournalTable.</p>
<p>This type of delete action is useful when you prefer a total clean-up—when you delete a customer, you also delete all the transactions associated with that customer.</p></td>
</tr>
</tbody>
</table>


## System tables

Cascading delete also works with Microsoft Dynamics AX system tables. For example, if you delete a user, the system automatically deletes the related information in the UserGroupList table.

## See also

[Maintaining Data Integrity](maintaining-data-integrity.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

