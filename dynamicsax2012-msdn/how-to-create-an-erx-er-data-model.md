---
title: 'How to: Create an ERX ER Data Model'
TOCTitle: 'How to: Create an ERX ER Data Model'
ms:assetid: 8f408031-66f1-49c3-9fb0-5f12cd55e08b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc604309(v=AX.60)
ms:contentKeyID: 35246539
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create an ERX ER Data Model [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you select the ERX ER Data Model option for the Reverse Engineering tool, it generates an **.erx** file that can be used to create an entity relationship (ER) data model. After you generate an **.erx** file, you can import the file into a modeling tool, such as Microsoft Office Visio or CA ERwin Data Modeler, to create an ER data model.

The Reverse Engineering tool can create an **.erx** file from a private or shared project or from a perspective. Before you generate an **.erx** file, be sure that the project or perspective is already defined. For more information, see [How to: Create a MorphX Development Project](how-to-create-a-morphx-development-project.md).

The following procedures explain how to generate an **.erx** file and create an ER data model from an **.erx** file.

### To generate an .erx file

1.  Click **Tools** \> **Reverse Engineer**. The **Reverse Engineering** dialog box displays.
    

    > [!NOTE]
    > <P>An alternative way to display the <STRONG>Reverse Engineering</STRONG> dialog box is to right-click the project or perspective, point to <STRONG>Add-Ins</STRONG>, and then click <STRONG>Reverse Engineer</STRONG>.</P>



2.  In the dialog box, select **ERX ER Data Model**.

3.  Select the type of item that you want to generate a model for, **Private project**, **Shared project**, or **Perspective**, and then select the item from the drop-down menu.

4.  If you want to change the name or location of the file, click the folder icon, and then specify a name and location for the file.

5.  Click **OK**.

### To create an ER data model in Microsoft Office Visio

1.  Open Microsoft Office Visio.

2.  Click **File** \> **New** \> **Software and Database** (or **Database** if you are using Microsoft Office Visio 2003) \> **Database Model Diagram**.

3.  On the **Database** menu, point to **Import**, and then click **Import Erwin ERX file**.
    

    > [!NOTE]
    > <P>You must be using the <STRONG>Database Model Diagram</STRONG> template to access the <STRONG>Import</STRONG> command.</P>



4.  In the dialog box, click the **Browse** button, navigate to the location of the **.erx** file that you generated from the Reverse Engineering tool, select the file, and then click **OK**.
    

    > [!NOTE]
    > <P>Microsoft Office Visio imports the file and displays the progress in the <STRONG>Output</STRONG> window. The imported tables and views display in the <STRONG>Tables and Views</STRONG> window.</P>



5.  On the **Database** menu, point to **View**, and then click **Tables and Views**.

6.  Drag items from the **Table and Views** window onto the diagram surface.
    
    After you have added a table to the diagram, you can right-click the table in the diagram, and then click **Show Related Tables**. This will add all the related tables from the **Tables and Views** window that are not already in the diagram.

### To create an ER data model in CA ERwin Data Modeler

1.  Open CA ERwin Data Modeler.

2.  On the **File** menu, point to **Import**, and then click **From External Format**. Import the ERX ER data model file that you generated from the Reverse Engineering tool.
    

    > [!NOTE]
    > <P>When the diagram first displays, all items are displayed in a single stack. You must arrange the items in the diagram.</P>



## See also

[Reverse Engineering Tool Overview](reverse-engineering-tool-overview.md)

[How to: Create a Visio UML Data Model](how-to-create-a-visio-uml-data-model.md)

[How to: Create a Visio UML Object Model](how-to-create-a-visio-uml-object-model.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

