---
title: Page Redirection
TOCTitle: Page Redirection
ms:assetid: 0368d123-c7e5-45a7-9e8f-0716842d356c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc518834(v=AX.60)
ms:contentKeyID: 28119385
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Page Redirection [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When a user has finished performing the task for a page, you may want to display a different page in Enterprise Portal. If the page is displayed in a modal dialog, you can close the current page so the page immediately beneath it is displayed. If the page is displayed in the main browser window, you can redirect to the new page to display.

## Redirection Method

Page redirection is used in several locations in the code for a User Control. For instance, the user is returned to the previously displayed page when they click OK or Cancel in a task page. Implementing a single redirection method consolidates the code into one location.

A task page in Enterprise Portal is typically displayed in modal dialog. When the user completes the task, the dialog is closed. The DialogHelper class provides the Close() method that is used to close the current modal dialog. It also provides the IsCurrentPageModalDialog() method to help you determine whether the current page is being shown in a modal dialog.

In some cases, a task page may be displayed directly in the main browser window. The AxWebSession object keeps track of the URL of the page that was previously displayed for the user. Typically, this is the page the user will be redirected to after they complete a task in the current page. If the previous URL is not available, the user should be redirected to a known page in Enterprise Portal after they complete a task.

The following example is the RedirectToPreviousPage method added for a User Control. This User Control contains an AxForm component and appears on a task page. If the page is being displayed in a modal dialog, the dialog is closed when the user finishes the task. If the page is being displayed in the main browser window, the user is redirected to the previous page when they finish the task. If the previous page is not available, the user is redirected to a known list page in the role center. Notice how a URL web menu item is used to specify the page to display.

``` csharp
private void RedirectToPreviousPage()
{
    if (DialogHelper.IsCurrentPageModalDialog() == true)
    {
        // Page is displayed in a modal dialog, so close the page.
        DialogHelper.Close();
    }
    else
    {
        // Page is opened in the main browser, so try to return to the previous page.
        if (!String.IsNullOrEmpty(AxWebSession.GetPreviousURL(this.Page)))
        {
            Response.Redirect(AxWebSession.GetPreviousURL(this.Page));
        }
        else
        {
            // The previous page is not available, so return to a known page.
            // Use the URL Web Menu item from the AOT to specify which
            // page will be displayed.
            AxUrlMenuItem listpage = new AxUrlMenuItem("FCMWorkOrdersListPage");
            Response.Redirect(listpage.Url.OriginalString);
        }
    }
}
```

## Using the Redirection Method

The redirection method is called from several locations in the User Control code. For example, it is called in the event handler that is run every time that a button on the AxForm for the User Control is clicked. The following code verifies that the Cancel button for the form was clicked. If it was, the redirection method is called to redirect the user to the previous page.

``` csharp
void WorkOrderForm_ItemCommand(object sender, DetailsViewCommandEventArgs e)
{
    if (e.CommandName == "Cancel")
    {
        // Cancel any editing action that had been started.
        this.DataSourceView.CancelEdit();

        // Redirect the user to the previous page.
        this.RedirectToPreviousPage();
    }
}
```

The redirection method is also called in the event handlers that are run in response to events such as ItemInserted or ItemUpdated. The following example shows the ItemInserted event handler for the AxForm component named WorkOrderForm. This event handler determines whether the event was successful. If it was, the redirection method is called to redirect the user to the previous page.

``` csharp
void WorkOrderForm_ItemInserted(object sender, DetailsViewInsertedEventArgs e)
{
    // Verify whether the operation was successful.
    if (e.AffectedRows == 1)
    {
        this.RedirectToPreviousPage();
    }
}
```

