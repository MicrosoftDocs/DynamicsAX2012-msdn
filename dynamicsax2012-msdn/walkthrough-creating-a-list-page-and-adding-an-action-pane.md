---
title: 'Walkthrough: Creating a List Page and Adding an Action Pane'
TOCTitle: 'Walkthrough: Creating a List Page and Adding an Action Pane'
ms:assetid: d7827fa0-2d8d-4846-ade1-0fe73a928273
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc639151(v=AX.60)
ms:contentKeyID: 35252063
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating a List Page and Adding an Action Pane [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An action pane is the part of a Microsoft Dynamics AX list page that enables you to work with the records in the list. In this walkthrough you will use the Application Object Tree (AOT) to create a basic customer list page and then add an action pane to that list page. This walkthrough shows how to do the following tasks:

  - Create a list page interaction class.

  - Create a list page form.

  - Add a data source to the list page.

  - Add fields to the data grid.

  - Add a tab to the action pane.

  - Add a button group to the tab.

  - Add a button to the button group.

## Prerequisites

To complete this walkthrough, you need:

  - Microsoft Dynamics AX

  - A license file that includes access to the MorphX development environment

  - Sample data in the CustTable database table of a company that you can access

## Creating a List Page

In this section, you create a list page interaction class, create the list page form, add a data source, and then add fields to the data grid. The following procedures create a list page that can display a list of customers.

### To create the list page interaction class

1.  In the AOT, right-click the **Classes** node, and then click **New Class**. The **Classes** node expands and displays a new class.

2.  Right-click the new class, and then click **Properties**. In the **Properties** window, click **Name**, and then enter **SampleListPageInteraction**.

3.  Expand the class node, and double-click **classDeclaration**. The class declaration opens in the Editor window.

4.  To modify the class declaration, click **classDeclaration** in the Editor window, and then add extends ListPageInteraction to line that defines the class. The following code example shows the class declaration for the **SampleListPageInteraction** class.
    
        Class SampleListPageInteraction extends ListPageInteraction

5.  Click **Save** and then close the Editor window.

### To create the list page form

1.  In the AOT, right-click the **Forms** node, click **New Form from template**, and then click **ListPage**. The **Forms** window opens and shows the new form.

2.  Right-click the new form, and then click **Properties**. The properties window opens.

3.  In the properties window, click the **Name** property of the form, and then enter **SampleListPage**.

4.  Click the **InteractionClass** property, expand the drop down list, and then click **SampleListPageInteraction**.

5.  To view the display properties of the form, expand the **Designs** node for the form, and then click **Design**. In the properties window, click the **Caption** property, and then enter **Sample List Page**.

6.  Expand the **Design** node and verify that the form includes an action pane, filter group, and grid control.

7.  In the AOT, right-click the **SampleListPage** form, and then click **Save**.

### To add the data source

1.  The data source for the list is defined by a query. To specify the query to use with the list page, click the **Data Sources** node for the form. The data source properties appear in the **Properties** window.

2.  Click the **Query** property, and then set its value to **CustTableListPage**. The query and the data sources of that query are added to the form.

3.  In the **Design** node, right-click the grid, and then click **Properties**. In the properties window, click the **DataSource** property, and then click **CustTable** in the drop-down list.

4.  Click the **Design** node. In the properties window, set the **DataSource** and **TitleDataSource** properties to **CustTable**.

5.  

### To specify the default action for the grid

1.  In the AOT, expand the form, expand **Designs**, expand **Design**, and then expand the action pane node.

2.  In the Action Pane node, expand the action pane tab labeled **HomeTab**, expand the button group labeled **MaintainGroup**, right-click the menu item button labeled **ViewButton**, and then click **Properties**.

3.  Click the **MenuItemName** property. Use the drop-down list to find and then click the menu item named **CustTableDetails**.

### To add fields to the grid

1.  Expand the **Data Sources** node of the form, right-click the **CustTable** node under the **CustTableListPage** query, and then click **Open New Window**. The **CustTable** data source appears in a new AOT window.

2.  In the window that displays the **CustTable** data source, expand **Fields**.

3.  Drag the **AccountNum**, **Party**, **SegmentId**, **Currency**, and **PaymTermId** fields from the **CustTable** data source window onto the **Grid** control of the **SampleListPage** form.

4.  Close the window that displays the **CustTable** data source.

5.  In the AOT, right-click the **SampleListPage** form, and then click **Save**.

## Adding an Action Pane Tab

In this section, you add a tab control to the action pane. The action pane, several common button groups, and several common buttons are added to the form when you use the list page template to create the form. An action pane must have at least one action pane tab. The following steps add a “General” action pane tab.


> [!NOTE]
> <P>If you want to copy an action pane tab from an existing list page, use the AOT to drag the action pane tab from the existing list page onto the action pane control of the new list page. This adds the action pane tab, all the button groups, and all the buttons for that tab.</P>



### To add the action pane tab

1.  Expand the **Designs** node, expand **Design**, and then click **ActionPane**.

2.  Right-click the action pane control, click **New Control**, and then click **ActionPaneTab**. A control named **ActionPaneTab** is added to the action pane.

3.  Click **ActionPaneTab** to display the control properties in the **Properties** window. Set the specified values for the following action pane tab properties.
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>General</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Caption</strong></p></td>
    <td><p><strong>General</strong></p>
    
    > [!note]  
    > <P>When the action pane is displayed, this value will be the tab label.</P>
    
    </td>
    </tr>
    </tbody>
    </table>


## Adding Button Groups to the Action Pane Tab

In this section, you add two button groups to the **General** action pane tab. An action pane tab must contain at least one button group control.

### To add the first button group

1.  Right-click the **General** action pane tab, click **New Control**, and then click **ButtonGroup**. A control named **ButtonGroup** is added to the action pane tab.

2.  Click the new button group to display the control properties in the **Properties** window. Set the specified values for the following button group properties.
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>List</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Caption</strong></p></td>
    <td><p><strong>List</strong></p>
    
    > [!note]  
    > <P>When the action pane is displayed, this value will be the button group label.</P>
    
    </td>
    </tr>
    </tbody>
    </table>


### To add the second button group

1.  Right-click the **General** action pane tab, click **New Control**, and then click **ButtonGroup**. A control named **ButtonGroup** is added to the action pane tab.

2.  Click the new button group to display the control properties in the **Properties** window. Set the specified values for the following button group properties.
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>Attachments</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Caption</strong></p></td>
    <td><p><strong>Attachments</strong></p>
    
    > [!note]  
    > <P>When the action pane is displayed, this value will be the button group label.</P>
    
    </td>
    </tr>
    </tbody>
    </table>


## Adding Buttons to the Button Groups

In this section, you add a button to each button group that you created earlier. A button group must contain at least one button control.

### To add a command button to the List button group

1.  Right-click the **List** button group, click **New Control**, and then click **CommandButton**. A control named **CommandButton** is added to the button group.

2.  Click the new button to display the control properties in the **Properties** window. Set the specified values for the following button properties.
    
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
    <td><p><strong>Big</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ButtonDisplay</strong></p></td>
    <td><p><strong>Text &amp; Image above</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Command</strong></p></td>
    <td><p><strong>Export To Microsoft Excel</strong></p>
    
    > [!note]  
    > <P>This is the action that the button performs when it is clicked.</P>
    
    </td>
    </tr>
    <tr class="even">
    <td><p><strong>ImageLocation</strong></p></td>
    <td><p><strong>EmbeddedResources</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>MultiSelect</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>ExportToExcel</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>NormalImage</strong></p></td>
    <td><p><strong>10156</strong></p>
    
    > [!caution]  
    > <P>You must set the <strong>ImageLocation</strong> before entering a value in this property.</P>
    
    </td>
    </tr>
    <tr class="even">
    <td><p><strong>Primary</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ShowShortCut</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Text</strong></p></td>
    <td><p><strong>Export to Excel</strong></p></td>
    </tr>
    </tbody>
    </table>


### To add a menu item button to the Attachments button group

1.  Right-click the **Attachments** button group, click **New Control**, and then click **MenuItemButton**. A control named **MenuItemButton** is added to the button group.

2.  Click the new button to display the control properties in the **Properties** window. Set the specified values for the following button properties.
    
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
    <td><p><strong>Big</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ButtonDisplay</strong></p></td>
    <td><p><strong>Text &amp; Image above</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ImageLocation</strong></p></td>
    <td><p><strong>EmbeddedResources</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MenuItemName</strong></p></td>
    <td><p><strong>DocuView</strong></p>
    
    > [!note]  
    > <P>When this button is clicked, the document handling form opens.</P>
    
    </td>
    </tr>
    <tr class="odd">
    <td><p><strong>MultiSelect</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>AttachmentsView</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>NormalImage</strong></p></td>
    <td><p><strong>10442</strong></p>
    
    > [!caution]  
    > <P>You must set the <strong>ImageLocation</strong> before entering a value in this property.</P>
    
    </td>
    </tr>
    <tr class="even">
    <td><p><strong>Primary</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ShowShortCut</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Text</strong></p></td>
    <td><p><strong>Attachments</strong></p></td>
    </tr>
    </tbody>
    </table>


3.  Right-click the form and then click **Save.**

To view the list page with the action pane, right-click the form, and then click **Open**. The list page opens and you can see the action pane and data grid you added to the form.


> [!NOTE]
> <P>When you open the form, you will see that the list page automatically includes the default filter pane. For more information about the filter pane, see <A href="how-to-add-controls-to-the-filter-pane.md">How to: Add Controls to the Filter Pane</A>.</P>



## Next Steps

After you add buttons to the action pane, you can specify the value of the **DefaultAction** property of the grid control. Identify the button that represents the action that you want performed when a row in the list is double-clicked.

To add more tabs, button groups, and buttons to the action pane, you use the same techniques that you used to create the **General** tab. For information about how to add a preview pane to a list page, see [How to: Add a Preview Pane to a List Page](how-to-add-a-preview-pane-to-a-list-page.md).

## See also

[List Page Overview](list-page-overview.md)

[Action Pane Buttons](action-pane-buttons.md)

[How to: Add a List Page to the Navigation Pane](how-to-add-a-list-page-to-the-navigation-pane.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

