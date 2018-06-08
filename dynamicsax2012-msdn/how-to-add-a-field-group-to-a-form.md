---
title: 'How to: Add a Field Group to a Form'
TOCTitle: 'How to: Add a Field Group to a Form'
ms:assetid: 69ce681a-d7ce-45b0-b417-b7fb48a40d14
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa609505(v=AX.60)
ms:contentKeyID: 35244784
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Field Group to a Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A field group is a collection of fields that the system treats as one item. A field group can appear on multiple forms. When you add or remove a field from a field group, the field is immediately added or removed from each form where the field group appears. For more information about field groups, see [Defining Field Groups](defining-field-groups.md).

To create a field group, you use the Application Object Tree (AOT) to add the field group and its fields to a table. For detailed information about how to create a field group, see [How to: Create a Field Group](how-to-create-a-field-group.md). You also use the AOT to assign the field group to the form where you want the field values to appear.

## Creating and Assigning Field Groups by Using the AOT

The following procedures show how to create a field group and how to add a field group to a form.

### ![Aa609505.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa609505.collapse_all(en-us,AX.60).gif")To add a field group to a table

1.  In the AOT, expand **Data Dictionary**, expand **Tables**, and then find and expand the table where you want to add a field group.
    
    For example, you want to add a field group to the table for customers. Therefore, you find and expand the **CustTable** node.

2.  Right-click **Field Groups**, and then click **New Group**. The AOT adds a field group named **Group1**.

3.  Right-click **Group1**, and then click **Rename**. Type a name that uniquely identifies the group.
    
    For example, you type MyFieldGroup for the name of the field group that you added to **CustTable**.

4.  In the AOT, right-click the **Fields** node, and then click **Open New Window**. The list of fields appears in a separate AOT window.

5.  In the AOT window that shows the list of fields, drag fields from the **Fields** node onto field group you added in the first AOT window.
    
    For example, drag the **AccountNum**, **CreditMax**, and **CreditRating** fields onto the **MyFieldGroup** node you added to **CustTable**.

6.  To save the field group, right-click table, and then click **Save**.

### ![Aa609505.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa609505.collapse_all(en-us,AX.60).gif")To add a field group to a form

1.  Press CTRL+D to open an AOT window, expand the **Forms** node, and then find the form where you want to add the field group.
    
    If you want to create a form, right-click the **Forms** node, click **New Form from template**, and then click the type of form you want to use.
    
    For example, you click **New Form from template** and then select **SimpleList**.

2.  Specify a name that uniquely identifies the form. To change the name, right-click the form, click **Rename**, and then type a name that uniquely identifies the new form.
    
    For example, you right-click the simple list form you created in the previous step, click **Rename**, and then type MySimpleListForm.

3.  In the AOT window that shows the table with the field group, click the table and then drag the table onto the **Data Sources** node of the form.
    

    > [!WARNING]
    > <P>You cannot drag a field group from a table in the <STRONG>Data Dictionary</STRONG> onto the form or the <STRONG>Design</STRONG> node of the form. You must first add the table that includes the field group to <STRONG>Data Sources</STRONG> node of the form.</P>

    
    For example, you drag **CustTable** onto the **Data Sources** node of MySimpleListForm.

### ![Aa609505.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa609505.collapse_all(en-us,AX.60).gif")To add fields to the form

1.  Expand the form node, expand **Designs**, and then expand **Design**.
    
    For example, you expand MySimpleListForm, expand **Designs**, expand **Design**, and then expand the **GridContainer** group. You should see the grid control for the simple list form.

2.  Expand the **Data Sources** node, right-click the table, and then click **Open New Window**. The table in the data source appears in a separate AOT window.
    
    For example, you expand the **Data Sources** node of the MySimpleListForm form, right-click **CustTable** and then click **Open New Window**.

3.  In the AOT window that shows the data source table, expand the **Fields** node and then click the field group you want to appear on the form. Drag the field group onto the **Design** node or a control in the **Design** node of the form. A control is added for the field group and for each field in the group.
    
    For example, you drag the MyFieldGroup that you added to **CustTable** onto the grid control of MySimpleListForm. If you expand the grid control you should see a group control named **MyFieldGroup**. If you expand the group, you should see the controls for the **AccountNum**, **CreditMax**, and **CreditRating** fields.
    

    > [!TIP]
    > <P>Use the <STRONG>DataSource</STRONG> property of the grid control to specify the table in the data source where the field group appears. If you do not specify the data source, the field values will not appear in the grid. For example, you use <STRONG>CustTable</STRONG> to populate the <STRONG>DataSource</STRONG> property of the grid that appears in MySimpleListForm.</P>



4.  Right-click the form, and then click **Save**.

To see the fields on the form, right-click the form and then click **Open**. For example, you right-click MySimpleListForm, and then click **Open**. The form appears and you can see a list of values for the fields specified by MyFieldGroup.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

