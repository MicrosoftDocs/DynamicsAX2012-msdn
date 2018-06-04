---
title: 'How to: Add Labels, Fields, and Menu Items to a Content Element'
TOCTitle: 'How to: Add Labels, Fields, and Menu Items to a Content Element'
ms:assetid: 4aab78f1-31c8-4386-9f2a-f16883774ac0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882347(v=AX.60)
ms:contentKeyID: 35257175
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
---

# How to: Add Labels, Fields, and Menu Items to a Content Element 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to add a label to a content element. A label is the user interface text that appears on Microsoft Dynamics AX forms and controls. Labels support the localizability of the text elements of the user interface. The following table specifies the types of labels that you can add to your Help documentation:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Label type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Labels</p></td>
<td><p>The text that appears on the user interface. These types of labels are found in a Microsoft Dynamics AX label file.</p></td>
</tr>
<tr class="even">
<td><p>Table fields</p></td>
<td><p>The text that appears on the user interface that represents a field from a data table.</p></td>
</tr>
<tr class="odd">
<td><p>Menu items</p></td>
<td><p>The text that appears on the user interface for a menu item.</p></td>
</tr>
</tbody>
</table>


Before you add a label to your documentation, consider whether the following restrictions affect how that label appears in your documentation.

  - To retrieve the text value of the label, the help server queries the Application Object Server (AOS). As a result, the person who requests the Help document must have permissions to access Microsoft Dynamics AX. If that person does not have permission, the default text value appears in the content element.

  - When the label appears in the help viewer, the text appears in the same language that is used by the Microsoft Dynamics AX client that originated the request.

  - You must use HTML to create your content element. The help server does not support using labels in non-HTML documents.

The following sections describe how to add each type of label to an HTML document.

## Adding a Label from the User Interface

You add labels to documentation that describes a form. To include the specific word or phrase that appears on the form, add the ID of that label to the HTML of your content element. The following steps describe how to make the text from a label appear in a content element.

### To use a label

1.  Find the ID of the label. In the Microsoft Dynamics AX development workspace, click **Tools** \> **Development tools** \> **Label** \> **Label editor**. The **Label editor** opens in a new window. Use the **Label editor** to find the ID of the label.
    
    For example, enter Bank Account in the **Find what** field, expand the **In the language** list, click **en-us**, and then click **Find now**. The **Label editor** lists all the labels that include the specified text value for the specified language. For more information about how to find a label, see [How to: Find a Label](how-to-find-a-label.md).

2.  Open the file that contains your content element in a text or HTML editor. Navigate to the location in the file where you want the label to appear.

3.  Add the \<dynHelpAx:label\> element. Specify values for the following attributes.
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Attribute</p></th>
    <th><p>Value</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>axtype</p></td>
    <td><p>&quot;Label&quot;</p></td>
    <td><p>Set the attribute to &quot;Label&quot;.</p></td>
    </tr>
    <tr class="even">
    <td><p>id</p></td>
    <td><p>The ID value of the label.</p></td>
    <td><p>Specify the ID value that you retrieved using the <strong>Label editor</strong>.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following HTML example adds a label element. Notice how the values of the axtype and id attributes are used to specify the Bank Account label.
    
    ``` html
    <dynHelpAx:label axtype="Label" id="@SYS21829"> </dynHelpAx:label>
    ```

4.  Specify a text value for the \< dynHelpAx:label\> element. If the label cannot be retrieved, the text that you supply appears in the content element.
    

    > [!WARNING]
    > <P>If you do not supply a default text value and the label cannot be retrieved, the content element will not include any value for that label. A missing label can significantly affect the usefulness of a content element. In addition, a missing label can be difficult to identify when you review a newly published document.</P>

    
    The following HTML example sets the default text for the label element to Bank Account.
    
    ``` html
    <dynHelpAx:label axtype="Label" id="@SYS21829">Bank Account</ dynHelpAx:label>
    ```

5.  Save your HTML file.

## Adding a Table Field

