---
title: Using Classes to Create a Dialog
TOCTitle: Using Classes to Create a Dialog
ms:assetid: deee29e9-26d6-4889-a93b-1f7b6c4ca29c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa877843(v=AX.60)
ms:contentKeyID: 35252087
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using Classes to Create a Dialog 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A dialog in Microsoft Dynamics AX is a simple form with a standardized layout, created by using the Dialog system class.

Dialogs should allow users to enter some simple values. Do not create complex dialogs—create forms instead.

Dialogs are non-modal. The dialog should not open a secondary window that requires user interaction. All user interaction should be carried out within the dialog.

## Dialog Methods

Following are some of the most commonly used methods in the Dialog class:

  - Use the addField method to add fields to the dialog. The addField method returns objects of the DialogField type.

  - Use the addGroup method to group related fields.

  - Use the addTabPage method to add tabbed pages.

  - Use the value method to set and get values in the dialog.

  - Use the run method to launch the dialog. When the user clicks **OK** or **Cancel**, the run method returns true or false, respectively.

## Dialog Classes

Dialog is the main class used to construct dialogs. DialogRunBase is an extension of the Dialog class that is used by the [RunBase framework](runbase-framework.md). The DialogControl class defines a single control in the dialog. DialogControl is extended by classes for the following control types:

  - DialogField

  - DialogGroup

  - DialogTabPage

  - DialogText

  - DialogWindow

## Example

![Example of a simple dialog](images/Aa877843.PATNDIAG(en-us,AX.60).gif "Example of a simple dialog")

The following code sample implements the dialog shown in the previous figure.
```X++  
    boolean myDialog(str FromChequeNum="1000", str NumOfCheque="300")
    {
        Dialog dialog = new Dialog("@SYS23133");
        DialogField dialogAccountId = dialog.addField(
            extendedTypeStr(BankAccount));
        DialogField dialogFromChequeNum = dialog.addField(
            extendedTypeStr(BankChequeStartNum),
            "@SYS4083");
        DialogField dialogNumOfCheque = dialog.addField(
            extendedTypeStr(BankChequeQty),
            "@SYS14578");
        ;
        dialogAccountId.Value("456");
        dialogAccountId.Active(false);
        dialogFromChequeNum.Value(FromChequeNum);
        dialogNumOfCheque.Value(NumOfCheque);
        if (dialog.run())
        {
            FromChequeNum = dialogFromChequeNum.Value();
            NumOfCheque = dialogNumOfCheque.Value();
            return true;
        }
        return false;
    }
```
  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

