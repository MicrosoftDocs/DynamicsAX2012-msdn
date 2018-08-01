---
title: Multiselection Design Pattern
TOCTitle: Multiselection
ms:assetid: 1f48b7c9-e9fb-49e6-a27f-ae79a0642458
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa557882(v=AX.60)
ms:contentKeyID: 35241499
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Multiselection Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Buttons and their underlying menu items must support multiselection in grids to the greatest possible extent. This programming pattern can be used to make functionality multiselection-enabled.

## Situation

The user has selected several records in a grid, and you want to make it possible to process exactly the selected records.

## Solution

You must traverse the multiselected records, if any. If there is no multiselection, you must process only the current record.

## Implementation

The Form data source object contains methods to traverse the cached and potentially selected records in, typically, a grid on a form.

One option is to make a for loop that goes through the selected records, or just the current record, as shown in the following example.

## Example

The following code example shows items that could be found on a form with the xRefReferences data source.

    void clicked() 
    {
        xRefReferences xRefReferencesEdit;
        ;
        // Are there any marked records?
        for (xRefReferencesEdit = xRefReferences_ds.getFirst(1) 
            ? xRefReferences_ds.getFirst(1)  
            // If yes, get the first marked record,
            // otherwise, use the current record.
            : xRefReferences;               
     
            // Continue as long as there are records to work on.
            xRefReferencesEdit; 
     
            // Get the potential next marked record.
            xRefReferencesEdit = xRefReferences_ds.getNext())
        {
            // Do processing with xRefReferencesEdit.
            ...    
        } 
    }

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

