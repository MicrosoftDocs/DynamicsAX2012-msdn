---
title: Using COM to Open a Form from an Application
TOCTitle: Using COM to Open a Form from an Application
ms:assetid: 212064f3-47c1-4ee3-9c13-0f83d987e2f8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677283(v=AX.60)
ms:contentKeyID: 49384055
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using COM to Open a Form from an Application 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

When you install the Microsoft Dynamics AX client, AX32.exe registers as a COM server. Microsoft Component Object Model (COM) is a platform-independent, distributed, object-oriented system for creating binary software components that can interact. As a result, you can use the Dynamics AX COM server to open a specified form. For example, you can create a .NET application that uses the DynamicsAxApplication COM interface to open the customer list page form.

## Using the Dynamics AX COM Object

The Dynamics AX COM object represents a running instance of the Microsoft Dynamics AX client application. You will have a Dynamics AX COM object for each client workspace that is running on your computer. To use the Dynamics AX COM object, you use a COM interface that specifies the methods, properties, and enumerations for the COM object. In addition, the COM interface starts the client for you whenever a running COM object is not found.

In Microsoft Dynamics AX 2012 R2, you can use a moniker to specify a partition for the Dynamics AX COM object. A COM moniker is a name that uniquely identifies a COM object. A partition is a division of processing into logical or functional parts for an application. In Microsoft Dynamics AX 2012 R2, partitions are used to enable data isolation. For example, you might use partitions to represent independent subsidiaries for an organization. For information about how to specify a partition, see [How to: Specify the Partition for the Form](how-to-specify-the-partition-for-the-form.md).


> [!NOTE]
> <P>If you use the COM interface to start the COM object, the interface will use the default partition for the logged in user.</P>



The COM interface always connects to the first running instance of the Microsoft Dynamics AX client. The interface does not check that the COM object is associated with a specified partition. If you can view data in more than one partition, you have to verify that you are working with data from the targeted partition.

## Using the Dynamics AX Client Type Library

To provide access to the Dynamics AX COM object, AX32.exe includes a type library named **Dynamics Ax Client 1.0 Type Library**. A type library (.tlb) is a file that stores information about the properties and methods of a COM object.

You use the Dynamics AX Client Type Library when you want to use the Dynamics AX COM object from an application. For example, you want to open a form from an application built by using the Microsoft .NET Framework. The .NET application uses the type library to add an interop assembly to the project. The interop assembly enables you to use the interfaces associated with the COM object.

For each interface in the type library, the interop assembly defines .NET equivalents, or wrappers, for the COM properties and methods. When you call a method from an interop assembly, a .NET-to-COM translation is executed, and then control is passed to the COM component. When the COM object returns a result, a COM-to-.NET translation is executed. In addition, the COM result is checked, and an exception is thrown if there is an error. For information about how to add the type library to a .NET application, see [How to: Use COM to Open a Form](how-to-use-com-to-open-a-form.md).

### ![JJ677283.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677283.collapse_all(en-us,AX.60).gif")Using the DynamicsAxApplication Interface

DynamicsAxApplication is the interface you use to open a specified form. The following table shows the method that you use.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>OpenMenuItem</p></td>
<td><p>Opens a form. You use a menu item to identify the form. The COM object executes “open form” logic with the specified menu item.</p></td>
</tr>
</tbody>
</table>


For more information about the interfaces in the type library, see [Dynamics AX Client Type Library Reference](dynamics-ax-client-type-library-reference.md).

## Security

To use the Dynamics AX COM object, you must be logged in as an authenticated Microsoft Dynamics AX user. The implementation of the API assumes each menu item has an associated security key. If the menu item is found not to have a security key, the call to OpenMenuItem returns the HRESULT value E\_ACCESSDENIED.

## See also

[Partitions, Companies, and Data Isolation in Microsoft Dynamics AX](partitions-companies-and-data-isolation-in-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

