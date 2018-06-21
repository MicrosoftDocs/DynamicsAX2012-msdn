---
title: Using the display Method Modifier
TOCTitle: Using the display Method Modifier
ms:assetid: 476d9e09-e41a-48fa-b3c9-e919ed782991
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa595058(v=AX.60)
ms:contentKeyID: 35243016
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using the display Method Modifier [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The display method modifier indicates that the method has a return value that can appear on a form or a report. A display method is any method that includes the display keyword as a method modifier. You can use the display method modifier with the following kinds of methods:

  - Table methods

  - Form methods

  - Form data source methods

  - Report methods

  - Report design methods

You should add a display method as a table method whenever possible. This enables you to use that same code with more than one form or report.


> [!NOTE]
> <P>If you want users to change the value that appears in the control, use the edit method modifier. For more information, see <A href="using-the-edit-method-modifier.md">Using the edit Method Modifier</A>.</P>



When you create or use a display method, you should be aware of the following issues:

  - The display method is called every time that the form is redrawn. To optimize form performance, the display method should not contain complex and time-consuming calculations.

  - The use of a display method can cause unintended information to become visible. For more information, see [Security on Display and Edit Methods](security-on-display-and-edit-methods.md).

  - A display method is not activated if the method appears on a hidden tabbed page.

  - You have to add the display keyword to a form data source method when the return value of that method appears on a grid control.

  - To improve the performance of a display method, you can cache the method. For more information, see [Caching display Methods](caching-display-methods.md).

## To create a display method

To create a display method, follow these steps.

1.  Place the display keyword immediately in front of the method’s return type. For example:
    
    display Amount amount()

2.  Specify the return type. The return type should be an extended data type. In the previous step, the method has a return type of Amount.
    
    Typically, a display method returns a calculated value like a sum or count. For an example of a calculated value, see [How to: Add a Control to a Form](how-to-add-a-control-to-a-form.md).

3.  Determine whether to add parameters to the display method. The following list shows when to add a parameter.
    
      - A display method for a table, form, report, or report design does not have any parameters. For example:
        
        display Amount amount()
    
      - A display method for a form data source does require a parameter. You use the parameter to specify a table buffer. The type of the table buffer has to match the type of the table in the form data source.
        
        The following example shows a display method that returns the number of customer records that appear in the form. Notice how the parameter has a type of CustTable. This table is in the form data source.
        
            display NumberOfRecords testMethod(CustTable myTable)
            {
               NumberOfRecords recCount = this.totalNumberOfRows();
               Return recCount;
            }

## To use a display method in a form

To use a display method with a form control, the control and the return type of the method must be identical types. For example, if you have a RealEdit control on the form, the display method that you are using must return a value of type real.

The following steps show how to use a display method with a form control.

1.  Set the DataSource property for the control to the data source that contains the method.
    
    If you do not set the DataSource property, the system assumes that the display method is defined as a form method.

2.  Set the DataMethod property to the name of the display method.

3.  For some types of controls, you might also want to set the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>ExtendedDataType</strong></p></td>
    <td><p>If this property is set, formatting, Help text, and other property values are inherited from the specified type.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ArrayIndex</strong></p></td>
    <td><p>If the display method returns an array, set this property to 0. The value 0 indicates that all array elements are to be shown in the control. If, for example, you set it to 2, only array element number two is shown.</p></td>
    </tr>
    </tbody>
    </table>


## To use a display method in a report

You can use display methods to provide data for reports. For a SQL Server Reporting Services report, you use a query as the data source for the report. You can use the display methods from the tables in that query to provide the data that appears in the report. For more information, see [How to: Use Display Methods in a Report](https://msdn.microsoft.com/en-us/library/gg724095\(v=ax.60\)).

You can also use display methods with reports that you create or update with the X++ reporting framework. For example, the following steps use a display method from a table to specify a value for a control in a report.

1.  Set the Table property for the control to the table that contains the display method that you want to use.
    
    If you do not set the Table property, the system assumes the specified display method is defined as a report or report design method.

2.  Set the DataMethod property to the name of the display method.

## See also

[Using the edit Method Modifier](using-the-edit-method-modifier.md)

[Caching display Methods](caching-display-methods.md)

[Security on Display and Edit Methods](security-on-display-and-edit-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

