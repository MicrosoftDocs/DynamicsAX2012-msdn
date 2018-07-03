---
title: Variable Names
TOCTitle: Variable Names
ms:assetid: 58d7a6d0-47ec-4047-951d-4e651c47143b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa606689(v=AX.60)
ms:contentKeyID: 35244338
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Variable Names 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The name, or identifier, for a variable points to a memory location where information of a specific data type is stored. The syntax rules for variable names are as follows:

  - Names must be limited to ASCII letters, digits, and the underscore character (\_), all with hex values of 0x7F or less.

  - Letters can be either uppercase or lowercase.

  - Names are not case sensitive. For example, aa and AA are treated as the same name.

  - The first character must be either a letter or the underscore character.

  - Variable names can be thousands of characters long.

The following four variables that are declared in the myMethod method have valid names in X++:

```X++
private void myMethod(int _, str _myParameter2)
    {
        str I;
        str XppAllowsVeryLongVariableNamesWhichTireOurFingers;
        …
    }
```

According to convention, variable names should begin with a lowercase letter. Variables of specialized types should be named like these examples:

CustInvoiceJour custInvoiceJour;

CustTable custTable;

For more information, see [Naming Conventions: Variables](naming-conventions-variables.md).

## See also

[Naming Conventions](naming-conventions.md)

[Data Types in X++](data-types-in-x.md)

[Declaration of Variables](declaration-of-variables.md)

[Variable Scopes](variable-scopes.md)

[Variables](variables.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

