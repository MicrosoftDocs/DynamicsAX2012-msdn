---
title: Area Page User Experience Guidelines
TOCTitle: Area Page
ms:assetid: 46ade758-b50b-455e-8743-6808dfffc852
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886591(v=AX.60)
ms:contentKeyID: 35267955
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Area Page User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An *area page* is a Microsoft Dynamics AX navigation page that displays menu items that link to list pages, content pages, forms, reports, classes, jobs, and queries. The area page is part of the navigation layer of the Microsoft Dynamics AX user experience.

Example of an area page

  
![Example of area page](images/Gg886591.Client_AreaPage_01(AX.60).png "Example of area page")Example of an area page

The area page is a landing page for users when they click an application module button in the Navigation Pane. Each application module of Microsoft Dynamics AX must have an area page.

## Overview

An area page consists of menus and menu items.

### Area page menus

The area page is comprised of a set of six top-level menus available to (but not required by) all application modules in Microsoft Dynamics AX.

These menus group the various submenus and menu item. In Microsoft Dynamics AX, the following menus are displayed for the area page:

  - **Common** – Displays the most commonly used menu items for an application module. Most menu items on this menu are designed for users to quickly find a record or group of records and then to perform an action against those records. Each list page for primary entities and primary forms that do not have list pages for an application module should be included on this menu.
    

    > [!NOTE]
    > <P>We recommend that you provide navigation to a list page within multiple application modules whenever that makes sense. For example, the <STRONG>Customers</STRONG> list page should be found in both the <STRONG>Accounts receivable</STRONG> application module and the <STRONG>Sales and marketing</STRONG> application module because accounts receivable users will look for customers in <STRONG>Accounts receivable</STRONG>, and sales people will look for customers in <STRONG>Sales and marketing</STRONG>.</P>

    
    Common menu for the “Accounts payable” application module
    
      
    ![Example of a Common menu](images/Gg886591.Client_AreaPage_02(AX.60).png "Example of a Common menu")Common menu for the “Accounts payable” application module

  - **Journals** – Displays menu items that provide access to forms that are used for interacting with journals. *Journal* is a standard accounting term that refers to the register that is used to record the financial consequences of business events in an accounting system. A journal details which transactions occurred and which accounts were affected.
    
    Journals menu for the “Accounts payable” application module
    
      
    ![Example of a Journals menu](images/Gg886591.Client_AreaPage_03(AX.60).png "Example of a Journals menu")Journals menu for the “Accounts payable” application module

  - **Inquiries** – Displays menu items that provide access to forms that are used for inquiry. An inquiry is designed to enable read-only access to information for search and analysis within the system so that a user does not have to generate a traditional report.
    

    > [!NOTE]
    > <P>Try to minimize the number of new inquiries that you create. Before creating an inquiry form, consider creating a list page or a secondary list page that displays the information. List pages provide more interactions options than an inquiry form does.</P>

    
    Inquiries menu for the “Accounts payable” application module
    
      
    ![Example of an Inquiries menu](images/Gg886591.Client_AreaPage_04(AX.60).png "Example of an Inquiries menu")Inquiries menu for the “Accounts payable” application module

  - **Reports** – Displays menu items that provide access to the reports for an application module.
    
    Reports menu for the “Accounts payable” application module
    
      
    ![Example of a Reports menu](images/Gg886591.Client_AreaPage_05(AX.60).png "Example of a Reports menu")Reports menu for the “Accounts payable” application module

  - **Periodic** – Displays menu items that provide access to forms that are usually used periodically, often for bulk updates to a set of records. They appear on the **Periodic** menu because they are usually performed at regular intervals of time, such as monthly, quarterly, or yearly.
    

    > [!NOTE]
    > <P>Try to minimize the number of new periodic forms that you create. If a list page exists for an entity, add the periodic task as an action on the list page instead of as a separate form.</P>

    
    Periodic menu for the “Accounts payable” application module
    
      
    ![Example of a Periodic menu](images/Gg886591.Client_AreaPage_06(AX.60).png "Example of a Periodic menu")Periodic menu for the “Accounts payable” application module

  - **Setup** – Displays menu items that provide access to forms that are used to maintain the general setup of features related to an application module.
    
    Setup menu for the “Accounts payable” application module
    
      
    ![Example of a Setup menu](images/Gg886591.Client_AreaPage_07(AX.60).png "Example of a Setup menu")Setup menu for the “Accounts payable” application module

### Area page menu items

The items that appear in the Navigation Pane and on the area page are generated from the menu items in the Microsoft Dynamics AX Application Object Tree (AOT). These items operate as navigation links that users use to access the features in the application module.

The menu item is displayed as a link to the associated item in the AOT. Clicking a menu item opens the list page, the form, or the report. A list page opens inline in the main application window. A form or a report opens in a separate task window over the area page.

