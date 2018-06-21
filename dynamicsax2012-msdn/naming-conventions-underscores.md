---
title: 'Naming Conventions: Underscores'
TOCTitle: Underscores
ms:assetid: 09132b07-320b-4077-976b-8b7b26684a99
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa575803(v=AX.60)
ms:contentKeyID: 35240325
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Naming Conventions: Underscores [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The underscore character ('\_') can be used in the following situations.

  - When naming formal parameters, it should be used as the first character. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

  - In the [DEL\_ prefix](naming-conventions-prefixes.md).

  - Subclasses can have the same name as their parent class, postfixed with a logical name that describes the subclass specialization. The name of the parent class might have to be shortened. In this case, use an underscore between the shortened parent class name, and the rest of the name. For example: InventUpd\_Financial, InventUpd\_Physical.

  - In an application object that is specialized for a specific country/region, the name is postfixed with underscore and the country/region code. For example: TaxReport\_BE, LedgerJournalizeTrans\_ES.

Do not use an underscore in the following situations:

  - Beginning of an application object name.

  - First character of a variable name in class declarations or methods. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

  - End of a variable name in class declarations or methods.

## See also

[Naming Conventions](naming-conventions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

