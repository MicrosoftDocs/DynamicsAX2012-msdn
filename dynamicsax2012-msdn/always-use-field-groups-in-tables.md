---
title: Always Use Field Groups in Tables
TOCTitle: Always Use Field Groups in Tables
ms:assetid: 739d7bc6-5f27-4018-b82d-b604cdffd1f9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa641676(v=AX.60)
ms:contentKeyID: 35245911
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Always Use Field Groups in Tables 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When designing tables, it is very important to use field groups. You should also add fields to a field group if you are adding fields to existing tables. Add them to an existing field group, if possible.

When you use field groups, IntelliMorph can automatically update the layout of all related forms and reports whenever a modification is made to the field groups.

If you create new forms or reports based on the field groups defined in the standard tables, you will not have to manually update the custom object when the standard tables are modified by an upgrade.

The sequence of the fields in the field groups on tables can be used to determine the sequence of the fields in forms. To do this, use the AutoDataGroup property on the Groups controls in the form design.

This means that the order in which the fields appear in the field group is significant.

## See also

[Best Practices for Field Groups](best-practices-for-field-groups.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

