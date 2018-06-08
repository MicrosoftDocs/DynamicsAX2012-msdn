---
title: Best Practices for Table Relations
TOCTitle: Table Relations
ms:assetid: e49138f5-5e29-42ea-9cb4-c0281a048381
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa880475(v=AX.60)
ms:contentKeyID: 35253191
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Table Relations 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You will get a best practices error if you create a relation on a table but do not add any fields to it. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

## Name

The name of a relation should be postfixed with the name of the table it relates to. For example, **CustBankAccounts** could be a relation on the **BankAccounts** table.

If there is only one relation for a table, you can just use the table name for the relation instead.

## Relations in the Data Model

A relation should be defined on the table that is holding the foreign key to the relating table. The **Validate** property must be set to **Yes**.

The system guarantees that data entered in the database fulfills the specified relations.

## The Self Relation

If a table has a key, the key must be defined by using relations. Such a relation is called the 'self relation'. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

The self relation should not be set up in situations where the fields in the key are all foreign keys (such as relations to other tables) - or more specifically, where the last field in the self relation is a foreign key.

## Navigational Relations

Navigational relations are definitions of relations that exist among data in tables where there are no integrity constraints.

Defining a navigational relation benefits the system’s Auto Join system when one form is opened from within another form.

Define navigational relations to make it easy to navigate in the application by using related information.

A navigational relation has the Validate property set to **No**.

The Auto Join system uses relations that are defined at both the involved tables, which means that you only have to define a navigational relation on the one table to the other to make the Auto Join system work both ways.

### ![Aa880475.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa880475.collapse_all(en-us,AX.60).gif")Example

Let us imagine that there is a relation with **CustTrans** table that is defined on the **LedgerTrans** table. The relation can be a purely navigational relation.

![TransDate and Voucher columns for relations](images/Aa880475.CRDBREL2(en-us,AX.60).gif "TransDate and Voucher columns for relations")

Both tables hold information about **TransDate** and **Voucher** columns, but neither of these columns are keys that are used for validating the other.

You can open a **CustTrans** table-based form from a **LedgerTrans** table-based form. The system will only show the **CustTrans** records that have the same **TransDate** and voucher as the **LedgerTrans** record has in the form from where you started.

## Configuration Keys

The configuration key that is specified for the field in a relation must be the same key, or in the same tree of keys, as the key used for the related field. If the external field in a relationship can be removed, due to configuration key settings, and the field on which the relation is set is not also removed, you will get a best practices warning. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

## See also

[How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

