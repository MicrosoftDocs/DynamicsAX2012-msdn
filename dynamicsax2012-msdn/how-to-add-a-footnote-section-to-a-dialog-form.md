---
title: 'How to: Add a Footnote Section to a Dialog Form'
TOCTitle: 'How to: Add a Footnote Section to a Dialog Form'
ms:assetid: ade2f793-37c3-44ff-876f-c8b6bc0fd315
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh811915(v=AX.60)
ms:contentKeyID: 44089717
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Footnote Section to a Dialog Form [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can add an image and text message to the footnote area of a dialog or drop dialog form. The footnote area is the section of the form under the commit and cancel buttons. You use the footnote area to show a message that provides information about how to complete or use the form. However, a footnote message is optional and you can decide to leave the footnote area empty. To add a message to the footnote area, you must first create the dialog or drop dialog form. For information about how to create a dialog form, see [How to: Create a Dialog Form](how-to-create-a-dialog-form.md).

### To add a message to the footnote area

1.  In the AOT, expand **Forms** and find the form you want to work with. Expand the form, expand **Designs**, and then expand **Design**. The **Design** node should include a group control named **DialogCommit**.

2.  Expand the **DialogCommit** group control. You should see a group control named **Footnote**.
    
    If you want to add a **Footnote** group, click the **DialogCommit** group, click **New Control**, and then click **Group**. The group control must be the last control in the group. If you have to move the control, click the control and then press ALT+UP ARROW or ALT+DOWN ARROW.

3.  Click the **Footnote** group control. In the property sheet, specify values for the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>FrameType</strong></p></td>
    <td><p><strong>Edged 3D Line</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>Footnote</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>MarginlessContainer</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>TopMargin</strong></p></td>
    <td><p><strong>10</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Visible</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    </tbody>
    </table>


4.  Right-click the **Footnote** group control, click **New Control**, and then click **Group**. A group control is added to the form.

5.  Click the group control. In the property sheet, specify values for the following properties:
    

    > [!TIP]
    > <P>You can use code to hide or show the message in the footnote area. To see an example of how to show or hide a group, see <A href="how-to-hide-fields-on-a-dialog-form.md">How to: Hide fields on a Dialog Form</A>.</P>

    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>AutoDeclaration</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Columns</strong></p></td>
    <td><p><strong>2</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Columnspace</strong></p></td>
    <td><p><strong>5</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>FrameType</strong></p></td>
    <td><p><strong>None</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a unique name for the static text control.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Visible</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    </tbody>
    </table>


6.  Right-click the group control, click **New Control**, and then click **Window**.

7.  Click the window control. In the property sheet, specify values for the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>BackStyle</strong></p></td>
    <td><p><strong>Transparent</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ImageResource</strong></p></td>
    <td><p>Specify the embedded resource you want to appear in the footnote area. To see a list of embedded resources, click <strong>Tools</strong> in the menu of the development workspace, and then click <strong>Embedded resources</strong>.</p>
    <p>For example, use <strong>928</strong> to show a caution symbol with the footnote message.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a unique name for the window control.</p></td>
    </tr>
    </tbody>
    </table>


8.  Right-click the group control, click **New Control**, and then click **StaticText**.

9.  Click the control. In the property sheet, set values for the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Type a unique name for the static text control.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the instruction you want to appear under the main instruction. You can select a label or type the text that you want to appear.</p></td>
    </tr>
    </tbody>
    </table>


10. Right-click the form and then click **Save**.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

