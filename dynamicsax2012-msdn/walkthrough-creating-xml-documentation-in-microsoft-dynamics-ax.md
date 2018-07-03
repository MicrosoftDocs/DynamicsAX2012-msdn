---
title: 'Walkthrough: Creating XML Documentation in Microsoft Dynamics AX'
TOCTitle: 'Walkthrough: Creating XML Documentation in Microsoft Dynamics AX'
ms:assetid: 0b7f9282-98ca-4fb5-b8a8-db86131bdc87
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc581979(v=AX.60)
ms:contentKeyID: 35240387
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating XML Documentation in Microsoft Dynamics AX 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can document classes, class methods, and table methods in X++ source code by using XML documentation. You can generate an XML file from this XML documentation.

This walkthrough illustrates the following tasks:

  - Creating a project

  - Creating a class

  - Creating a method

  - Adding documentation to the method

  - Adding documentation to the class

  - Creating XML files for the project

  - Creating XML files for the entire application

## Creating a Project

You can create XML documentation files for a project or for the entire application. In this procedure, you will create a project that contains the class and method for which you will create XML documentation.

### To create a project

1.  Open Microsoft Dynamics AX.

2.  Press CTRL+SHIFT+P to open the **Projects** window.

3.  In the **Projects** window, right-click the **Shared** node, point to **New**, and then click **Project**.
    

    > [!NOTE]
    > <P>The <STRONG>Shared</STRONG> node expands with a new project that has a name such as <STRONG>Project1</STRONG>.</P>



4.  Right-click **Project1**, select **Rename**, and then rename the class myProject.

## Creating a Class

Next, you will create a class.

### To create a class

1.  Open **myProject**.

2.  Right-click **myProject**, point to **New**, and then click **Class**.

3.  In the **Projects** window, right-click the **Shared** node, point to **New**, and then click **Project**.
    

    > [!NOTE]
    > <P>The <STRONG>myProject</STRONG> node expands with a new class that has a name such as <STRONG>Class1</STRONG>.</P>



4.  Right-click **Class1**, select **Rename**, and then rename the class Math.

## Creating a Method

In this procedure, you will create a method.

### To create a method

1.  Right-click **Math** and select **New Method**.

2.  In the Code Editor, change the method to the following code.
    ```X++  
        int add(int a, int b)
        {
            ;
            return a + b;
        }
    ```
3.  Save the method.

## Adding Documentation to the Method

Now you are ready to insert a header template into the method and write information between the XML tags.

### To add documentation to the method

1.  Click the **Script** button to access the **Scripts** shortcut menu, point to **Scripts**, point to **documentation**, and then click **HeaderTemplate**. XML tags will appear at the top of the code editor.

2.  Below the \<summary\> tag, type a description of the method, such as "Adds two integers."

3.  Below the \<param name="a"\> tag, type a description of the parameter, such as "The first integer to add." Add a similar description after the \<param name="b"\> tag.

4.  Below the \<returns\> tag, type a description of the return value, such as "The sum of a and b."
    

    > [!NOTE]
    > <P>The parameter and returns tags were inserted because the method has parameters and a return value.</P>



5.  Below the \<remarks\> tag, add additional optional information, such as "An integer is a positive or negative whole number or zero."

## Adding Documentation to the Class

In this procedure, you will insert a header template into the method and write information between the XML tags.

### To add documentation to the class

1.  Open the **Math** class.

2.  Click the **Script** button to access the **Scripts** shortcut menu, point to **Scripts**, point to **documentation**, and then click **HeaderTemplate**. Alternatively, with your cursor positioned on an empty line above the code, type ///. XML tags will appear at the top of the code editor.

3.  Below the \<summary\> tag, type a description of the class, such as "The Math class performs mathematical operations."

4.  Below the \<remarks\> tag, add optional information, such as "This class contains the add method."

## Creating XML Files for the Project

In this procedure, you will create an XML file that contains the documentation that you wrote in **myProject**, and an XML file that contains reflection information about the class and method in **myProject**.

### To create XML files for the project

1.  Create a folder in which you will create the XML documentation files. This procedure will reference a folder that has the path, C:\\XMLDoc.

2.  In the **Projects** window, right-click the **myProject** node, point to **Add-Ins**, and then click **Extract XML documentation**.

3.  Select the **Documentation** and **Reflection** check boxes.

4.  In the documentation **File name** field, type "C:\\XMLDoc\\documentation.xml".
    

    > [!NOTE]
    > <P>For security purposes, you may not be able to create XML files directly on the root directory.</P>



5.  In the reflection **File name** field, type "C:\\XMLDoc\\reflection.xml", and then click **Okay**. You can view the files at C:\\XMLDoc.

## Creating XML Files for the Entire Application

In this procedure, you will create an XML file that contains all of the documentation in the application, and an XML file that contains reflection information about all the objects in the application.


> [!NOTE]
> <P>The reflection file does not contain form information.</P>



### To create XML files for the whole application

1.  Create a folder in which you will create the XML documentation files. This procedure will reference a folder that has the path, C:\\XMLDoc.

2.  Open the command prompt.

3.  Type the following to create a documentation file for the whole application. Ax32.exe -startupcmd=xmldocumentation\_C:\\XMLDoc\\documentation.xml

4.  Type the following to create a reflection file for the whole application. Ax32.exe -startupcmd=xmlreflection\_C:\\XMLDoc\\reflection.xml
    

    > [!NOTE]
    > <P>When you use these commands, Microsoft Dynamics AX will start and create the XML files. It will close when it finishes.</P>



## See also

[XML Documentation](xml-documentation.md)

[XML Documentation Overview](xml-documentation-overview.md)

[How to: Add XML Documentation to X++ Source Code](how-to-add-xml-documentation-to-x-source-code.md)

[How to: Generate XML Documentation Files](how-to-generate-xml-documentation-files.md)

[Best Practices: XML Documentation](best-practices-xml-documentation.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

