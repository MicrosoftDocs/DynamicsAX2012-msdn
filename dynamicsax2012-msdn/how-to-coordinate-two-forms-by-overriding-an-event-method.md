---
title: 'How to: Coordinate Two Forms by Overriding an Event Method'
TOCTitle: 'How to: Coordinate Two Forms by Overriding an Event Method'
ms:assetid: 902ecdc4-9238-490c-b19d-fc88502e51fb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa660749(v=AX.60)
ms:contentKeyID: 35247409
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Coordinate Two Forms by Overriding an Event Method [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how two forms that show related data can be coordinated when they are opened. For example, it is useful to have quick access to the related transaction data when looking at one particular bank account. The parent form displays the bank account, and the child form displays the transactions for that one account.

## Ways to Coordinate Two Forms

The most common way to achieve coordination between parent and child forms is by using dynamic links (not a dynamic-link library, or DLL). Dynamic links do not require code. Dynamic links are powerful and are straightforward to create, but they cannot be customized to meet nonstandard specifications.


> [!NOTE]
> <P>For more information about how to use dynamic links between forms, see <A href="how-to-link-two-forms-by-using-dynamic-links.md">How to: Link Two Forms by Using Dynamic Links</A>.</P>



This topic describes another way to coordinate parent and child forms. Forms can be coordinated by using code in an overridden method. This approach can provide more control over a form's functionality. For example, opening the child form can be restricted to particular parent values. Or, a list of fields can be used to coordinate the child form. However, this approach coordinates the forms only when the child form is opening. There is no ongoing coordination after both forms are opened. Also, this approach takes more effort to implement.

## Scenario

The following scenario describes how to add a button to a form, and then how to modify that button so that it opens a child form. The scenario uses two forms that are included with Microsoft Dynamics AX, the BankAccountTable form and the BankAccountTrans form.

1.  In the Application Object Tree (AOT), expand the **Forms** node, expand the **BankAccountTable** node, and then expand the **Designs** node.

2.  Right-click the **Design** node, click **New Control**, and then click **Button**.

3.  Expand the node for the new button, right-click **Methods**, point to **Override Method**, and then click **clicked**.

4.  Right-click the **clicked** node, and then click **Edit**.

5.  Copy the following example code, paste the code into the editor window, and then close it.

6.  Right-click the **BankAccountTable** node, and then click **Open**.

7.  In the grid control, click any row to give it focus.

8.  Click the newly added button. This opens the BankAccountTrans form.

The BankAccountTrans form is populated only with data associated to the one bank account value that is highlighted on the parent BankAccountTable form.

### ![Aa660749.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa660749.collapse_all(en-us,AX.60).gif")Code Example

Paste the following code into the overridden clicked method as shown in step 5 of the previous scenario.

    // The override of the clicked method on the button.
    void clicked()
    {
        Args myArgs;
        FormRun myFormRun;
        ;
        // Keep this call to super() when overriding the clicked method.
        super();
        myArgs = new Args();
    
        // Provide the name of the form to launch.
        myArgs.name("BankAccountTrans");
    
        // The BankAccountTable data source variable name
        // represents the currently selected item in the grid
        // on the parent form (and thus in the data source).
        myArgs.record(BankAccountTable);
    
        myFormRun = ClassFactory.formRunClass(myArgs);
    
        myFormRun.init();
        myFormRun.run();
        myFormRun.wait();
    }

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

