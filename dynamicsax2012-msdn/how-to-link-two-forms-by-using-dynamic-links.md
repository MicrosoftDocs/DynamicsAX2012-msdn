---
title: 'How to: Link Two Forms by Using Dynamic Links'
TOCTitle: 'How to: Link Two Forms by Using Dynamic Links'
ms:assetid: 81d7aae1-b8f3-4d5b-8839-9ae80b95c736
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb394995(v=AX.60)
ms:contentKeyID: 35246144
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Link Two Forms by Using Dynamic Links 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Two forms can be linked so that moving focus to a different row in a grid causes an immediate change in the data that is displayed in the other form. Microsoft Dynamics AX provides dynamic links for this purpose. Dynamic links are created by using the Application Object Tree (AOT), without writing any code.


> [!NOTE]
> <P>Dynamic links in Microsoft Dynamics AX are not DLLs.</P>



## Dynamic Links are Based on Extended Data Types

The following is a list of the elements that work together to create the dynamic link behavior between a parent form and a child form. This list emphasizes the sharing of an extended data type:

  - A data relationship exists between two tables, usually as one-to-many (one parent row relates to many child rows).

  - Each table has a field of the same extended data type.

  - In the parent table, the extended data type field values uniquely identify each row.

  - The extended data type has a relation defined on it for the field in the parent table.

  - Each table is a data source for one of the two forms.

  - The parent form contains a button that launches the child form.


> [!NOTE]
> <P>For more information about extended data types, see <A href="how-to-create-an-extended-data-type.md">How to: Create an Extended Data Type</A>.</P>



## Dynamic Link Scenario

The following scenario explains the steps necessary to create a dynamic link between two forms.

A form displays a grid control of bank account numbers. One row in the grid is highlighted. This parent form has a button that opens a child form to display transactions. The child form shows only the transactions for the account that is highlighted in the parent's grid. When the user moves focus to a different account row in the grid, the transactions form automatically refreshes itself. The transactions form now shows only the transactions for the newly highlighted account.

The account table and the transactions table each have a field of the same extended data type. For example, CompanyBankAccountId might be an appropriate name for the extended data type that the two tables share. The account table is the data source for the account form, and the transactions table is the data source for the transactions form.


> [!NOTE]
> <P>For more information about creating forms, see <A href="walkthrough-creating-a-form-by-using-the-aot.md">Walkthrough: Creating a Form by Using the AOT</A>.</P>



Use the following steps in the AOT to create dynamic link behavior between the two forms.

1.  Verify that the parent and child tables both have a field of the same extended data type by checking the ExtendedDataType property of the fields of the tables.

2.  In the AOT, expand the **Data Dictionary** node, and then expand the **Tables** node. Expand the table that is the data source for the parent form, and then expand its **Relations** node.

3.  Right-click the **Relations** node, and choose **New Relation**. Change the **Name** property as appropriate. For the newly created relation, set its **Table** property to the name of the data source of the child form.

4.  In the AOT, expand the **Menu Items** node, and then expand the **Display** node.

5.  Drag the child form onto the **Display** node (unless it is already present). This drag step is more straightforward if two AOT windows are open.

6.  Under the node for the parent form, expand the **Designs** node, and then expand the **Design** node.

7.  Right-click the **Design** node, and then select **New Control**, **MenuItemButton**.

8.  Set the button's MenuItemName property to match the name of the child form. Set its DataSource property to match the name of the parent table.

The dynamic link is now created.

### ![Bb394995.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb394995.collapse_all(en-us,AX.60).gif")Test the Dynamic Link

1.  Right-click the parent form, and then select **Open**.

2.  Open the child form by clicking the menu item button that you added.

3.  In the grid on the parent form, move focus to another row. The child form immediately displays different data.

## See also

[How to: Join Data Sources for a Form](how-to-join-data-sources-for-a-form.md)

[How to: Coordinate Two Forms by Overriding an Event Method](how-to-coordinate-two-forms-by-overriding-an-event-method.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

