---
title: Query Reuse by Composite Queries
TOCTitle: Query Reuse by Composite Queries
ms:assetid: 44b00a82-a148-4943-86f4-bdaa400e4de0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc588007(v=AX.60)
ms:contentKeyID: 35242961
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Query Reuse by Composite Queries [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A composite query uses another query as its data source. A composite query is similar to class inheritance in X++ or C\#.

A composite query is a good design choice when one of the following is true:

  - An existing query lacks only a range that you want to add.

  - An existing query lacks only a method override that you want to add.

## Create a Composite Query

The following steps describe how to create a composite query.

1.  In the AOT, right-click the **Queries** node, and then click **New Query**.

2.  Expand the node for the new query.

3.  Drop the existing query onto the **Composite Query** node of the new query.

The original query is called the base query. When the base query is changed, the changes are instantly in effect for the composite query.

## Modify the Composite Query

The only modifications available on a composite query include:

  - Override methods, including methods overridden by the base query

  - Add ranges

### ![Cc588007.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc588007.collapse_all(en-us,AX.60).gif")Override a Method on the Composite Query

X++ code in a method override on the base query is run when the composite query is run. This is true even if you override the same method name on the composite query and comment out the default call to super(). This shows that the class inheritance analogy from C\# does not perfectly describe the relationship between a composite query and its base query.

You can override a method on the composite query that has the same name as the method that is overridden on the base query. When you perform an override, the X++ code **Editor** window does not display the code from the base query. Instead the X++ code is either an empty method or a call to super().

For more information about overriding methods on a composite query, see [Walkthrough: Creating a Form Based on a Composite Query](walkthrough-creating-a-form-based-on-a-composite-query.md).

### ![Cc588007.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc588007.collapse_all(en-us,AX.60).gif")Add a Range to the Composite Query

The effect of adding a range to a composite query depends on the ranges that are on the base query. The most important factor is whether the range on the composite query references a field that is also referenced in a base query range.

For more information about ranges, see [Query Elements in the AOT](query-elements-in-the-aot.md).

#### ![Cc588007.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc588007.collapse_all(en-us,AX.60).gif")A Field that is Referenced by a Base Query Range

For example, Field1 is referenced by two ranges on a base query. The two ranges are conjoined by a Boolean OR operation. You want to add a third range on Field1, and you know it would be conjoined with the two existing ranges by a Boolean OR operation. But you must not affect forms and reports that are based on the base query. So you consider adding the range to a composite query.

If you add the range to a composite query, the range will be conjoined with the two base query ranges by a Boolean AND. In most cases this does not match your intention, and you must find another approach.

#### ![Cc588007.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc588007.collapse_all(en-us,AX.60).gif")A Field that is Not Referenced by a Base Query Range

For example, you want to add a range on Field1. Field1 is not referenced by any range on the base query. Regardless of which query you add the Field1 range to, the new range is conjoined with the existing ranges by a Boolean AND operation. Any form that uses the composite query as its data source is affected the same way regardless of which query the new range is added to.

## Composite Query and Data Sources Nodes are Mutually Exclusive

Under a query node, either the **Data Sources** or the **Composite Query** node can have an object defined, but not both.

## See also

[Query Framework in the AOT](query-framework-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

