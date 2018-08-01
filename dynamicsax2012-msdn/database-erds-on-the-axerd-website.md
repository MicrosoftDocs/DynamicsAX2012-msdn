---
title: Database ERDs on the AxErd Website
TOCTitle: Database ERDs on the AxErd Website
ms:assetid: 2d6b9c04-a195-4d29-8ac0-e6e71ec2a800
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn246477(v=AX.60)
ms:contentKeyID: 54671696
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Database ERDs on the AxErd Website [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

We have created about 30 database entity relationship diagrams (ERDs) for tables of Microsoft Dynamics AX 2012 R2. As a developer, you can use these ERDs when you customize a given application module, such as the **Accounts payable** module or the **General ledger** module.

The ERDs are part of our AxErd website. The website can be reached at the following Http URL:

[AxErd website: http://go.microsoft.com/fwlink/p/?linkid=296623](http://go.microsoft.com/fwlink/p/?linkid=296623)

## Design Principles for these ERDs

The Microsoft Dynamics AX database contains several thousand tables. It is impossible to construct one ERD that contains every table. And it is impossible to construct enough smaller specialized ERDs that foresee every precise need of every developer. So the ERDs we provide are designed to capture the core tables of each module, and to include some major tables from other related modules.

We made minor adjustments so that each ERD can fit onto one side of a standard sheet of paper when printed.

## Support Files for Extension of ERDs

The AxErd website also contains hundreds of linked support pages that are designed to assist you when you need to extend one of the ERDs that AxErd provides. In Microsoft Dynamics AX 2012, you can easily look up all the *parent* tables of a given table by opening the following node in the AOT:

AOT \> Data Dictionary \> Tables \> *MyTable* \> Relations \> *MyRelation*

However, it is much harder for you to look up all the *child* tables of that same given table. The cross-reference feature does technically provide this information, but only after many interactions with the user interface for each child table. In contrast, the AxErd website enables you to retrieve a list of the child or parent tables with one click. AxErd has all the foreign key information sorted and gathered together in one place.

For instructions on how you can semi-automate the task of extending or creating an ER diagram with Microsoft Dynamics AX 2012, click the Help link on the AxErd Home page.

## Tables and ERDs are Displayed by Module

For each table, the AxErd website conveniently associates tables to modules in both of the following ways:

  - Provides a long alphabetized list of all tables, with the correct module name next to each table name.

  - Provides a separate page for each module, where each such page displays an alphabetized list of all tables in the module.

## See also

[Table Keys: Surrogate, Alternate, Replacement, Primary, and Foreign](table-keys-surrogate-alternate-replacement-primary-and-foreign.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

