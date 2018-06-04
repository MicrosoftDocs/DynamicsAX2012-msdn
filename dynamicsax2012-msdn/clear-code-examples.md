---
title: Clear Code Examples
TOCTitle: Clear Code Examples
ms:assetid: a5df0244-6a26-4e89-a398-81ae337f9749
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa851125(v=AX.60)
ms:contentKeyID: 35248412
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Clear Code Examples 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The code in the two examples below can be rewritten to be much clearer.

## Example 1

From:

if (args.parmEnumType() \!= enumnum(BMBuildIdEnum))

{

    if (args.record().tableId == tableNum(BMmoduleTable))

    {

        moduleTable = args.record();

        buildId = moduleTable.buildId;

    }

    else

    {

        return null;

    }

}

else

{

    buildId = args.parmEnum();

}

...

To:

if (args.parmEnumType() == enumNum(BMBuildIdEnum))

{

    buildId = args.parmEnum();

}

else

{

    if (args.record().tableId == tableNum(BMmoduleTable))

    {

        moduleTable = args.record();

        buildId = moduleTable.buildId;

    }

    else

    {

        return null;

    }

}

...

The rewrite puts the most important case first, and removes the negative logic used in the first if statement in the first version of the code.

## Example 2

From:

ledgerJournalTrans = this.ledgerJournalTransInitFromCreate(\_tmpProjAdjustmentCreate);

    if (ledgerJournalTrans.validateWrite())

    {

        ledgerJournalTrans.insert();

        ProjPostLedger = ProjPost::construct(ledgerJournalTrans,ledgerVoucherTrans);

        if (projPostLedger.checkTrans())

        {

            projPostLedger.PostTrans();

        }

        else

        {

            throw error("@SYS21628");

        }

    }

    else

    {

        throw error("@SYS21628");

    }

    ledgerjournalTrans.delete(false);

...

To:

ledgerJournalTrans = this.ledgerJournalTransInitFromCreate(\_tmpProjAdjustmentCreate);

if (\!ledgerJournalTrans.validateWrite())

{

    throw error("@SYS21628");

}

ledgerJournalTrans.insert();

ProjPostLedger = ProjPost::construct(ledgerJournalTrans,ledgerVoucherTrans);

     

if (\!projPostLedger.checkTrans())

{

    throw error("@SYS21628");

}

    projPostLedger.PostTrans();

    ledgerjournalTrans.delete(false);

...

## See also

[Dead Code Examples](dead-code-examples.md)

[X++ Coding Standards](x-coding-standards.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

