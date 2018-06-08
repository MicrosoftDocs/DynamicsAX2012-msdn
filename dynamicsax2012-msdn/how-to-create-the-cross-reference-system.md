---
title: 'How to: Create the Cross-Reference System'
TOCTitle: 'How to: Create the Cross-Reference System'
ms:assetid: de2669ec-be56-44d9-9bf0-6613dd0542bb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa877386(v=AX.60)
ms:contentKeyID: 35252084
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create the Cross-Reference System 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The cross-reference system is a collection of tools you use to create and view information about the relationships between objects in the AOT. For example, you can use the cross-reference system to identify objects that get used by a specified form and the objects that use that form. To create and maintain cross-reference information, you first have to complete the following tasks:

  - Configure the cross-reference system.

  - Update the cross-reference data.

The following sections describe how to complete these tasks. For information about how to view cross-reference data, see [Viewing the Cross-Reference System Information](viewing-the-cross-reference-system-information.md).

## To configure and run a manual update

The following steps describe how to configure the cross-reference system and then start a manual update.

1.  In the development workspace, open the **Tools** menu, and then click **Cross-reference** \> **Periodic** \> **Update**. The **Update cross-reference** window appears.

2.  Use the **Update cross-reference** window to configure the type of cross-reference data that you want to view. The following table describes the fields and controls you use to configure the cross-reference system:
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Field</p></th>
    <th><p>Control type</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Select</strong></p></td>
    <td><p>Button</p></td>
    <td><p>Opens the <strong>Inquiry</strong> window. You use this window to specify the date and time and the application model record types for the update.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Delete all</strong></p></td>
    <td><p>Check box</p></td>
    <td><p>Removes existing cross-reference information.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Selected</strong></p></td>
    <td><p>Check box</p></td>
    <td><p>Updates specified cross-reference information. To specify the types to cross-reference, click the <strong>Select</strong> button.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Update all</strong></p></td>
    <td><p>Check box</p></td>
    <td><p>Updates all cross-reference information.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Update data model</strong></p></td>
    <td><p>Check box</p></td>
    <td><p>Updates cross-reference information that is used by the Reverse Engineering tool.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Modified date and time</strong></p></td>
    <td><p>Text box</p></td>
    <td><p>Shows the date range for the update. To change the date range, click the <strong>Select</strong> button.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Record type</strong></p></td>
    <td><p>Text box</p></td>
    <td><p>Shows the record types from the application model that you want to update. To change record types, click the <strong>Select</strong> button.</p></td>
    </tr>
    </tbody>
    </table>


3.  Click **OK** to save your changes and start the update. Click **Cancel** to close the window without starting the update and remove any changes that you made.

## To configure automatic updates

To help maintain cross-reference data, you can configure the compiler to update the cross-reference system. The automated update occurs when you compile an object in the AOT.


> [!NOTE]
> <P>You can also manually update cross-reference data for a single object in the AOT. To complete the update, right-click the object, point to <STRONG>Add-Ins</STRONG>, point to <STRONG>Cross-reference</STRONG>, and then click <STRONG>Update</STRONG>. The cross-reference data for that object is updated.</P>



To configure automatic updates, follow these steps:

1.  In the development workspace, open the **Tools** menu, and then click **Options**.

2.  In the **Options** window, click the **Development** link on the left side of the window.

3.  In the **Set up option for the development workspace** form, click the **Compiler** button.

4.  In the **Compiler setup** window, select **Cross-reference**. The cross-reference check box specifies whether the compiler updates cross-reference data during compilation.
    
    For information about the other fields in the **Compiler setup** window, see [Compiler Setup Form](https://msdn.microsoft.com/en-us/library/aa617600\(v=ax.60\)).

5.  Click **OK** to save your changes and close the window.

## See also

[Cross-reference Tool](cross-reference-tool.md)

[How to: Schedule Cross-references Without a Batch](how-to-schedule-cross-references-without-a-batch.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

