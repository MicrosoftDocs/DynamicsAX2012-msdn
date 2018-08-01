---
title: static exist Method Design Pattern
TOCTitle: static exist Method
ms:assetid: 68a1fa44-45e3-46db-b167-654bee2bdf13
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa672421(v=AX.60)
ms:contentKeyID: 35244766
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# static exist Method Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Each table with a key should have a static exist method. Use it to check if a record that fulfills the specified key actually exists.

The exist method must:

  - Be static because it is used to check if any table object (record) exists among all the objects of the table class.

  - Return a boolean value.

  - Take an argument of the type of the key of the table or a list of arguments if the key consists of more than one field. If there is a list of arguments, they must be in the same order as the fields in the index that are used for the table's key.

  - Check for the most effective, existing index in the record against the supplied key, and then return true if it is in the table. If not, false.

  - Run on both the client and server. This is the default behavior. You can also make it explicit by putting "client server" in the declaration, but do not specify a single tier in the declaration (either the client or the server).

The method must be used whenever one record should be checked that is exists based on its key.

## Example

The following code is an example of the static exist method design pattern.

    static boolean exist(CustGroupId custGroupId)
    {
        return custGroupId 
            && (select firstOnly RecId from custGroup
                index hint GroupIdx
                where custGroup.custGroup == custGroupId).RecId != 0;
    }

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

