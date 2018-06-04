---
title: 'How to: Define an Extended Data Type as an Array'
TOCTitle: 'How to: Define an Extended Data Type as an Array'
ms:assetid: 7a410977-8d7f-4119-b388-d94d4dee7589
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa675074(v=AX.60)
ms:contentKeyID: 35246078
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Define an Extended Data Type as an Array 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create an extended data type in the Application Object Tree (AOT) that contains multiple elements. This enables you to store multiple data elements in a single field that is based on this extended data type.

To manage changes to AOT objects, a version control system is available. For more information, see [Version Control System](version-control-system.md).

A typical example is an extended data type for handling an address. Instead of defining three fields on your form to enter the address, you can define an extended data type with three elements (the first element exists by default), as shown in the following figure.

![Extended Data Types in the AOT](images/Aa675074.EDTsAsArrays(en-us,AX.60).gif "Extended Data Types in the AOT")

When you create a form based on a table that contains a field of the MyAddress type, MorphX automatically generates a field on your form for each element in the MyAddress definition. The definition of the MyAddress type above causes 3 fields to be generated on a form, called Address, Address1, and Address2.

You can make arrays of all categories of extended data types.

For a description of how to create your own extended data types, see [How to: Create an Extended Data Type](how-to-create-an-extended-data-type.md).

To see a full description of the properties you can modify for each category of extended data type, see [Extended Data Type Properties](https://msdn.microsoft.com/en-us/library/aa575242\(v=ax.60\)).

## Define an Extended Data Type as an Array

1.  Expand the relevant extended data type, and then locate the **Array Elements** node.

2.  Right-click the **Array Elements** node, and then choose **New Element** in the shortcut menu.

3.  Display the property sheet for the element, and then rename the element by changing the **Label** property.

4.  To specify the plural name of the element, use the **CollectionLabel** property.

5.  To display a help string when using the extended data type in a form, use the **HelpText** property.

6.  Save your modifications.

## See also

[How to: Create an Extended Data Type](how-to-create-an-extended-data-type.md)

[Extended Data Type Properties](https://msdn.microsoft.com/en-us/library/aa575242\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