You add table field labels when you want your documentation to include the text that appears in the user interface. The following steps describe how to add the label from a table field to the HTML of a content element.

### To use the label from a table field

1.  Find the name of the field. In the AOT, expand **Data Dictionary**, expand **Tables**, and then click the table that contains the field you want to use. Note the value of the **Name** property of that table. Expand **Fields**, and then search the list for the field that contains the label you want to use. Note the value of the **Name** property of that field.

2.  Open the file that contains your content element in a text or HTML editor. Navigate to the location in the file where you want the label to appear.

3.  Add the \< dynHelpAx:label\> element. Specify values for the following attributes.
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Attribute</p></th>
    <th><p>Value</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>axtype</p></td>
    <td><p>&quot;Field&quot;</p></td>
    <td><p>Set the attribute to &quot;Field&quot;.</p></td>
    </tr>
    <tr class="even">
    <td><p>axtable</p></td>
    <td><p>The name of the table.</p></td>
    <td><p>Specify the value of the <strong>Name</strong> property of the table that contains the field.</p></td>
    </tr>
    <tr class="odd">
    <td><p>axfield</p></td>
    <td><p>The name of the field</p></td>
    <td><p>Specify the value of the <strong>Name</strong> property for the field.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following HTML example adds the label from the **Name** field of a customer. Notice how the values of the axtype, axtable, and axfield attributes are used to specify the field.
    
    ``` html
    <dynHelpAx:label axtype="Field" axtable="DirPartyTable" axfield="Name"> </dynHelpAx:label>
    ```

4.  Specify a default text value for the \<label\> element. If the field label cannot be retrieved, the text that you supply appears in the content element. The following HTML example sets the default text for the field to Name.
    
    ``` html
    <dynHelpAx:label axtype="Field" axtable="DirPartyTable" axfield="Name">Name</dynHelpAx:label>
    ```

5.  Save your HTML file.

## Adding a Menu Item Label

You add a menu item label to your documentation when you want to include the text value that appears in the user interface for the specified menu item. The following steps describe how to add the label from a menu item to the HTML of a content element.

### To use the label from a menu item

1.  Find the menu item. In the AOT, expand **Menu Items**, and then expand the menu item category. For example, expand the **Display** node. Search the list for the menu item that contains the label you want to use. Note the value of the **Name** property for that menu item.

2.  Open the file that contains your content element in a text or HTML editor. Navigate to the location in the file where you want the menu item label to appear.

3.  Add the \<dynHelpAx:label\> element. Specify values for the following attributes.
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Attribute</p></th>
    <th><p>Value</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>axtype</p></td>
    <td><p>&quot;MenuItem&quot;</p></td>
    <td><p>Set the attribute to &quot;MenuItem&quot;.</p></td>
    </tr>
    <tr class="even">
    <td><p>axmenutype</p></td>
    <td><p>&quot;Display&quot;</p></td>
    <td><p>Set the attribute to &quot;Display&quot;.</p></td>
    </tr>
    <tr class="odd">
    <td><p>axmenuitem</p></td>
    <td><p>The name of the menu item.</p></td>
    <td><p>Specify the value of the <strong>Name</strong> property for the menu item.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following HTML example adds the label for the **SalesTable** menu item. Notice how the values of the axtype, axmenutype, and axmenuitem attributes are used to specify the menu item.
    
    ``` html
    <dynHelpAx:label axtype="MenuItem" axmenutype="Display" axmenuitem="SalesTable"> </dynHelpAx:label>
    ```

4.  Specify a default text value for the \<label\> element. If the menu item label cannot be retrieved, the text that you supply appears in the content element. The following HTML example sets the default text for the field to Sales order.
    
    ``` html
    <dynHelpAx:label axtype="MenuItem" axmenutype="Display" axmenuitem ="SalesTable">Sales order</dynHelpAx:label>
    ```

5.  Save your HTML file.

## See also

[Walkthrough: Creating Help Documentation](walkthrough-creating-help-documentation.md)

[How to: Create a Help Document using a Template](how-to-create-a-help-document-using-a-template.md)

