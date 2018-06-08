---
title: Cross-Company Data Access
TOCTitle: Cross-Company Data Access
ms:assetid: a380050c-7ed4-4ce8-92a3-951b309e9239
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc634544(v=AX.60)
ms:contentKeyID: 35248379
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Cross-Company Data Access 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A cross-company query returns data for several companies in a single run. A query does not have to be limited to returning data for the current session company. A cross-company query operates over all companies that you have read permissions for, or over a subset of companies that you specify.

## How to Create a Cross-Company Query

To create a cross-company query:

  - In X++, use the crossCompany keyword on the X++ select statement.

  - In X++, set the allowCrossCompany property method to true on an instance of the Query class.

  - In the AOT, set the **AllowCrossCompany** property to **Yes** on a node under **Query**.

### ![Cc634544.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc634544.collapse_all(en-us,AX.60).gif")Cross-Company Querying in Forms

You can also design cross-company query behavior into dynamically linked parent and child form pairs. One important step in creating such forms is to set the FormDataSource.crossCompanyAutoQuery to true. Or in the AOT, set the **CrossCompanyAutoQuery** property to **Yes** on a node under the **Data Sources** of a **Form**.

## Equivalent to Unions

The results returned for an X++ select crossCompany query match what could be returned by a union of several select statements that each omits the crossCompany keyword.

In the Microsoft Dynamics AX client, you could set your current session company to **CM1**, then run a select query and save the results. You could switch to company **CM2**, rerun the query, and then add the results to the earlier results. You could repeat this cycle for all the companies you are authorized to see. Your accumulated results would be the same as running one select crossCompany.

## In This Section

  - [Cross-Company X++ Code Basics](cross-company-x-code-basics.md)  

  - [Cross-Company and the company Getter Method](cross-company-and-the-company-getter-method.md)  

  - [Cross-Company Queries for Views](cross-company-queries-for-views.md)  

  - [Cross-Company Reports in the AOT](cross-company-reports-in-the-aot.md)  

## See also

[Queries in the AOT for Data Access](queries-in-the-aot-for-data-access.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

