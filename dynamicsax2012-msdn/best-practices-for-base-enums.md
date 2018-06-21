---
title: Best Practices for Base Enums
TOCTitle: Base Enums
ms:assetid: 79f07f94-6f38-41f4-b766-a97f40907c38
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa656564(v=AX.60)
ms:contentKeyID: 35246070
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Base Enums [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes best practices for using [enums](enums.md). For rules about setting Enum properties, see [Best Practices for Enum Properties](best-practices-for-enum-properties.md).

Define and use enums when a field or a variable can have a limited, fixed number of predefined outcomes. If there might be an unlimited number of user-defined outcomes, use a to-be-related-to table instead.

If you want to make an enum a mandatory field on a table, make the first outcome with the value zero, as none, with the label **Not selected**.

Most enums can be regarded as specialized types, and should be used as they are. Some enums (like NoYes and TableGroupAll) can be regarded as more general types that can be specialized by using extended data types.

## Enums and Constants

When you are working with enums and constants:

  - Always let the constant be an enumerator.

  - Never use numeric constants instead of enums.

  - Never use other constants (such as other enum types) instead of enums (Booleans are compatible with all enums).

  - Do not make Boolean tests on enum fields, except where the 0/false value is clearly the one with the false outcome.

  - Never use relational operators on enums.

  - Never compare or assign to enums of different types.

  - Do not expect the enumerators to have a numeric value in the range of 0.\<num of enumerators - 1\>.

## Deleting Enumerators

If you want to delete an enumerator, determine whether it has been used in persistent storage in existing tables; old data must be taken into account.

To remove the enumerator while saving it in a database at the customer site as a table field:

1.  Rename the enumerator to DEL\_\<original name\>.

2.  Remove its label, and replace it with the text "\*\*\* Outdated \*\*\*".

3.  Add the Configuration Key SysDeletedObjects40 ('To be deleted after update') to the enumerator.

4.  Remove the usage of the enumerator from the code.

5.  Write a release update job that removes the data that is based on this enumerator from the installation, probably changing it to something else, so that the total result will be consistent.
    
    After the update, the user will not see the enumerator in the user interface.

6.  Remove the enumerator in the next version so that other enumerators do not change their numerical value: to set the UseEnumValue property to Yes, on the enum.

## See also

[Best Practices for Enum Properties](best-practices-for-enum-properties.md)

[Enums](enums.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

