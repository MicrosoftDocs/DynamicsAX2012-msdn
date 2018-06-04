---
title: 'How to: Specify the Page Title for a Details Form'
TOCTitle: 'How to: Specify the Page Title for a Details Form'
ms:assetid: 7f1e5f3f-4c50-40e2-a71c-6826e78b73b9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528506(v=AX.60)
ms:contentKeyID: 37835254
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Specify the Page Title for a Details Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to populate the page title of a details form. You use the page title to identify the record that appears in the form. Typically, you use the page title to show the ID and name values from the record. You can also show additional information about the record below the page title.

Before you complete these steps, you must first add one or more tables to the **Data Sources** node of the form. For information about how to add a data source to the form, see [How to: Add a Data Source to a Details Form](how-to-add-a-data-source-to-a-details-form.md).

### To specify the header title

1.  In the AOT, expand **Forms** and find the form you want to add a page title to.

2.  In the form node, expand **Designs**, expand **Design**, expand **Tab**, expand **TabPageDetails**, expand the **HeaderInfo** group, right-click **HeaderTitle** control, and then click **Properties**. The **Properties** window opens.

3.  In the property sheet click **DataSource** and then select the table you want to use.
    
    For example, the **HeaderTitle** of the **Customers** form specifies CustTable in the **DataSource** property of the control.

4.  You can use either a field or a data method to specify the data values that appear in the title for the group. To use a field, click the **DataField** property and then click the field that contains the values that you want to appear. To use a table method, click **DataMethod** and then type the name of the method that returns the value or values that you want to appear.
    
    For example, the **Customers** form uses the titleFields method from CustTable table to populate the page title.

## See also

[Details Form User Experience Guidelines](details-form-user-experience-guidelines.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