## Guidelines

The following sections describe the guidelines for an area page.

### Grouping

  - Because a menu may have many menu items, the menu items often have to be grouped in submenus.

  - If there are more than 3 related menu items on a menu with more than 10 menu items, it is best to group them in a submenu.

  - Submenus should be of the same approximate granularity. When a user looks across groups, menus should have the same level of detail. Menu names should reflect the contents on the menu.
    
    If the forms contained in the group are closely related, consider building a single form by using the [Table of Contents User Experience Guidelines](table-of-contents-user-experience-guidelines.md) (TOC) pattern that encapsulates all of the functionality. It is easier for users to understand a single concept in the navigation and easier for them to swap between the contents of a TOC than to move between entries in the navigation.

  - Submenus may be required for complex sets of menu items. We recommend that you do not go more than two levels deep with submenus.

### Ordering

  - Menu items should be arranged in a business process or dependency order. For example, *Sales quotations* should precede *Sales orders* in the *Sales and marketing*   **Common** area.

  - Items in the **Setup** area should be arranged in dependency order. For example, *Category groups* should precede *Categories*.

  - Menus items should be ordered consistently between the different menus.

  - If there is no obvious process or dependency order, menus and menu items should be arranged by frequency of use.

### Country/region specific menu items

  - Menu items that are specific to a country or region should be grouped under a submenu with the name of the country or region. The name of the menu item should not include the name of the country or region unless it cannot be included in a submenu. In this case, the name of the country or region can be added in parentheses.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p><strong>Correct examples</strong></p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Tax reports (Spain)</p></td>
    </tr>
    <tr class="even">
    <td><p>Sales tax by customer (Belgium)</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p><strong>Incorrect examples</strong></p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Spanish tax reports</p></td>
    </tr>
    <tr class="even">
    <td><p>Belgian sales tax by customer</p></td>
    </tr>
    <tr class="odd">
    <td><p>Withholding tax - Thailand</p></td>
    </tr>
    </tbody>
    </table>


## Labels and text

This section contains labels and text guidelines for menus and tooltips that appear on an area page.

### Menu labels and text

**General guidelines**

  - The names of menu items should be concise while offering enough information to allow users to understand what will happen when they click the link. Proper naming will make it easy for users to choose between the multiple items.
    
    In general, menu names should be plural nouns and aligned to the name of the form or report to which they provide access. A slash mark (/) should not be included in the name of submenu or menu items to indicate a choice such as *and/or*. The appropriate conjunction should be used instead: *and* or *or*. Exceptions to this guideline include the following terms: *client/server*, *read/write*, *country/region*, and *ZIP/postal code*.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Price and discount groups</p></td>
    </tr>
    <tr class="even">
    <td><p>Calculation and approval statuses</p></td>
    </tr>
    <tr class="odd">
    <td><p>Requests for quotes by item or vendor</p></td>
    </tr>
    </tbody>
    </table>


  - Punctuation should not be included in the name of a submenu or menu item.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Incorrect examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Consolidation – import</p></td>
    </tr>
    <tr class="even">
    <td><p>Recalculation, actual costs</p></td>
    </tr>
    <tr class="odd">
    <td><p>Journal names: Inventory</p></td>
    </tr>
    </tbody>
    </table>


  - All other UI text guidelines for casing, font, and other typographical aspects apply.

**Common and Journals menus**

  - Submenu and menu item names should be plural nouns.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Unconfirmed purchase orders</p></td>
    </tr>
    <tr class="even">
    <td><p>Invoice registrations</p></td>
    </tr>
    <tr class="odd">
    <td><p>Payment transfers</p></td>
    </tr>
    <tr class="even">
    <td><p>Picking lists</p></td>
    </tr>
    </tbody>
    </table>


  - If singular nouns appear as submenu or item names, they should be recast as tasks. For example, *Cleanup* should be recast as *Cleanup tasks*; and *Conversion* should be recast as *Conversion* tasks.

**Periodic menu**

  - Submenu and menu item names should be nouns.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Ledger period recalculation</p></td>
    </tr>
    <tr class="even">
    <td><p>Fixed asset reclassification</p></td>
    </tr>
    <tr class="odd">
    <td><p>Online consolidation</p></td>
    </tr>
    </tbody>
    </table>


  - If verb phrases appear as submenu or item names, they should be recast. For example, *Create prenotes* should be recast as *Prenote creation*.

**Inquiries menu**

  - Submenu and menu item names should be plural nouns.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Promissory notes</p></td>
    </tr>
    <tr class="even">
    <td><p>Raw registrations</p></td>
    </tr>
    <tr class="odd">
    <td><p>Absence statistics</p></td>
    </tr>
    </tbody>
    </table>


  - If singular nouns appear as submenu or item names, they should be recast. For example, *Workflow history* should be recast as *Workflow histories*.

