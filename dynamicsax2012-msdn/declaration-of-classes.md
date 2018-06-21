---
title: Declaration of Classes
TOCTitle: Declaration of Classes
ms:assetid: 55c72af3-cb14-4e5f-96cd-7d393b34445c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa631180(v=AX.60)
ms:contentKeyID: 35244331
ms.date: 10/11/2017
mtps_version: v=AX.60
---

# Declaration of Classes [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You create application classes by using the Application Object Tree (AOT).

## Creating a Class in the Application Object Tree

You create an application class by following these steps:

1.  In the AOT, locate the **Classes** node.

2.  Right-click the **Classes** node and click **New Class** in the shortcut menu.

3.  Expand the **Class1** node, so you can see the **classDeclaration** node.

4.  Right-click the **classDeclaration** node, and then click **View Code**. This displays the code **Editor** window.

In the **classDeclaration** code block, before the open brace {, the class declaration is decorated with the public modifier. All classes in Microsoft Dynamics AX are public. If you remove the public modifier, the system still treats the class as public.

Other modifiers can be specified on the class declaration, including final and extends.

## Creating Variables in a Class

All classes are public, but all member variables are implicitlyprotected. Even though all member variables are protected, you cannot decorate a member variable with the private or public keywords. All member variables belong only to object instances of the class. You cannot decorate a member variable with the static keyword. The following steps exemplify these rules:

1.  Right-click the **classDeclaration** node, and then click **View Code**.

2.  In the code **Editor** window for the classDeclaration, add the following declaration of a string variable on a line between the open and close braces {}:
    
    str firstName;

The X++ code for the classDeclaration now looks like the following.

    public class Class1
    {
        str firstName;
    }

You can provide access to a member variable by returning it from a simple instance public methods that get and set its value.

For information about how to write variable declarations, see [Declaration of Variables](declaration-of-variables.md).

## Creating Accessor Methods in a Class

In this section you add simple public methods that get and set the value of the member variable firstName.

## Add a Getter Accessor Method

Follow these steps to add a method that gets or returns the value of a member variable:

1.  Right-click the **Class1** node, and then click **New** \> **Method**.

2.  Rename the **method1** node to **getFirstName**.

3.  In the code **Editor** window, paste in the following X++ code for the method.
    
        public str getFirstName()
        {
            return firstName;
        }
    

    > [!NOTE]
    > <P>The this keyword cannot be used to reference member variables such as firstName.</P>



## Add a Setter Accessor Method

Follow these steps to add a method that sets the value of a member variable:

1.  Right-click the **Class1** node, and then click **New** \> **Method**.

2.  Rename the **method1** node to **setFirstName**.

3.  In the code **Editor** window, paste in the following X++ code for the method.
    
        public void setFirstName(str _firstName)
        {
            firstName = _firstName;
        }

## Test the Accessor Methods

The following X++ job tests the preceding getter and setter accessor methods.

    static void AccessorJob61(Args _args)
    {
        Class1 c1;
        c1 = new Class1(); // ‘new’ method is inherited from the Object class.
        c1.setFirstName("Isaac");
        print c1.getFirstName();
        pause;
    
    /*** Content of the Print window:
    Isaac
    ***/
    }

## See also

[Best Practices for Class Declarations](best-practices-for-class-declarations.md)

[Creating a Subclass](creating-a-subclass.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

