---
title: 'How to: Enable and Disable an Action Pane Button on a List Page'
TOCTitle: 'How to: Enable and Disable an Action Pane Button on a List Page'
ms:assetid: 4ec9cb4b-69fb-49d6-a30a-f9d2d1b93d9f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc570334(v=AX.60)
ms:contentKeyID: 35243473
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Enable and Disable an Action Pane Button on a List Page 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The only buttons in the action pane that should be enabled are those that perform valid actions for the current selection in the list. Buttons that cannot perform an action must appear in a disabled state. When the user changes the selection in the list, the enabled and disabled state of each button must be updated based on the new selection.

For example, you can use the **Multiselect** property to enable and disable an action pane button that performs an action on a single record. In some cases, the criteria for enabling and disabling an action pane button may be more complex, and must be done with code. The following procedure shows how to add code that enables and disables action pane buttons based on the selection in the list.

### To enable or disable an action pane button

1.  In the AOT, expand **Forms** and find the form for the list page where the action pane button appears. Use the **InteractionClass** property of the form to get the name of the interaction class for the list page.

2.  Expand **Designs**, expand **Design**, and then expand the **Action Pane**. Get the name of each action pane button that you want to enable or disable based on the list selection.

3.  Expand **Classes**, right-click the interaction class for the list page, click **Override Method**, and then click **selectionChanged**. The **Editor** window opens and displays the **selectionChanged** method.
    

    > [!TIP]
    > <P>If you have to enable and disable several controls in the <STRONG>selectionChanged</STRONG> method, the code in the method can become difficult to implement and maintain. In this situation, you might want to add new methods to the list page interaction class that enable or disable specified action pane button controls. You could then use the <STRONG>selectionChanged</STRONG> method to call these methods.</P>



4.  Use the list page **activeRecord** method to get a reference to the current record in the list page grid. To use the method, you have to supply the name of the data source for the list page.
    
    The following code example shows how to reference the current record in a grid that shows customer records. Notice the use of the **queryDataSourceStr** function to specify the name of the data source. In the example, **CustTableListPage** is the name of the query and **CustTable** is the data source of that query.
    
        Public void selectionChanged()
        {
            CustTable custTableCurrent = this.listPage().activeRecord(queryDataSourceStr(CustTableListPage, CustTable));
            
            super(); 
        }

5.  Add the criteria that you use to enable or disable the action pane button.
    
    For example, you have a button in the action pane of a customer list page that you use to assign a credit limit to a customer. If the customer already has a credit limit, you want that button to appear as a disabled button. If the customer does not have a credit limit, you want that button to appear as an enabled button.

6.  Use the **actionPaneControlEnabled** method of the list page to enable or disable the button. To use the method, you specify the name of the button control and whether to enable or disable the control.
    
    The following code example shows how to enable or disable a specified action pane button. Notice the use of the **formControlStr** function to get the name of the button control. In the example, **CustTableListPage** is the name of the form and **SetCreditMax** is the name of action pane button.
    
        Public void selectionChanged()
        {
            CustTable custTableCurrent = this.listPage().activeRecord(queryDataSourceStr(CustTableListPage, CustTable));
            
            super();
            
            if(custTableCurrent.CreditMax > 0)
            {
                this.listPage().actionPaneControlEnabled(formControlStr(CustTableListPage, SetCreditMax), false);
                
            }
            else
            {
                this.listPage().actionPaneControlEnabled(formControlStr(CustTableListPage, SetCreditMax), true);
                
            }
        }

7.  In the **Editor** window, click **Compile**. Close the **Editor** window.

## See also

[List Page Overview](list-page-overview.md)

[Action Pane Button Overview](action-pane-button-overview.md)

[How to: Create an Action Pane Button](how-to-create-an-action-pane-button.md)

[Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

