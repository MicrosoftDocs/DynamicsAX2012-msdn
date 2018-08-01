---
title: 'How to: Create a Visio UML Data Model'
TOCTitle: 'How to: Create a Visio UML Data Model'
ms:assetid: 051d60d2-8b99-4766-aa78-e4ffadd51c65
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa552178(v=AX.60)
ms:contentKeyID: 35240270
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Visio UML Data Model [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A UML data model provides a visual representation of the metadata for tables and their relationships and views. You can use the Reverse Engineering tool to create a UML data model from a private or shared project or from a perspective. The UML data model is created in Microsoft Office Visio 2010 (not 2013). Before you create a UML data model, be sure that the project or perspective is defined. For more information, see [How to: Create a MorphX Development Project](how-to-create-a-morphx-development-project.md). The following procedure explains how to use the Reverse Engineering tool to create a UML data model.


> [!NOTE]
> <P>&nbsp;&nbsp;To see method names correctly in the model, you must be running in debug mode before starting the Reverse Engineering tool. To set the debug mode, click <STRONG>Tools</STRONG> &gt; <STRONG>Options</STRONG>. Click the <STRONG>Development</STRONG> tab and select <STRONG>When Breakpoint</STRONG> for the <STRONG>Debug mode</STRONG> field.</P>



### To create a Visio UML data model

1.  Click **Tools** \> **Reverse Engineer**. The **Reverse Engineering** dialog box displays.
    

    > [!NOTE]
    > <P>An alternative way to display the <STRONG>Reverse Engineering</STRONG> dialog box is to right-click the project or perspective, point to <STRONG>Add-Ins</STRONG>, and then click <STRONG>Reverse Engineer</STRONG>.</P>



2.  In the dialog box, select **Visio UML Data Model**.

3.  Select the type of item that you want to generate a model for, **Private project**, **Shared project**, or **Perspective**, and then select the item from the drop-down menu.

4.  If you want to change the name or location of the file, click the folder icon, and then specify a name and location for the file.

5.  Click **OK**.
    
    After the data model is created, Visio opens and contains all the UML model elements along with a blank diagram. Use Model Explorer to drag model elements onto the diagram and format them. If the Model Explorer window is not already open, on the **UML** menu, point to **View**, and then click **Model Explorer**.

## See also

[Reverse Engineering Tool Overview](reverse-engineering-tool-overview.md)

[How to: Create a Visio UML Object Model](how-to-create-a-visio-uml-object-model.md)

[How to: Create an ERX ER Data Model](how-to-create-an-erx-er-data-model.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

