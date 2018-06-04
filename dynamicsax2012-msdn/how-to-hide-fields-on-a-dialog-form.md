---
title: 'How to: Hide fields on a Dialog Form'
TOCTitle: 'How to: Hide fields on a Dialog Form'
ms:assetid: 9d99e7ad-2304-4dbb-b305-3be11ff972d4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh811913(v=AX.60)
ms:contentKeyID: 44089714
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Hide fields on a Dialog Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how you enable a dialog or drop dialog form to hide and then show a collection of fields and controls. To access the hidden fields, you click a button on the dialog form. You can use the hidden fields and controls to complete less common scenarios from the dialog form. To complete the following steps, you must first create the dialog or drop dialog form. For information about how to create a dialog form, see [How to: Create a Dialog Form](how-to-create-a-dialog-form.md).

### To add a group of hidden fields

1.  In the AOT, find the dialog form that you want to modify. Expand the form, expand **Designs**, expand **Design**, right-click the **DialogContent** group, click **New Control**, and then click **Group**. A group control is added to the form. Move the control to be the last control in the **DialogContent** group. To move the group, press ALT+UP ARROW or ALT+DOWN ARROW.
    

    > [!WARNING]
    > <P>If you did not use a template or the name property of the group controls were changed, you might see different names for the <STRONG>DialogContent</STRONG> or <STRONG>DialogCommit</STRONG> group controls.</P>



2.  Right-click the group control you added and then click **Properties**. The property sheet for the control appears. In the property sheet, populate the following properties by using the specified values:
    
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
    <td><p><strong>FrameType</strong></p></td>
    <td><p><strong>None</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>MoreFields</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Visible</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    </tbody>
    </table>


3.  Expand the **Data Source** node of the form, right-click the table that contains the fields you want to add to the form, and then click **Open New Window**.

4.  In the AOT window that shows the table, expand **Fields**. Drag the field or field group you want to appear on the form onto the group control that you added earlier.

### To add the button control

1.  In the AOT window that shows the form, click the group named **DialogCommit**. In the property sheet for the **DialogCommit** group, set the **Column** property to **2**.

2.  Right-click the **DialogCommit** group, click **New Control**, and then click **Button**. A button control is added to the group. The button should be the first control in the group. To move the button, press ALT+UP ARROW or ALT+DOWN ARROW.

3.  Click the button. In the property sheet, populate the following properties by using the specified values:
    
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
    <td><p><strong>ButtonDisplay</strong></p></td>
    <td><p><strong>Text &amp; Image left</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>DisabledImage</strong></p></td>
    <td><p><strong>7884</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>DisabledImageLocation</strong></p></td>
    <td><p><strong>EmbeddedResource</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ImageLocation</strong></p></td>
    <td><p><strong>EmbeddedResource</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p><strong>moreFewerButton</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>NormalImage</strong></p></td>
    <td><p><strong>7887</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>Link</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Text</strong></p></td>
    <td><p>To display <strong>Show more fields</strong>, select label @SYS191195.</p>
    <p>To display <strong>Shows fewer fields</strong>, select label @SYS191193.</p></td>
    </tr>
    </tbody>
    </table>


### To show or hide a field group

1.  Expand the button control that you added earlier, right-click **Methods**, click **Override method**, and then click **clicked**. The method opens in the code editor.

2.  In the code editor, add a call to a method named toggleMoreFewer. Use a reference to the current button control as a method parameter. In addition, you should add toggleMoreFewer after the call to super.
    
    The following code example shows how to modify the clicked method.
    
        void clicked()
        {
            super();
            
            element.toggleMoreFewer(this);
        }

3.  Add the toggleMoreFewer method to the form. Right-click the **Methods** node of the form, and then click **New Method**. A new method appears in the code editor.

4.  Specify that the method is public. In addition, change the name of the method to toggleMoreFewer and add that the method accept a **FormButtonControl** as a parameter. Add code that changes the **Visible** property of the **MoreFields** group that you added earlier. Also, change the image and text that appear on the button control.
    
    The following code example shows the toggleMoreFewer method. Notice how the method changes the visible property of the **MoreFields** group. Also notice how the method changes the value of the normalImage and text properties of the button control.
    
        public void toggleMoreFewer(FormButtonControl moreFewerButton)
        {
            element.lockWindowUpdate(true);
            
            moreFewerButton.imageLocation(2);
            
            if(MoreFields.visible())
            {
                moreFewerButton.normalImage(“7887”);
                moreFewerButton.text(‘@SYS191195’);
                
                MoreFields.visible(false);
            }
            else
            {
                moreFewerButton.normalImage(“7883”);
                moreFewerButton.text(‘@SYS191193’);
                
                MoreFields.visible(true);
            }
            
            element.lockWindowUpdate(true);
        }

5.  Right-click the form and then click **Save**.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

