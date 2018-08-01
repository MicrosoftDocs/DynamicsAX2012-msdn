---
title: 'How to: Add a Page Title Group to a Simple List Form'
TOCTitle: 'How to: Add a Page Title Group to a Simple List Form'
ms:assetid: 3c71ec62-a4ca-4ae1-9822-16bde9ba7f48
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh538477(v=AX.60)
ms:contentKeyID: 39508910
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Page Title Group to a Simple List Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A simple list or simple list and detail form can include a page title. You use the page title to identify the record that appears in the form or provide context for that record. However, the page title is optional and is not included on all simple list or simple list and details forms. For information about simple list form design, see [Simple List Forms Overview](simple-list-forms-overview.md).

You often use a page title when you have forms that show related data. For example, you use a menu item button on a details form to open a simple list form. When the simple list form appears, the page title identifies the record that is open in the details form. The page title provides context for the records that appear in the simple list form. The following procedures show how to add a page title group to a form and how to add a field to the page title group.

### To add the title group to the form

1.  In the AOT, expand **Forms**, and then expand the form where you want to add the title group.
    

    > [!NOTE]
    > <P>If you use a template to create the form, you do not have to add a control for the page title group. The template includes the page title group. Go to the following section that describes how to add a control to the group.</P>



2.  Expand **Designs**, right-click **Design**, click **New Control**, and then click **Group**. A group control is added to the form. Use the ALT+UP ARROW or ALT+DOWN ARROW to move the group. The page title group should be the first group control on the form. Move the page title group so that it appears after the action pane control.

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
    <td><p>Type a name that uniquely identifies the group. Typically, the group is named <strong>PageTitleGroup</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>DetailTitleContainer</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ViewEditMode</strong></p></td>
    <td><p><strong>View</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Visible</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    </tbody>
    </table>


### To add a control to the title group

1.  In the AOT, expand **Forms**, and then expand the form where you want to add fields to the title group.

2.  Expand **Designs**, expand **Design**, right-click **PageTitleGroup**, click **New Control**, and then click **StringEdit**. A string edit control is added to the group.

3.  Click the string edit control. In the properties sheet for the control, specify values for the following properties.
    

    > [!TIP]
    > <P>Before you specify property values, you should know what field you want to appear in the title group. To specify the field value, you use either the <STRONG>DataField</STRONG> property or the <STRONG>DataMethod</STRONG> property. You cannot populate both properties on one control.</P>

    
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
    <td><p><strong>DataField</strong></p></td>
    <td><p>Select the field from the data source that has the value that you want to appear on the form. You typically use a data field when you want the page title to show a value from the selected record in the simple list or simple list and details form.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DataMethod</strong></p></td>
    <td><p>Specify the method from the form data source that provides the value or values that you want to appear on the form. You typically use a data method when you want the page title to specify values from a parent record.</p>
    <p>For example, you can use the parentTitleFields method of the form data source. You use this method to add the <strong>TitleField1</strong> and <strong>TitleField2</strong> values from the parent data source to the page title of the form.</p>
    
    > [!caution]  
    > <P>To use parentTitleFields, there must be a table relation between the table in the form data source and the data source of the parent record. For more information about table relations, see <a href="defining-table-relations.md">Defining Table Relations</a>.</P>
    
    </td>
    </tr>
    <tr class="odd">
    <td><p><strong>DataSources</strong></p></td>
    <td><p>Select the data source for the form.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>TitleField</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Visible</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    </tbody>
    </table>
    
    For example, the page title of the **Maintain benefits** form shows the name and personnel number of the selected worker in the **Workers** list page. The form opens when you click the **Personal information** \> **Benefits** button in the action pane of the list page. To show the name and personnel number fields, the string edit control in title group of the **HcmWorkerEnrollment** form sets the **DataSource** property to **HcmWorkerEnrolledBenefit**. The **DataMethod** property is then set to parentTitleFields.

4.  To add another field to the title group, repeat the previous two steps.

5.  Right-click the form and then click **Save**.

## See also

[How to: Create a Simple List Form](how-to-create-a-simple-list-form.md)

[How to: Create a Simple List and Details Form](how-to-create-a-simple-list-and-details-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

