---
title: 'How to: Create a Content Page'
TOCTitle: 'How to: Create a Content Page'
ms:assetid: c9ba215b-ba93-4a5c-8631-d8eeb709fa37
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc638023(v=AX.60)
ms:contentKeyID: 35251252
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Content Page [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Microsoft Dynamics AX content page is a specialized type of form. To create a content page, use the Application Object Tree (AOT) to create a new form with a **WindowType** property of **ContentPage**. The following procedure describes how to use the AOT to create a content page.

### To create a content page form

1.  In the AOT, right-click the **Forms** node, and then click **New Form**. The **Forms** node expands and displays a new form.

2.  Right-click the new form node, and then click **Properties**. In the properties window, enter a unique name for the content page. To save the content page name, press ENTER.

3.  To view the design properties of the form, expand the new form node, expand **Designs**, and then click the **Design** node. The properties window displays the form properties. While most form properties can use the default value, set values for the following properties.
    
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
    <td><p><strong>BottomMargin</strong></p></td>
    <td><p><strong>Auto</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Caption</strong></p></td>
    <td><p>Specify a label for the content page.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>LeftMargin</strong></p></td>
    <td><p><strong>Auto</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>RightMargin</strong></p></td>
    <td><p><strong>Auto</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TopMargin</strong></p></td>
    <td><p><strong>Auto</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>WindowType</strong></p></td>
    <td><p><strong>ContentPage</strong></p></td>
    </tr>
    </tbody>
    </table>


4.  With the basic form created, add the control that you want to use to display data. Right-click **Design**, click **New Control**, and then click the type of control.
    

    > [!NOTE]
    > <P>For information about how to use an ActiveX control, see <A href="how-to-add-activex-controls-to-forms.md">How to: Add ActiveX Controls to Forms</A>.</P>



5.  Click the new control to display its properties. Set values for the following properties.
    
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
    <td><p><strong>Height</strong></p></td>
    <td><p><strong>Column height</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a label for the control.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>VerticalSpacing</strong></p></td>
    <td><p><strong>0</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Width</strong></p></td>
    <td><p><strong>Column width</strong></p></td>
    </tr>
    </tbody>
    </table>


6.  To save the new content page, right-click the form in the AOT, and then click **Save**.

With the content page created, add a data source that retrieves the data records. For more information about how to add a data source to a content page, see [How to: Add a Data Source to a Primary List Page](how-to-add-a-data-source-to-a-primary-list-page.md).


> [!NOTE]
> <P>After adding the data source, you might want to override form and control methods that load data from the data source into the control, and respond to user interface events.</P>



To complete the content page, add an action pane. For information about how to add an action pane to a content page, see [Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md).

## See also

[Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md)

[How to: Create a List Page Form](how-to-create-a-list-page-form.md)

[Form Control Properties](form-control-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

