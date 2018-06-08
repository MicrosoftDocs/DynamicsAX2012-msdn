---
title: Pop-up Windows
TOCTitle: Pop-up Windows
ms:assetid: 6f1de021-5ca6-4a20-b624-079e41e08010
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc592938(v=AX.60)
ms:contentKeyID: 28119437
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Pop-up Windows 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Many tasks in Enterprise Portal are performed in modal windows that are opened from list pages. The URL Web Menu Item used to open the page indicates whether the page is displayed in a modal window. This is the preferred way to use modal windows in Enterprise Portal for Microsoft Dynamics AX 2012.

In Microsoft Dynamics AX 2009, if you wanted to display information or have the user perform a task in a separate window, you had to use a pop-up window. A pop-up window is another web browser window that appears on top of the main Enterprise Portal window. Pop-up windows like this can still be used in Microsoft Dynamics AX 2012.

## Parent Window

The parent window is the page in Enterprise Portal from which the pop-up window is opened. The parent window must contain a User Control that has the [AxPopupParentControl](axpopupparentcontrol.md) component. Properties for this component allow for you to specify characteristics of the pop-up window. For example, the **PopupHeight** and **PopupWidth** properties control the size of the pop-up window.

## Child Window

The child window is another page in Enterprise Portal that will be displayed in the pop-up window. It must have a URL Web Menu Item defined that points to the page. For details about how to create a web menu item, see [How to: Create Web Menu Items](how-to-create-web-menu-items.md).

The page used for the child window will typically contain a User Control that has the [AxPopupChildControl](axpopupchildcontrol.md) component. This component is used when closing the pop-up window. It is also used when passing values from the pop-up window back to the parent window.

## Opening the Pop-up Window

To open the pop-up window, use the OpenPopup method provided by the AxPopupParentControl. This method is typically called from the code for a User Control on the parent page. The OpenPopup method has one parameter, which specifies the web menu item of the page to be opened and displayed in the pop-up window.

The following example is the code for a button that was added to a User Control. The User Control contains the AxPopupParentControl component. An AxUrlMenuItem object is created that specifies the page to open in the pop-up window.

``` csharp
protected void SamplePopup_Click(object sender, EventArgs e)
{
    AxUrlMenuItem menuItem = new AxUrlMenuItem("SamplePopupPage");

    AxPopupParentControl1.OpenPopup(menuItem);
}
```

## Closing the Pop-up Window

The user can close a pop-up window by clicking the close box. The pop-up window can also be closed through code for a User Control in the pop-up window. The AxPopupChildControl provides the ClosePopup method. This method requires two boolean parameters. The first specifies whether field values must be passed from the pop-up window back to the parent. The second parameter specifies whether the parent page has to post back after the pop-up window closes.

If the second parameter of the ClosePopup method is set to true, the PopupClosed event for the AxPopupParentControl will be run when the pop-up window closes. You can use the method handler for this event to retrieve values that are passed back to the parent from the pop-up window.

## Passing Values Back to the Parent Window

It is often useful to pass values from the pop-up window back to the parent window. The AxPopupParentControl and AxPopupChildControl provide a collection of AxPopupField objects for this purpose. This collection is accessed through the **Fields** property for the component. This property provides access to the **AxPopupField Collection Editor**.

You will use the **AxPopupField Collection Editor** to create the collection of field values to pass from the child window back to the parent window. Each AxPopupField object in the collection has a **Name** property. It also has an optional **Target** property which maps the field to a control on the page. The names of the AxPopupField objects in the collection must be the same for both the AxPopupChildControl and the AxPopupParentControl. For instance, assume the AxPopupParentControl had the following set of AxPopupField objects defined:

Field1

Field2

Field3

The AxPopupChildControl must have AxPopupField objects that have the same names defined for its **Fields** collection. The names enable the fields to be matched as they are passed from the child back to the parent.

The values of the AxPopupField objects can be set or retrieved automatically. They can also be set or retrieved manually through code for the User Control.

### Automatically Setting and Retrieving Values

If you have set the **Target** property for an AxPopupField object for the AxPopupChildControl, it is mapped to a field for the User Control. In the pop-up window, Enterprise Portal will automatically set the AxPopupField object value to the value that is contained in the field specified by the **Target** property. If you have set the **Target** property for the AxPopupField object for the AxPopupParentControl, the value passed back for this field from the pop-up window will automatically be retrieved and put in the mapped field.

The field specified by the Target property must be within the same naming container as the User Control, or any parent container in the hierarchy. The field must also have the Value client-side property.

### Manually Setting and Retrieving Values

If you have not set the **Target** property for the AxPopupField objects, you can set their value manually through code in the pop-up window. Use the SetFieldValue method to do this. You can also use code in the parent window to retrieve the value of each AxPopupField object. Use the GetFieldValue method to do this.


> [!WARNING]
> <P>You cannot set or retrieve an AxPopupField object value through code if you have used the <STRONG>Target</STRONG> property to map it to a field.</P>



For example, the following is code for a button that is contained in the User Control displayed in a pop-up window. When the button is clicked, the two AxPopupField objects defined in the **Fields** collection have their values set. Then the pop-up window is closed.

``` csharp
protected void Button1_Click(object sender, EventArgs e)
{
    // Specify the values to be returned.
    AxPopupChildControl1.SetFieldValue("Field1", "Field 1's value");
    AxPopupChildControl1.SetFieldValue("Field2", "Field 2's value");

    // Close the pop-up window. Indicate that values are to be
    // returned and that a postback should occur for the parent.
    AxPopupChildControl1.ClosePopup(true, true);
}
```

Code for the PopupClosed event on the parent window is typically used to retrieve the values passed back from the pop-up window. The following example shows the code that retrieves the values returned by the previous example.

``` csharp
void AxPopupParentControl1_PopupClosed(object sender, EventArgs e)
{
    string value1;
    string value2;

    value1 = AxPopupParentControl1.GetFieldValue("Field1"));
    value2 = AxPopupParentControl1.GetFieldValue("Field2"));
}
```

