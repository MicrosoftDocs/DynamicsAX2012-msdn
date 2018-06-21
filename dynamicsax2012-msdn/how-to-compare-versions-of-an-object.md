---
title: 'How to: Compare Versions of an Object'
TOCTitle: 'How to: Compare Versions of an Object'
ms:assetid: a4c49d51-138d-426f-aa07-b22067a72cf3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa850617(v=AX.60)
ms:contentKeyID: 35248383
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Compare Versions of an Object [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can compare two versions of the same application object by using the **Compare** tool. For example, you can compare a table with an earlier version of the same table provided that version control is enabled. Each version of the application object stored by the version control system is numbered. The **Compare** tool identifies the differences between two versions and provides action buttons to copy, move, or delete the differences. This topic describes how to compare two different versions of the same application object.


> [!NOTE]
> <P>You can also open the <STRONG>Compare</STRONG> tool form on the <STRONG>History</STRONG> form. For more information, see <A href="how-to-view-the-history-of-an-element.md">How to: View the History of an Element</A>.</P>



## Procedures

### To compare two versions of an application object

1.  In the Application Object Tree, right-click the application object that you want to compare, and then click **Compare**. The **Comparison** formopens.

2.  On the **Name & Location** tab, select the two versions that you want to compare.

3.  Click the **Advanced** tab, and then set the following options as needed.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Option</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Show differences only</strong></p></td>
    <td><p>Select this option to view only the differences. When this option is cleared, matching results are displayed as black check marks.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Suppress whitespace</strong></p></td>
    <td><p>Select this option to view differences in spaces in X++ code.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Case sensitive</strong></p></td>
    <td><p>Select this option to view upper and lowercase differences. By using this option, MyName and Myname would be displayed as a difference.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Show line numbers</strong></p></td>
    <td><p>Select this option to enable line numbers in X++ code.</p></td>
    </tr>
    </tbody>
    </table>


4.  Click **Compare** to begin the version compare.

The differences between the versions are displayed in the results window on the **Comparison** form. For more information about the results, see [Compare Tool](compare-tool.md).

## See also

[Version Control System](version-control-system.md)

[How to: Roll Back to a Previous Version of an Element](how-to-roll-back-to-a-previous-version-of-an-element.md)

[How to: View the History of an Element](how-to-view-the-history-of-an-element.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

