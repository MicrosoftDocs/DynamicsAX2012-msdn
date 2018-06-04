---
title: Naming Conventions
TOCTitle: Naming Conventions
ms:assetid: 6079f110-34e8-4ac9-984d-38449ff988fe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa632638(v=AX.60)
ms:contentKeyID: 35244484
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Naming Conventions 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Naming conventions contribute to consistency and to making the application easier to understand.

The following topics provide naming rules for application objects:

[Best Practices for Labels](best-practices-for-labels.md)

[Naming Conventions: Name Structure](naming-conventions-name-structure.md)

[Naming Conventions: Use of Uppercase and Lowercase](naming-conventions-use-of-uppercase-and-lowercase.md)

[Naming Conventions: Underscores](naming-conventions-underscores.md)

[Naming Conventions: Abbreviations](naming-conventions-abbreviations.md)

[Naming Conventions: Prefixes](naming-conventions-prefixes.md)

[Naming Convention: Automatically Generated Names](naming-convention-automatically-generated-names.md)

[Naming Conventions: Variables](naming-conventions-variables.md)

[Naming Conventions: License Codes](naming-conventions-license-codes.md)

[Naming Conventions: Delegates and Event Handlers](naming-conventions-delegates-and-event-handlers.md)

[Naming Conventions: Methods](naming-conventions-methods.md)

## General Rules

  - All names must be in U.S. English.

  - The default rule is to use logical and descriptive names if no other specialized rules apply.

  - Identifier names have a limit of 40 characters.

  - Names in the Application Object Tree (AOT) and in X++ code must correspond to the names in the U.S. English user interface.

  - Names must be spelled correctly.

  - Names must be used consistently.

  - Each path in the AOT must be unique; nodes must not have identical names.

  - All texts that appear in the user interface must be defined by using a label. (This rule applies only if you want your solution certified as an international solution.)

  - Do not begin a name with "aaa", or "CopyOf". Do not begin a name with "DEL\_" unless it is a table, extended data type or enum, and it is needed for data upgrade purposes. Names that use these prefixes cause a best practices error when you check the objects into the version control system.![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

  - We do not support an EDT with the same name as a Table, EDT, Base Enum, or Class.

Rules are available about the following:

  - [Use of labels](best-practices-for-labels.md)

  - [Name structure](naming-conventions-name-structure.md)

  - [Upper and lower case](naming-conventions-use-of-uppercase-and-lowercase.md)

  - [Underscores](naming-conventions-underscores.md)

  - [Abbreviations](naming-conventions-abbreviations.md)

  - [Prefixes](naming-conventions-prefixes.md)

  - [Naming Convention: Automatically Generated Names](naming-convention-automatically-generated-names.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

