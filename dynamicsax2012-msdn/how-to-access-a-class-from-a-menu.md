---
title: 'How to: Access a Class from a Menu'
TOCTitle: 'How to: Access a Class from a Menu'
ms:assetid: e1b47729-ba70-4afb-8501-20e9f050a833
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa879186(v=AX.60)
ms:contentKeyID: 35253096
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Access a Class from a Menu 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can access a class from a menu by using an action menu item and a static main method.

## Access a Class from a Menu Item

1.  Add a static main method to a class in the Application Object Tree (AOT).

2.  Add the code you want to run, to the main method.
    
    In the following example, the main method displays a message on the screen using the print function.
    
        static void main(Args args)
        {
            print "Hello World";
            pause;
        }
    
    In the following example, the main method calls a class method that prints telephone numbers.
    
        static void main(Args args)
        {
            TelNumber telNumber;
            telNumber = new telNumber();
        
            telNumber.printTel();
        
        }
    
    For more information about the print function, see [Print Statements](print-statements.md).

3.  Create an action menu item that references the class you created in step 1. For more information, see [How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

