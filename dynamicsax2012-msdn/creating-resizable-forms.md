---
title: Creating Resizable Forms
TOCTitle: Creating Resizable Forms
ms:assetid: ec4251d9-a0d7-4948-96fa-c0c4e4febc6d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa884066(v=AX.60)
ms:contentKeyID: 35253235
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Creating Resizable Forms 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Forms can be resized by the user to display more information. Many forms in Microsoft Dynamics AX can be sized. A form should be resizable only if it will display additional information when it increases in size.

Forms that can be resized are identified by the lines in the form's lower-right corner.

To make a form resizable, set the Height property on the form **Design** node to Column height, and then set the Width property to Column width.

During form resizing, the controls on the form are resized to fit the new form size. Controls positioned in several columns share the additional height when a form increases in size. However, they do not share additional width—the last column gets any extra width.


> [!NOTE]
> <P>For controls to be resizable, the container control (Group, Tab, TabPage, and so on) that holds the controls must also be resizable. Properties cannot be changed for a control in a group that has the AutoDataGroup property set to Yes.</P>
> <P>For an illustration of the possible combinations of Height and Width settings on various controls, see the tutorial_Form_Arrange form.</P>



## See also

[Form Design Properties](form-design-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

