---
title: 'How to: Create a List Page Form'
TOCTitle: 'How to: Create a List Page Form'
ms:assetid: 3864127d-58b6-4368-b135-87c57595582f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc586969(v=AX.60)
ms:contentKeyID: 35242839
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a List Page Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To create a Microsoft Dynamics AX list page, you use the Application Object Tree (AOT) to create a list page interaction class and form that specify the behavior and structure of the list page. The following procedures describe how to create the class and form for a primary list page.

### To create the list page interaction class

1.  In the AOT, right-click the **Classes** node, and then click **New Class**. The **Classes** node expands and displays a new class.

2.  Right-click the new class, and then click **Properties**. In the **Properties** window, click **Name**, and then enter a unique name for the class.
    

    > [!IMPORTANT]
    > <P>You should match the name of the class to the name of the list page. In addition, you should append <STRONG>Interaction</STRONG> to the name of the class. For example, the list page interaction class for the customer list page is named <STRONG>CustTableListPageInteraction</STRONG>.</P>



3.  Expand the class node, and then double-click **classDeclaration**. The class opens in the Editor window.

4.  To modify the class declaration, click **classDeclaration**, and then add extends ListPageInteraction to the class declaration.
    
    The following code example declares an interaction class for a list page named RoomsListPage.
    ```X++
        public class RoomsListPageInteraction extends ListPageInteraction 
        {
        .. 
        }
    ```
5.  Click **Save** and then close the Editor window. If you view the properties for the class, the **Extends** property is now set to **ListPageInteraction**.

### To create the list page form

1.  In the AOT, right-click **Forms**, click **New Form from template**, and then click **ListPage**. The new list page form appears in a second AOT window.

2.  Right-click the new form, and then click **Properties**. In the **Properties** window, click **Name**, and then type a unique name for the list page.
    

    > [!IMPORTANT]
    > <P>To identify the form as a list page, always append <STRONG>ListPage</STRONG> to the form name. For example, the Facility Management sample contains a list page that displays room information. The form for the list page is named <STRONG>FCMRoomsListPage</STRONG>.</P>



3.  Verify that the **FormTemplate** property is set to **ListPage**.
    

    > [!NOTE]
    > <P>Setting the <STRONG>FormTemplate</STRONG> property to <STRONG>ListPage</STRONG> adds the <STRONG>InteractionClass</STRONG> property to the form.</P>



4.  Click **InteractionClass**, expand the drop down list, and then click the name of the class that you created earlier.
    
    For example, to specify the class for the **FCMRoomsListPage**, click the **RoomsListPageInteraction** class you created earlier.

5.  Verify the form includes an action pane, grid, and filter group control. Expand the form node, expand **Designs**, and then expand **Design**. You should see an action pane, filter group, and grid control.

6.  Save your changes by right-clicking the form, and then clicking **Save**.

After you create the form, you have to add a data source. For information about data sources, see [How to: Add a Data Source to a Primary List Page](how-to-add-a-data-source-to-a-primary-list-page.md).

## See also

[Form Overview](form-overview.md)

[Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md)

[Form Control Properties](form-control-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

