---
title: 'Walkthrough: Creating a Secondary List Page'
TOCTitle: 'Walkthrough: Creating a Secondary List Page'
ms:assetid: 98d229b7-ec42-407f-a44a-a87be8178769
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc606758(v=AX.60)
ms:contentKeyID: 35247993
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating a Secondary List Page [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A secondary list page displays a subset of records from an existing primary list page. To demonstrate the steps to create a secondary list page, this walkthrough uses the Application Object Tree (AOT) to build a secondary list page based on the **Customers** list page. The secondary list page displays customers who have a credit limit.

This walkthrough illustrates the following tasks:

  - Creating a secondary list page query that is based on the data source of the primary list page.

  - Creating a menu item that associates a query with a list page form.

  - Adding a secondary list page to the Navigation Pane and to an area page.

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX.

  - A license file that includes access to the MorphX development environment.

  - Sample data in the CustTable database table of a company that you can access.

## Creating a Secondary List Page Query

In this section, you create a query that retrieves customers who have a credit limit. The query has to include all the data fields that the list page form requires. To make sure the query includes the necessary fields, you will create a copy of the original query, and add a range restriction to it.

### To create the query

1.  In the AOT, expand the **Queries** node, right-click **CustTableListPage**, and then click **Duplicate**. A new query named **CopyOfCustTableListPage** is added to the **Queries** node.
    

    > [!NOTE]
    > <P>You can also use a composite query to create the query for the secondary list page. You can add a range to the composite query that specifies the records to include in the secondary list page. For more information about how to create a composite query, see <A href="query-reuse-by-composite-queries.md">Query Reuse by Composite Queries</A>.</P>



2.  Click **CopyOfCustTableListPage**, and then display its properties. In the **Properties** window, enter **CustTableCreditLimitListPage** for the **Name** property.

3.  Expand the **CustTableCreditLimitListPage** query, expand **Data Sources**, expand **CustTable**, right-click **Ranges**, and then click **New Range**. A range node is added to the query.

4.  Click the range node, and then use the **Properties** window to specify values for the following properties.
    
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
    <td><p><strong>Field</strong></p></td>
    <td><p><strong>CreditMax</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Value</strong></p></td>
    <td><p><strong>&gt;0</strong></p></td>
    </tr>
    </tbody>
    </table>


5.  Right-click the **CustTableCreditLimitListPage** query, and then click **Save.**

## Creating a Menu Item

Next, create a menu item for the **CustTableCreditLimitListPage**. You use the menu item to associate the query with the **CustTableListPage** form.

### To create the menu item

1.  In the AOT, expand **Menu Items**, right-click **Display**, and then click **New Menu Item**. A new menu item is added to the **Display** node.

2.  Click the new menu item, and then use the **Properties** window to specify values for the following properties.
    
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
    <td><p><strong>Label</strong></p></td>
    <td><p><strong>Customers with Credit Limits</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>CustTableCreditLimitListPage</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Object</strong></p></td>
    <td><p><strong>CustTableListPage</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ObjectType</strong></p></td>
    <td><p><strong>Form</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Query</strong></p></td>
    <td><p><strong>CustTableCreditLimitListPage</strong></p></td>
    </tr>
    </tbody>
    </table>


3.  In the AOT, right-click the **CustTableCreditLimitListPage** menu item, and then click **Save.**

To view the secondary list page, right-click the menu item, and then click **Open**.

## Adding the Secondary List Page to the Navigation Pane

In this section, you add the **CustTableCreditLimitListPage** menu item to the **Customers** menu. This adds the menu item to the Navigation Pane and to the area page of the Accounts Receivable module.

### To add the menu item to the menu

1.  Expand the **Menus** node, expand **AccountsReceivable**, expand **Common**, right-click **Customers**, click **New**, and then click **Menu Item**. A menu item is added to the **Customers** node.

2.  Click the new menu item, and then use **Properties** window to specify values for the following properties.
    
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
    <td><p><strong>MenuItemName</strong></p></td>
    <td><p><strong>CustTableCreditLimitListPage</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>IsDisplayedInContentArea</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    </tbody>
    </table>


3.  Right-click the **AccountsReceivable** menu, and then click **Save**.

To view the new menu item in the Navigation Pane and area page, you have to restart the client application.

## See also

[List Page Overview](list-page-overview.md)

[How to: Add a List Page to the Navigation Pane](how-to-add-a-list-page-to-the-navigation-pane.md)

[Menus and Menu Items](menus-and-menu-items.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