**Reports menu**

  - Submenu and menu item names should be plural nouns.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Campaigns</p></td>
    </tr>
    <tr class="even">
    <td><p>Greenhouse gas emissions</p></td>
    </tr>
    <tr class="odd">
    <td><p>Vendor requests</p></td>
    </tr>
    </tbody>
    </table>


  - If singular nouns appear as submenu or item names, they should be recast. For example, *Workflow tracking* should be recast as *Initiated workflows*; *Alert tracking* should be recast as *Notifications*.

**Setup menu**

  - Submenu and menu item names should be nouns.

  - The plural form of the noun should be used for submenus and for menu items that open forms for maintaining reference data or master data. If you are setting up a singular component or process, use the singular form of the noun.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Organizations</p></td>
    </tr>
    <tr class="even">
    <td><p>Data crawler</p></td>
    </tr>
    <tr class="odd">
    <td><p>Vendor management</p></td>
    </tr>
    </tbody>
    </table>


  - The submenu and menu item names should not include the following words: *maintain*, *manage*, *setup*, *set up*.

### Tooltips labels and text

  - Tooltips should provide additional information for users to understand what will happen when they click a menu item.

  - In general, tooltips should be sentences in the imperative mood (the implicit subject is *you*).

  - A tooltip should not include end punctuation.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Open balance journals</p></td>
    </tr>
    <tr class="even">
    <td><p>Generate report on open purchase orders</p></td>
    </tr>
    <tr class="odd">
    <td><p>View list of opportunities</p></td>
    </tr>
    <tr class="even">
    <td><p>Set up product dimension groups</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Incorrect examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Opens the balance journals.</p></td>
    </tr>
    <tr class="even">
    <td><p>Shows a summary of the open purchase orders</p></td>
    </tr>
    <tr class="odd">
    <td><p>Create and maintain a list of opportunities.</p></td>
    </tr>
    <tr class="even">
    <td><p>Configuration of product dimension groups</p></td>
    </tr>
    </tbody>
    </table>


  - The object of the predicate should be a plural noun describing the entity to which it provides access. Modifiers such as “the”, “a”, and “this” between the verb and the object should be avoided.

**Common and Journals menu**

  - The verb "Open" should be used with a plural noun representing the entity that is accessed for menu items that open a new form containing the entities. The verb phrase "Open a list of" should be used if the menu item navigates to a list page containing the entities.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Open purchase journals</p></td>
    </tr>
    <tr class="even">
    <td><p>Open list of invoice registrations</p></td>
    </tr>
    <tr class="odd">
    <td><p>Open list of payment transfers</p></td>
    </tr>
    <tr class="even">
    <td><p>Open picking lists</p></td>
    </tr>
    </tbody>
    </table>


**Periodic menu**

  - A verb phrase should be used that describes the periodic action to perform.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Recalculate payroll statistics for specified pay types</p></td>
    </tr>
    <tr class="even">
    <td><p>Consolidate balances</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Incorrect examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Open the payroll recalculation form</p></td>
    </tr>
    <tr class="even">
    <td><p>Allows the user to consolidate balances.</p></td>
    </tr>
    </tbody>
    </table>


**Inquiries menu**

  - The verb “View” should be used, along with the plural noun representing the entity that is accessed.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>View promissory notes</p></td>
    </tr>
    <tr class="even">
    <td><p>View absence statistics</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Incorrect example</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Shows the absence statistics</p></td>
    </tr>
    </tbody>
    </table>


**Reports menu**

  - The verb phrase “Generate a report on” should be used with the plural noun representing the entity that is the subject of the report. The term “print” should not be used because many reports will only be viewed on the screen.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct example</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Generate report on campaigns</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Incorrect examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Greenhouse gas emissions report</p></td>
    </tr>
    <tr class="even">
    <td><p>Print vendor requests</p></td>
    </tr>
    </tbody>
    </table>


  - In some cases, terms other than “report” more accurately describe the output, for example, “Generate bar codes” or “Generate inventory labels”.

**Setup menu**

  - The verb “Set up” should be used, along with the plural noun representing the entity that is configured or maintained.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Set up payroll categories</p></td>
    </tr>
    <tr class="even">
    <td><p>Set up user profiles</p></td>
    </tr>
    <tr class="odd">
    <td><p>Set up language codes</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Incorrect examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Create or update payroll categories</p></td>
    </tr>
    <tr class="even">
    <td><p>Setup of user profiles</p></td>
    </tr>
    <tr class="odd">
    <td><p>Language code setup</p></td>
    </tr>
    </tbody>
    </table>


  - The tooltip can also include the following words: *maintain, manage, setup, set up*.

