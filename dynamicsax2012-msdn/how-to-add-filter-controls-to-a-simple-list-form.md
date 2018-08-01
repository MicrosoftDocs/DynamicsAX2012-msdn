---
title: 'How to: Add Filter Controls to a Simple List Form'
TOCTitle: 'How to: Add Filter Controls to a Simple List Form'
ms:assetid: 6a513e12-5fe8-4524-bbfc-72c3ffbc9885
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh745335(v=AX.60)
ms:contentKeyID: 42607685
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add Filter Controls to a Simple List Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A simple list or simple list and detail form can include a custom filter group. You use controls in the custom filter group to specify field values. The grid then lists the records that include the specified values. However, a custom filter is optional and is not included on all simple list or simple list and details forms. For more information, see [Simple List Forms Overview](simple-list-forms-overview.md).

To enable a form to be filtered, you add one or more controls to the custom filter group of the form. Typically, the custom filter group appears under the action pane strip and the optional page title group. To learn about the page title group, see [How to: Add a Page Title Group to a Simple List Form](how-to-add-a-page-title-group-to-a-simple-list-form.md).

### To add the custom filter group

1.  In the AOT, expand **Forms**, and then expand the form where you want to add the custom filter group.
    

    > [!NOTE]
    > <P>If you use a template to create the simple list or simple list and details form, a custom filter group control was already added to the <STRONG>Design</STRONG> node of the form. To use the existing filter group, go to the procedure that describes how to add a control to the group.</P>



2.  Expand **Designs**, right-click **Design**, click **New Control**, and then click **Group**. A group control is added to the form. Use the ALT+UP ARROW or ALT+DOWN ARROW to move the group. Move the custom filter group so that it appears under the action pane control. If the form includes a page title group, move the custom filter group under the page title group.

3.  Right-click the group control, and then click **Properties**. In the properties sheet, verify the following property values:
    
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
    <td><p><strong>AlignChild</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a name that uniquely identifies the group. Typically, the group is named <strong>CustomFilterGroup</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>DetailTitleContainer</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ViewEditMode</strong></p></td>
    <td><p><strong>Edit</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Visible</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    </tbody>
    </table>


4.  Right-click the form and then click **Save**.

### To add a control to the custom filter group

1.  In the AOT, expand **Forms**, and then expand the form where you want to add fields to the filter group.

2.  Expand **Designs**, expand **Design**, right-click **CustomFilterGroup**, click **New Control**, and then click the type of control you want to use. The control is added to the group.
    
    For example, click **ComboBox** to add a field that you can use to show enum or EDT values. To specify the values that appear in the control, use the **EnumType** or **ExtendedDataType** property. For example, the filter control of the **BudgetTransactionInquiry** form sets the **EnumType** property to **AllDraftCompleted**.

3.  Expand the control node, right-click **Methods**, click **Override methods**, and then click **modified**. The method opens in the code editor.

4.  Add code to the method that updates the form by using the specified filter value. Add the code after the call to super in the modified method.
    
    The following code example shows how to refresh the form after a value is selected in the filter control. In this example, Table1\_ds is the data source for the form. To follow the example, you would replace Table1\_ds with the name of the table in the data source of the form.
    ```X++  
        public boolean modified()
        {
            boolean ret;
            
            ret = super();
            
            // A new filter value has been selected; refresh the form using that filter value.
            Table1_ds.executeQuery();
            
            return ret;
        }
    ```
### To use the control value to filter the form

1.  Expand the **Methods** node of the form, right-click **classDeclaration**, and then click **View Code**. The method opens in the **Editor** window.

2.  In the classDeclaration method, declare a variable of type **QueryFilter**. The following code example shows how to declare a variable named queryFilter.
    ```X++  
        public class FormRun extends ObjectRun
        {
            QueryFilter queryFilter;
        }
    ```
3.  Expand the **Data Sources** node, and then find the table that has the field that has the values that you will use to filter the list.

4.  Expand the table node, right-click **Methods**, click **Override method**, and then click **init**. The method opens in the **Editor** window.

5.  Use the addQueryFilter method of the data source query to initialize queryFilter. Add your code after the call to **super**. Use the addQueryFilter method to specify the table and field you will use to filter the list. The method returns a QueryFilter object. For information about the QueryFilter class, see [How to: Use the QueryFilter Class with Outer Joins](how-to-use-the-queryfilter-class-with-outer-joins.md).
    
    The following code example initializes queryFilter. In this example, Table1\_ds represents the data source for the form. In addition, relatedID specifies the name of a field in Table1. To follow the example, replace Table1\_ds and relatedID with the name of a table and a field from the data source of the form.
    ```X++  
        public void init()
        {
            super();
            
            // Add a filter to the query. Specify the field to use in the filter.
            queryFilter = Table1_ds.query().addQueryFilter(Table1_ds.queryBuildDataSource(),"relatedID");
        }
    ```
6.  In the same table, right-click the **Methods**, click **Override method**, and then click **executeQuery**. The method opens in the **Editor** window.

7.  Associate the value of the filter group control you added earlier with the queryFilter object. Add your code before the call to **super**.
    
    The following code example uses the value of a control named ComboBox to specify the value for the queryFilter object. To follow the example, replace **ComboBox** with name of the filter control you added earlier.
    ```X++  
        public void executeQuery()
        {
            // Get the filter value from the filter control.
            queryFilter.value(element.design().controlName("ComboBox").valueStr());
            
            super();
        }
    ```

    > [!NOTE]
    > <P>If you find the filter creates a new record when you expect the form to be empty. Set the <STRONG>ViewEditMode</STRONG> property in the <STRONG>Design</STRONG> node of the form to <STRONG>View</STRONG>.</P>



8.  Right-click the form, and then click **Save**.

## See also

[How to: Create a Simple List Form](how-to-create-a-simple-list-form.md)

[How to: Create a Simple List and Details Form](how-to-create-a-simple-list-and-details-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

