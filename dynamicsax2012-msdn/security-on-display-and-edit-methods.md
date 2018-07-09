---
title: Security on Display and Edit Methods
TOCTitle: Security on Display and Edit Methods
ms:assetid: 88c7afba-29db-43d8-82ed-27e176ca242f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa658897(v=AX.60)
ms:contentKeyID: 35246255
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security on Display and Edit Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Security for display and edit methods can be enforced on forms. Security cannot be enforced on reports when the method is declared on the table in the Application Object Tree (AOT). This means that a user who has access to the table, also has access to all of its display methods from reports.

If a display method returns data from another table (or another row in the same table) it can result in unintended information disclosure. If a display method returns data from the same row, but from another column, this also poses a threat.

## Example: (Table: InventItemGroup)

   ```X++
   display ForecastHasSales hasSalesBudget()
    {
        return (select forecastSales
                    where forecastSales.itemGroupId == this.itemGroupId).recId != 0;
    }
   ```

## Example: (Table: CustInterestJour)

   ```X++
   server display InterestAmountCur sumInterestAmount()
    {
        InterestAmountCur   interestAmountCur;
        CustInterestTrans   custInterestTrans;
    
        while select sum(InterestAmount) from custInterestTrans
            group by CurrencyCode
            where custInterestTrans.InterestNote == this.InterestNote &&
                  custInterestTrans.InterestCalculate
        {
            interestAmountCur += custInterestTrans.custInterestAmount(this);
        }
        return interestAmountCur;
    }
   ```

## Mitigations

  - Evaluate each display method that returns data from another row, either in the same table or in a different table. If you decide that it poses a threat, perform explicit authorization checks and throw an exception if access is unauthorized.

  - Manually activate [Record Level Security](record-level-security.md) in the display or edit method.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

