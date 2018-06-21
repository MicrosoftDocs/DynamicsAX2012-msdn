---
title: 'How to: Customize a List Page Grid'
TOCTitle: 'How to: Customize a List Page Grid'
ms:assetid: ea86f0de-2ced-4cd5-a0e6-27a483b3aab8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc622504(v=AX.60)
ms:contentKeyID: 35253232
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Customize a List Page Grid [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To enhance the information that you get from a list page, you can customize how data fields appear in the data grid. The following sections describe how you customize columns.

  - Using Hidden Fields with a List Page

  - Using Icons in the Data Grid

## Using Hidden Fields with a List Page

To support the data needs of different user roles, you can add data fields that do not at first appear on the data grid. You can only use hidden fields together with a list page in the client. You cannot add hidden field from a list page in Enterprise Portal. A user who wants to add a hidden field can do so by using the client personalization tools. To add a hidden field, follow these steps.

### To create a hidden field

1.  In the AOT, expand the **Forms** node, expand the list page form, expand **Data Sources**, expand the list page data source node, expand the **Fields** node, and then click the field that you want to add as a hidden field. View the properties for the selected field.

2.  Click the **AllowAdd** property, and set its value to **Yes**.

3.  Right-click the form, and then click **Save**.

### To add the hidden field to the list page

1.  To add a hidden field, open the Microsoft Dynamics AX client, open the list page, right-click the list page, and then click **Personalize**.

2.  In the **Personalization** window, click **Add fields**, click the field you want to add, and then click **Add**. For more information about user personalization, see [Enabling User Personalization of Forms](enabling-user-personalization-of-forms.md).

## Using Icons in the Data Grid

To quickly identify records in a list page grid that meet specified criteria, you can add a column that displays icons. Typically, the icons call attention to records that require special attention. You can only view a column with icons in a list page on the client. The icons do not appear when you view the list page in Enterprise Portal.


> [!NOTE]
> <P>You can also use the <STRONG>ImageResource</STRONG> property of the <STRONG>Window</STRONG> control to add an image to the data grid. However, the image is applied to all records in the grid.</P>



The following procedures show how to add an icon to each record that meets specified criteria.

### To create the data source method

1.  In the AOT, expand the **Data Dictionary** node, expand Tables, expand the table you use in the list page data source, right-click **Methods**, and then click **New Method**. The code editor window opens and displays the following.
    
        Private void method1()
        {
        }

2.  Replace private void method1() with a display method that uses the table as a parameter. For more information about display methods, see [Using the display Method Modifier](using-the-display-method-modifier.md).
    
    The following code example adds a display method named creditRatingAlert to **CustTable**.
    
        display int creditRatingAlert(CustTable custTable)
        {
        }

3.  Add code to the method that determines when to display an image. The code must also return the resource ID of the image to display.
    

    > [!NOTE]
    > <P>To view the available images, display the <STRONG>Tools</STRONG> menu in the developer workspace. Click <STRONG>Embedded resources</STRONG>. The <STRONG>Embedded resources</STRONG> window displays the available images, and the resource ID of each image.</P>

    
    The following code example returns the resource ID of the alert icon when the value of the customer **CreditRating** field is set to Poor.
    
        display int creditRatingAlert(CustTable custTable)
        {
            // If the value in the CreditRating field 
            // is equal to Poor, return an integer equal to the
            // resource ID of the alert symbol.
            if(custTable.CreditRating == "Poor")
            {
                return 792;
            }
           else
           {
               return 1030;
           }
        }

4.  To validate and save your code changes, click the **Compile** button in the code editor window. Close the code editor window.

The table method returns the resource ID of the image that you want to appear in the data grid. Now, you have to add a column where the icon appears on the data grid.

### To add an icon column to a grid

1.  Expand the list page form, expand **Designs**, expand the **Design** node, right-click **Grid**, click **New Control**, and then click **Window**. A **Window** control enables you to add images to the data grid. For more information about window controls, see [Overview of Form Control Types](overview-of-form-control-types.md).

2.  To change the location of a column, expand the **Grid**, select the **Window** control, and then press ALT+UP ARROW or ALT+DOWN ARROW.

3.  Right-click the **Window** control, and then click **Properties**. Use the **Properties** window to set the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>DataMethod</strong></p></td>
    <td><p>Enter the name of the method that you added to the data source table.</p>
    <p>For example, enter creditRatingAlert to use the method added to <strong>CustTable</strong> in the previous code example.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataSource</strong></p></td>
    <td><p>Specify the table that contains the method that you entered in the <strong>DataMethod</strong> property.</p>
    <p>For example, if you entered creditRatingAlert, which is defined for CustTable, you would click <strong>CustTable</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DisplayTarget</strong></p></td>
    <td><p><strong>Client</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Height</strong></p></td>
    <td><p><strong>16</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that identifies the control.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ShowLabel</strong></p></td>
    <td><p>Specify whether the value in the <strong>Label</strong> property appears on the data grid. Typically, you set this property to <strong>No</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>VerticalSpacing</strong></p></td>
    <td><p><strong>0</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Width</strong></p></td>
    <td><p><strong>16</strong></p></td>
    </tr>
    </tbody>
    </table>


4.  Right-click the form, and then click **Save**.

When the list page grid loads, the data source method named in the **DataMethod** property is called for each record. If a record meets the criteria in the method, the specified icon appears with that record in the data grid.

## See also

[How to: Add Fields to the List Page Grid](how-to-add-fields-to-the-list-page-grid.md)

[How to: Add a Control to a Form](how-to-add-a-control-to-a-form.md)

[User Personalization of Forms](user-personalization-of-forms.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

