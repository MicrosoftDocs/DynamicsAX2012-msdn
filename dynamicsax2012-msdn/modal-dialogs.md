---
title: Modal Dialogs
TOCTitle: Modal Dialogs
ms:assetid: 2ebce1b1-efd3-4634-bd34-89b9388bf705
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh830902(v=AX.60)
ms:contentKeyID: 45260822
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Modal Dialogs [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Enterprise Portal pages can be displayed in SharePoint modal dialogs. Modal dialogs are used for many pages because they provide a better user experience. They can help the user focus on a specific task, yet still maintain their context within Enterprise Portal. For information about opening pages in modal dialogs, see [How to: Create Web Menu Items](how-to-create-web-menu-items.md). See [Page Interaction Patterns](page-interaction-patterns.md) for information about how modal pages are used in Enterprise Portal.

The code that you add to User Controls will have to work with modal dialogs. The following sections provide details about how your code can do this.

## DialogHelper Class

The DialogHelper class has several methods that are useful when you are working with SharePoint modal dialogs. This class is located in the Microsoft.Dynamics.Framework.Portal.UI namespace. You must have the following using statement to reference this namespace:

using Microsoft.Dynamics.Framework.Portal.UI;

The following examples show the common actions that are performed by using the DialogHelper class, such as opening and closing modal dialogs.

### Open

The Open() method opens a page as a modal dialog. You can use an AxUrlMenuItem to specify the page to be opened. The following example shows code for a button that opens the URL web menu item named ModalForm1.

``` csharp
protected void Button1_Click(object sender, EventArgs e)
{
    // Create an AxUrlMenuItem
    AxUrlMenuItem menuItem = new AxUrlMenuItem("ModalForm1");

    DialogHelper.Open(menuItem, this);
}
```

The Open() method can also use the AXDialogArgs object to specify how the modal dialog is opened, and what content is displayed. The following example opens a modal dialog and displays a web site.

``` csharp
protected void OpenWebSite_Click(object sender, EventArgs e)
{
    // Set up the arguments.
    AXDialogArgs args = DialogHelper.DialogArgs;
    args.URL = "http://www.microsoft.com";

    // Display the web site in a modal dialog.
    DialogHelper.Open(args, this);
}
```

### Close

The Close() method closes the current modal dialog. In its simplest form, it takes no parameters. The following example closes the current dialog when the user clicks the button:

``` csharp
protected void Button1_Click(object sender, EventArgs e)
{
    DialogHelper.Close();
}
```

Use the Close() method with the boolean parameter true to close all of the modal dialogs. This is useful for cases like canceling an operation, when all modal dialogs have to be closed. This is shown in the following example:

``` csharp
protected void CancelButton_Click(object sender, EventArgs e)
{
    DialogHelper.Close(true);
}
```

The Close() method can be configured by the CloseDialogBehavior enumeration. For example, the following code closes the current modal dialog and refreshes the page that is returned to.

``` csharp
protected void CloseButton_Click(object sender, EventArgs e)
{
    DialogHelper.Close(CloseDialogBehavior.RefreshPage);
}
```

### IsCurrentPageModalDialog

The IsCurrentPageModalDialog() method is useful to determine whether the code in the current page is running in a modal dialog. For example, a single User Control can be used for both a modal page and for a report drill-back destination that is displayed in the main Enterprise Portal window. The content to display could be different in these two cases. If the page is shown in main Enterprise Portal window (not in a modal dialog) then hiding the Close button on the action pane for the page is reasonable. The following example does this.

``` csharp
protected void Page_Load(object sender, EventArgs e)
{
    // Find out whether the page is being displayed in a modal dialog window.
    // If it is not, such as when it is opened by a drill-back from an
    // SSRS report, then do not show the Close button.

    if (DialogHelper.IsCurrentPageModalDialog() == false)
    {
        // Do not show the Close button.
        this.RoomForm.AutoGenerateCancelButton = false;
    }
}
```

### Navigate

The Navigate() method navigates to a new page, replacing the current page. The following example shows code for a button in a User Control. When the user clicks the button, the WorkOrdersList is displayed, replacing the current page.

``` csharp
protected void WorkOrderList_Click(object sender, EventArgs e)
{
    AxUrlMenuItem menuItem = new AxUrlMenuItem("WorkOrdersList");
    DialogHelper.Navigate(menuItem, this);
}
```

## Returning Values from a Modal Dialog

A user can be viewing a page in Enterprise Portal (call it the base page) and open another page as a modal dialog. When the modal dialog closes, you may want to return a value from the modal dialog back to the base page from which it was opened.

### Setting up the closed event

To set up the closed event, you must register the ModalDialogClosed event for the User Control on the base page. Typically, you do this in the **Page\_Load** event for the User Control. For detailed information about registering for events, see [User Control Events](user-control-events.md). The following code shows an example of this registration:

``` csharp
protected void Page_Load(object sender, EventArgs e)
{
    AxBaseWebPart.GetWebpart(this).ModalDialogClosed += new EventHandler<AXModalDialogClosedEventArgs>(Base_ModalDialogClosed);
}

void Base_ModalDialogClosed(object sender, AXModalDialogClosedEventArgs e)
{
    // Code to handle the returned value.
    string returnValue;

    returnValue = e.DialogArgs.Data;
    TextBoxReturnValue.Text = returnValue;
}
```

In the event handler for the ModalDialogClosed event, you can use the event arguments to retrieve the data returned. In the previous example, the returned value is used to set a text box.

### Returning the value

In the User Control that is displayed in the modal dialog, you specify the string data that you want to return to the base page. For example, the following code is the button click script that returns the value in the text box named TextBox1. When the code closes the modal dialog, the argument value is returned to the base form.

``` csharp
protected void Button1_Click(object sender, EventArgs e)
{
    AXDialogArgs args = DialogHelper.DialogArgs;
    args.Data = TextBox1.Text;

    DialogHelper.Close(CloseDialogBehavior.Auto);
}
```

If you want to do this in a single step, you can specify the value to return directly in the DialogHelper.Close() method:

``` csharp
DialogHelper.Close(CloseDialogBehavior.Auto, "This is the string that is returned");
```

