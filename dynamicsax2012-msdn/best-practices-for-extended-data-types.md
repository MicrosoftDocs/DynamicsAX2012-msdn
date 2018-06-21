---
title: Best Practices for Extended Data Types
TOCTitle: Extended Data Types
ms:assetid: 34c58dad-942e-4c83-b374-4e0ec92d4ac2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa603996(v=AX.60)
ms:contentKeyID: 35242002
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Extended Data Types [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The basic rules for using extended data types are as follows:

  - Use an extended data type wherever possible.

  - Create an extended data type for each atomic entity in the situation that your application is modeling.

  - The hierarchies you create among the extended data types should be able to pass the "is-a" test (except for the super-grouping types and the mixed field types described later in this topic). That is, an extended data type should be a "member" of the parent extended data type concept. For example, SuppItemId "is-a" ItemId, but SuppItemId is not a ClassName.

  - Only create subtypes when they are needed. If you want to add a field to a table or to a dialog, do not choose a type that is too general, and just add texts for label and help locally. Instead, create the type from the beginning and reuse it everywhere else.

  - Do not directly use the system data types recID or tableID. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon") Use the extended data type RefRecId or an extended data type derived from RefRecId.

For more information, see [Best Practices for Extended Data Type Properties](best-practices-for-extended-data-type-properties.md)

## Benefits of EDTs

The benefits of EDTs are as follows:

  - Code is easier to read because variables have a meaningful data type. For example, Name instead of string.

  - The properties you set for an EDT are used by all instances of that type, which reduces work and promotes consistency. For example, account numbers (AccountNum data type) have the same properties throughout the system.

  - You can create hierarchies of EDTs, inheriting the properties that are appropriate from the parent and changing the other properties. For example, the ItemCode data type is used as the basis for the MarkupItemCode and PriceDiscItemCode data types.

## Super-Grouping Types used as Templates for other Types

Extended data types like SysGroup and Description are used for defining a uniform user interface in the standard application. All group table identifiers and names are initially set up with the same width. Specialized extensions should be created for each usage.

These super-grouping types can be used for setting the length and so on for all the fields that use their subtypes, but the intention is that they must not be counted on as compatible.

The specialized subtypes can be disintegrated from their super-grouping types at the site of the implementation. This allows for customized settings of each actual type.

The super-grouping types should not be used from X++ code and in fields because their subtypes can be disintegrated. They must only be used as super types.

## Configuration Keys and Relationships

The configuration key specified for the extended data type in a relation must be the same key, or in the same tree of keys, as the key used for the related field. If the external field in a relationship can be removed, due to configuration key settings, and the extended data type on which the relation is set is not also removed, a best practices warning occurs. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

## See also

[Best Practices for Extended Data Type Properties](best-practices-for-extended-data-type-properties.md)

[SysGroup Extended Data Type](https://msdn.microsoft.com/en-us/library/gg902216\(v=ax.60\))

[Extended Data Types (EDTs)](extended-data-types-edts.md)

[How to: Create an Extended Data Type](how-to-create-an-extended-data-type.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

