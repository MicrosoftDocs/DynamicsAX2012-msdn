---
title: Cross-Company Methods and Properties
TOCTitle: Cross-Company Methods and Properties
ms:assetid: 3370c7a5-5bd3-42ba-acac-6f3f95d93345
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc569524(v=AX.60)
ms:contentKeyID: 35241995
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Cross-Company Methods and Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++ code, you can call functions that are related to cross-company functionality by using:

  - Query class methods

  - changeCompany X++ keyword

In X++ code, you can set properties that are related to cross-company functionality by using:

  - allowCrossCompany on a Query instance

  - company on a table buffer (extended from xRecord class)

  - crossCompanyAutoQuery on a FormDataSource instance

Just as these properties can be set in X++ code, they can also be set in the Application Object Tree (AOT). These methods can be called in methods overridden in the AOT.

## Functions

### ![Cc569524.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc569524.collapse_all(en-us,AX.60).gif")Methods on the Query class

In X++ code, after you create an instance of the [Query](https://msdn.microsoft.com/en-us/library/gg913387\(v=ax.60\)) class, you can call several instance methods that are related to cross-company functionality. These query methods are relevant only if you set the query's allowCrossCompany property to true:

  - addCompanyRange

  - clearCompanyRange

  - getCompanyRange

If you do not call addCompanyRange, the query returns data for all companies that the user has authority to read. You can call addCompanyRange to restrict the range of company data that the query returns. The first call to addCompanyRange minimizes the data that the query returns because data is returned for only the first company that is added. Subsequent calls to addCompanyRange increase the amount of data returned by the query.

The clearCompanyRange method cancels the earlier calls to addCompanyRange. The clearCompanyRange method has no effect if addCompanyRange has not been called.

The getCompanyRange method returns a container of dataAreaId values that have been added.

### ![Cc569524.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc569524.collapse_all(en-us,AX.60).gif")changeCompany Keyword

The X++ language has a [keyword](x-keywords.md) changeCompany. You use changeCompany to create a bracketed scope in which the active company can differ from your session company.

The keyword changeCompany is used in data modification processing in cross-company scenarios.

For more information about how to use changeCompany for data modification in cross-company scenarios, see [Cross-Company Data Modification Using X++](cross-company-data-modification-using-x.md).

For more information about how to use the changeCompany keyword beyond cross-company processes, see [Change Company Design Pattern](change-company-design-pattern.md).

## Properties

There are properties you can set that are related to cross-company functionality. In X++ these can be either properties or property methods (which are small methods that get and set a state of the object). In the AOT, these appear in the **Properties** window.

### ![Cc569524.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc569524.collapse_all(en-us,AX.60).gif")AllowCrossCompany Property on Query

In the AOT, each query node has the **AllowCrossCompany** property. The default value is **No**. You can set this property to **Yes** to make the query return data for all companies that you are authorized to read from.

This is the same property that can be accessed in X++ code on an instance of the Query class.

### ![Cc569524.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc569524.collapse_all(en-us,AX.60).gif")Company Property on xRecord Buffers

In X++ code, a buffer variable can be declared for a table. For the BankAccountTable, the buffer declaration could be: BankAccountTable myBat;. The myBat variable inherits all the methods and properties from the [xRecord](https://msdn.microsoft.com/en-us/library/gg950368\(v=ax.60\)) class.

One of the properties inherited by a table buffer is company. In X++, the syntax is a pair of get and set property methods (the setter takes a parameter).

In the AOT, this property is not present on tables that are immediately under the **Tables** node. But when a table is dragged onto a query's **Data Sources** node, that new table node has the **Company** property. The default setting is blank.

This **Company** property must be left blank when the **AllowCrossCompany** property is set to **Yes**.

### ![Cc569524.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc569524.collapse_all(en-us,AX.60).gif")Purpose of Setting the Company Property

When **AllowCrossCompany** is **No**, you can set a data source's **Company** property to a non-blank value to alter the current company context, as an override to the current session company. This is similar to using the changeCompany keyword in X++ code, although the scope or duration of the change is different.

You can set **Company** to a value to automate agreements between two companies. For example, the creation of a purchase order might automatically generate an invoice for the other company.

## See also

[Cross-Company X++ Code Basics](cross-company-x-code-basics.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

