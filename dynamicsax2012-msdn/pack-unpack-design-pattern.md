---
title: Pack-Unpack Design Pattern
TOCTitle: Pack-Unpack
ms:assetid: e2db506c-4cae-4178-8ca6-2ca45158db3c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa879675(v=AX.60)
ms:contentKeyID: 35253124
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Pack-Unpack Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use the pack-unpack pattern to save and/or store the state of an object, and then later re-instantiate the same object.

## Situation

An object has a particular state. You want to work with the same object at a later time or another place (such as on another tier).

## Solution

Make it possible to save the state of the object in a form that can be persistently saved or transported to another tier. Moreover, make it possible to reinstantiate the object.

For Table objects (records), this is straightforward because they are enabled for persistence and are automatically transported between client and server.

For class objects, create a pack method to read the state of the object and return it in a container suitable for saving or transporting between tiers. Reading the state of the object implies collecting the value of all its members. If the members are tables (records, cursors, temporary tables) or classes, it must also be possible to read their state.

Likewise, create an unpack method that takes the packed state and reinitializes an object with it. Construct the object before creating an unpack method.

You can also create a static create method that instantiates a new object. Initialize the new object with the packed state information, and return it ready for use.

## Implementation

To implement the pack-unpack pattern, create the following methods.

### ![Aa879675.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa879675.collapse_all(en-us,AX.60).gif")public container pack()

Returns the state of the object as a container.

According to the [Persistent Data Storage Design Pattern](persistent-data-storage-design-pattern.md), the first entry is a version number that describes the version of the saved structure.

Example:

    container pack() 
    {
        return [#CurrentVersion,#CurrentList]; 
    }

Where the macros are defined in the classDeclaration:

    public class InventAdj extends RunBaseBatch 
    {
        InventClosing inventClosing;
        #DEFINE.CurrentVersion(1)
        #LOCALMACRO.CurrentList
            InventClosing
        #ENDMACRO 
    }

### ![Aa879675.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa879675.collapse_all(en-us,AX.60).gif")public boolean unpack(container \_packedObject)

The unpack method takes the saved state of the object and reinitializes the object with it. It reinitializes the object members according to the values in the container, taking the supplied version number into account.

The method can return a Boolean that signals the result of the initialization process.

The object should be only instantiated before a call is made to the unpack method.

Example:

    public boolean unpack(container _packedClass) 
    {
        int version = conPeek(_packedClass,1);
        
        switch (version)    
       {        
            case #CurrentVersion:
                [version,#CurrentList] = _packedClass;
                break;
            default:
                return false;
        }
        return true;
    }

### ![Aa879675.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa879675.collapse_all(en-us,AX.60).gif")public void new()

The constructor (the new method) of the object is expected to take no parameters. It should be possible to instantiate the object without knowing anything about it except its class type, and then reinitialize it by using the unpack method.

A typical example would be to not have an explicitly defined new method, but to use the standard new method without parameters.

### ![Aa879675.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa879675.collapse_all(en-us,AX.60).gif")public static \<YourClass\> create(container \_packedObject)

You can also create a create method that does the following:

  - Instantiates a new object (by calling the constructor)

  - Initializes it with the saved state of the object and reinitializes the object together with it (by calling the unpack method, which can then be set to private)

  - Returns the reinitialized object of your class

For example, you do this in the List::create system class method.

## Limitations

An object cannot be packed unless all the members it contains can be packed.

If objects contain table or class members, you must be able to pack these members and to return them to the same state when unpacked.

A reinstantiated object is not the same object as the one that was saved. It is just an object of the same class whose members contain the same information.

## Related Patterns

[Persistent Data Storage Design Pattern](persistent-data-storage-design-pattern.md)

## Known Uses

  - All RunBaseBatch descendants. The Batch system uses the unpacking option.

  - QueryRun

  - Microsoft Dynamics AX collection classes (formerly called foundation classes)

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

[Collection Classes in Microsoft Dynamics AX](collection-classes-in-microsoft-dynamics-ax.md)

[SysPackable Interface](https://msdn.microsoft.com/en-us/library/gg963713\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

