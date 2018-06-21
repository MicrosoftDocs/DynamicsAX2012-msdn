---
title: 'How to: Create a Details Form'
TOCTitle: 'How to: Create a Details Form'
ms:assetid: e999d83a-a0e2-41e0-b333-cd5e9ec3a7d0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528511(v=AX.60)
ms:contentKeyID: 37835258
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Details Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to use a form template from the AOT to create a details form. To create the form, follow these steps.

### To create the details form

1.  In the AOT, right-click **Forms**, click **New Form from template**, and then click **DetailsFormMaster** or **DetailsFormTransaction**. The new details form appears in a second AOT window.

2.  Right-click the new form and then click **Properties**. In the **Properties** window, click **Name**, and then type a unique name for the form.

3.  Expand **Designs** and then click **Design**. In the **Properties** window click **Caption**, and then specify the label you want to appear in the title of the form.

4.  Click the **Style** property. If **Style** specifies **DetailsFormMaster**, go to the next step. If **Style** specifies **DetailsFormTransaction**, expand the **Design** node, expand **Tab**, expand **TabPageDetails**, expand **DetailsTab**, expand **LineView**, and then expand **LineViewTab**.
    
      - Click **LineViewHeader**, click the **Caption** property, and then specify the label you want to use as the title for the tab page. Typically, you use the entity name followed by **header**. For example, **Sales order header** is the caption used in the sales order details page.
    
      - Click **LineViewLines**, click the **Caption** property, and then specify the label you want to use as the title for the tab page. Typically, you use the entity name followed by **lines**. For example, **Sales order lines** is the caption used in the sales order details page.

5.  Verify that the **Design** node contains the **ActionPane**, **ActionPaneTab**, **ButtonGroup**, and **Button** controls for the form.

6.  Right-click the form and then click **Save**.

After you create the form, you must add a data source to the form. For information about how to add a data source, see [How to: Add a Data Source to a Details Form](how-to-add-a-data-source-to-a-details-form.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

