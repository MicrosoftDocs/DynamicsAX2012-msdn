---
title: Storno Design Pattern
TOCTitle: Storno
ms:assetid: 40d4ff11-a6fa-4728-8eca-60d8d6283dd4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa594252(v=AX.60)
ms:contentKeyID: 35242947
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Storno Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Storno is a German word that is used to describe an account that has plus credit and minus debit.

Amount fields on Transaction tables that could be corrected should use this design pattern.


> [!NOTE]
> <P>This design pattern is used for the GeneralJournalAccountEntry table.</P>



## Extended Data Type Account Field Settings

You must show the transaction amount where corrections can appear with the following:

  - The DisplaceNegative property set to approximately 10

  - The SignDisplay property set to None

The corrected amounts (Storno) cannot otherwise be shown. The data types AmountMSTDebCred and AmountCurDebCred can be used for this purpose.

## IsCorrection Field Settings

Apart from the amount fields as previously defined, a Boolean field named Correct should be defined on the same table as the amount fields.

Set the Correct field to true if the record represents a corrected posting.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Setting</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Type</p></td>
<td><p>#Enum</p></td>
</tr>
<tr class="even">
<td><p>Name</p></td>
<td><p>#IsCorrection</p></td>
</tr>
<tr class="odd">
<td><p>Label</p></td>
<td><p>#@SYS13069 -&gt; Correction</p></td>
</tr>
<tr class="even">
<td><p>HelpText</p></td>
<td><p>#@SYS3643 -&gt; Is the current transaction a reversing entry?</p></td>
</tr>
<tr class="odd">
<td><p>SaveContents</p></td>
<td><p>#No</p></td>
</tr>
<tr class="even">
<td><p>Mandatory</p></td>
<td><p>#No</p></td>
</tr>
<tr class="odd">
<td><p>AllowEditOnCreate</p></td>
<td><p>#Yes</p></td>
</tr>
<tr class="even">
<td><p>AllowEdit</p></td>
<td><p>#Yes</p></td>
</tr>
<tr class="odd">
<td><p>Visible</p></td>
<td><p>#Yes</p></td>
</tr>
<tr class="even">
<td><p>Table</p></td>
<td><p>#GeneralJournalAccountEntry</p></td>
</tr>
<tr class="odd">
<td><p>EnumType</p></td>
<td><p>#NoYes</p></td>
</tr>
</tbody>
</table>


## Use Correct Flags

Set the correct flag of the involved amount fields by using the system function corrflagset if the record represents a corrected posting as shown in the following example.

    void postLoad() 
    {
        if (this.IsCorrection)
        {
            this.FuntionalCurrencyAmount = corrflagset(this.FunctionalCurrencyAmount,1);
            this.TransactionCurrencyAmount = corrflagset(this.TransactionCurrencyAmount,1);
        }
        super(); 
    }

The correction flags of a real are manipulated with the corrflagget and corrflagset functions.

## Check if the Amount Field has been Corrected

When you use the Amount field, check if it has been corrected as shown in the following example.

    if (GeneralJournalAccountEntry.IsCredit)
    {
        amountCredit = GeneralJournalAccountEntry.FunctionalCurrencyAmount;
        totalAmountCredit += amountCredit;
    }
    else
    {
        amountDebit += GeneralJournalAccountEntry.FunctionalCurrencyAmount;
        totalAmountDebit += amountDebit;
    }

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

[corrFlagGet Function](https://msdn.microsoft.com/en-us/library/aa887212\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

