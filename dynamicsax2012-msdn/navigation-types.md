---
title: Navigation Types
TOCTitle: Navigation Types
ms:assetid: 79f5df06-c637-45b0-92e8-6d6103e3aa1e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886599(v=AX.60)
ms:contentKeyID: 35267963
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Navigation Types [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic contains design concepts and recommendations for the various types of navigation available to users in Microsoft Dynamics AX 2012.

## Design concepts

Microsoft Dynamics AX 2012 applications developed for a specific user role should be designed around the assumption that users are performing concrete business tasks repeatedly. To best support users, the navigation layer should provide standardized designs and stable locations.

The standard navigation window presents the user with a module navigation control in the left pane, which will often be familiar from Microsoft Outlook®, and an address bar with forward and back buttons. Also, for this release, forms are created as independent windows that can leave the boundary of the Microsoft Dynamics AX navigation window.

The benefits of the navigational model include:

  - Similarity to Outlook.
    
    From Outlook, we have adopted the idea of having the primary navigation pane on the left side of the window and having lists and a preview pane on the right side of the window. We have also adopted the idea of performing tasks in a separate window.

  - Reduced window management.
    
    Our design encourages you to show content through a progressive set of links to reduce window management issues.
    
      - Users can easily switch focus and get back to where they were in the application by using the back button.
    
      - Users can easily go to a higher level in the system by using the breadcrumb bar. (For example, a user could use the breadcrumb bar to navigate from the Customers area to the overall Sales department.)

  - Better user focus on key tasks.
    
    By identifying key tasks, designs should help users focus on a single activity, such as managing customers.

  - Easier ad hoc data comparison.
    
    Allowing users to view data in a form outside of the frame enables them to more easily compare data side-by-side with data in other applications.

## Guidelines

The navigation layer of an application should present all of the navigation, data, and tasks in a single window. The navigation layer includes the following elements:

  - Links on application pages, such as Role Center, area, and list pages and activity centers.

  - The Navigation Pane.

  - The Address bar.

### Application pages

The content area of application pages can contain links to forms, wizards, and other pages. Every application page also should include a Navigation Pane on the left side and an Address Bar at the top, as shown in the following images.

Role Center page

  
![Role Center page](images/Gg886599.client-nav-types-02(AX.60).png "Role Center page")Role Center page

Area page

  
![Area page](images/Gg886599.client-nav-types-03a(AX.60).png "Area page")Area page

List page

  
![List page](images/Gg886599.client-nav-types-03b(AX.60).png "List page")List page

### Navigation Pane

The Navigation Pane is the primary navigation control. It is displayed on the left side of the application window. The Navigation Pane is divided into three areas. From top to bottom, the areas are:

  - **Favorites.** These are user-defined and can be selected at the top of the pane.

  - **Places.** These are pages or forms available within the selected module.

  - **Application modules.** These can be selected at the bottom of the pane.

Navigation Pane with Accounts receivable module selected

  
![Navigation Pane](images/Gg886599.client-nav-types-04(AX.60).png "Navigation Pane")Navigation Pane with Accounts receivable module selected

The Navigation Pane displays user favorites and links that are specific to the selected module.

**Favorites**

The My Favorites section, which contains links defined by the user, is located at the top of the Navigation Pane. The user can show or hide this section by clicking **File \> View \> Show Favorites in Navigation Pane**. The favorites should not change when a new module is selected.

**Places**

This section should display links to the selected module's area page, primary and secondary list pages, and Directory views:

  - **Area page.** Each module (for example, Accounts receivable) should have one area page. Selecting the Area page menu item in the Navigation Pane should cause area page content to be displayed in the application window content pane. The area page should contain all the content of the module grouped into areas.

  - **Common.** The most commonly used menu items for an application module should be listed in the Common section. Most Common menu items should be designed to quickly find a record or group of records and then to perform an action against those records. The Common menu should include all list pages for primary entities as well as all primary forms
    
      - A link for a **primary list page** (unfiltered list page) should be placed at the first level of the places section. Selecting a list page menu item in the navigation Pane should cause a list page to be displayed in the content pane of the application window.
    
      - A link for a **secondary list page** (filtered list page) should appear at the second level of the Places section. A secondary list page has a filter applied to it, which makes it more specific than the primary list page. Selecting a secondary list page menu item in the Navigation Pane should cause a secondary list page to be displayed in the content pane of the application window. The Role Center may have a Cue for this kind of list page.

  - **Journals.** Journal is a standard accounting term referring to the register that is used to record the financial consequences of business events in an accounting system. A journal details which transactions occurred and which accounts were affected. Menu items should provide access to forms for interacting with journals.

  - **Inquiries.** An inquiry should be designed to enable search and analysis and read-only access to information without generating a traditional report. This menu should provide access to forms used for an inquiry.

  - **Reports.** Menu items for accessing the reports for this application module should be listed in this menu.

  - **Periodic.** This section should display menu items for forms that are typically used periodically—monthly, quarterly, and so on—often for bulk updates to a set of records.

  - **Setup.** This section should display links to the forms that are used to maintain the general setup of features related to the selected application module.

**Application modules**

In Microsoft Dynamics AX, application modules are the top-level containers for navigation. Names of application modules should be based on industry-standard Enterprise Resource Planning (ERP) taxonomy. In addition to application modules for business-related functions (like Accounts Payable or Cost Accounting) there should be three product-wide application modules: Home, Organization administration, and System administration.

The **Home** application module should provide menu items pertinent to general application users for features that are not tied to a specific application module. Clicking the Home module button should display the logged-on user’s Role Center (if installed) as well as a link to the Home area page. If Role Centers have not been installed, clicking the Home module button should display the Home area page.

The **Organization administration** area page should be reserved for menu items that cross the application modules in Microsoft Dynamics AX and are related to business functionality. This application module should be used for menu items for business process-related features. Conversely, links associated with the support and operation of the ERP system software should be placed in the System administration area page.


> [!NOTE]
> <P>The Organization administration module in Microsoft Dynamics AX 2012 contains functionality that was in the Basic and Administration modules in earlier releases of Microsoft Dynamics AX.</P>



The **System administration** application module is reserved for product-wide menu items that directly support the operation and function of the ERP software and servers. This area page should be used for list pages, forms, and setup and configuration menu items for software system-related features. Conversely, links associated with the support and operation of the business applications should be placed in the Organization administration area page.


> [!NOTE]
> <P>The System administration module contains functionality that was in the Basic and Administration modules in earlier releases of Microsoft Dynamics AX. The Basic and Administration modules have been removed from the product.</P>



**Choosing a module for menu items**

You should place menu items in modules based on their location in the standard ERP taxonomy and based on the roles of the users who require access to them. For example, if your menu item should be available to all users of the system, consider placing it in the Home module. If your menu item is primarily used by IT personnel, consider placing it in the **System administration** module. If your menu item is primarily accessed by accounts payable clerks, consider placing it in the **Accounts payable** module. You should not choose menu item placement based on factors like database schema (shared table versus company-specific tables) as these factors have little relevance to users.

Menu items may be duplicated (referenced multiple times) if they are relevant within multiple modules and roles. For example, the Categories menu item is used in both the **Sales and marketing** application module as well as the **Sourcing and Procurement** application module. If a menu item is relevant across more than three application modules, it should be considered as a candidate for the **Home** or **Organization administration** application modules.

### Address bar

![Address bar](images/Gg886599.client-nav-types-06(AX.60).png "Address bar")

The Address bar is composed of travel buttons (back, forward, and history) and a breadcrumb bar. The breadcrumb bar is located to the right of the Forward and Back buttons.

The **Back** button takes the user back to the page that was previously displayed in the content pane of the application window. The **Forward** button takes the user to the next page. A previous page will exist only if the user has navigated to the current page from another page. A next page will exist only if the user has clicked the Back button. If the user cannot go back or forward, the relevant button is disabled and is colored grey. To the right of the Forward and Back buttons is a history button, displayed as a small downward-pointing triangle. Clicking the history button displays a drop-down menu that lists the user’s navigation history.

The breadcrumb bar shows the path that the user has taken to the current page. Text strings in the path are separated by small right-pointing triangles that act as navigation buttons. Clicking one of these triangles displays a menu listing pages associated with path. For example, in the preceding image, clicking the triangle button following **Basic** would display a list of pages in the Basic module; pages in the list would be at the same level in the navigation structure as the Employees page.

