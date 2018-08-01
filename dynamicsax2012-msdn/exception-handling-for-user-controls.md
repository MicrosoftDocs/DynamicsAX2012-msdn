---
title: Exception Handling for User Controls
TOCTitle: Exception Handling
ms:assetid: cacfc62a-ae7e-47a6-b96b-0488b929e73c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc619956(v=AX.60)
ms:contentKeyID: 28119499
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Exception Handling for User Controls [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Code you add to User Controls may call methods that throw exceptions. It is important that your code correctly handle any exceptions encountered. Unhandled exceptions create a poor experience for the user. The Enterprise Portal framework can help you manage exceptions.

## Exception Categories

Exceptions in Enterprise Portal are divided into three categories. These exception categories are defined in the enumeration AxExceptionCategory. They are described in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Exception Category</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NonFatal</p></td>
<td><p>Indicates an exception that was expected. The exception handling code should respond appropriately and allow for the request to continue normally.</p></td>
</tr>
<tr class="even">
<td><p>AxFatal</p></td>
<td><p>Indicates that an unrecoverable error has occurred in Enterprise Portal. Enterprise Portal content will not display. Non-portal content should display as expected.</p></td>
</tr>
<tr class="odd">
<td><p>SystemFatal</p></td>
<td><p>Indicates a serious error has occurred and the request must be aborted. Errors of this kind often cause an HTTP error code 500.</p></td>
</tr>
</tbody>
</table>


## When Exception Handling Is Needed

You must handle exceptions when code you add to a User Control directly calls code that can throw exceptions. The following are common situations where this occurs.

  - Your code directly calls methods from the Enterprise Portal framework that can throw exceptions. For instance, the EndEdit method for a DataSetViewRow object can encounter exceptions as a result of the edit operation. If your code called this method directly, it must handle the exceptions.

  - Your code calls X++ methods through a proxy, and the X++ methods throw exceptions. Your code must handle the exceptions.

The controls for Enterprise Portal have built-in functionality to perform standard actions such as editing a row in a grid or saving the contents of a form. The code for this built-in functionality properly handles exceptions. If the action started with the built-in functionality of a control, such as a user clicking the OK button for an AxForm, you do not need to add code to handle exceptions for that action.

## Exception Handling Code

The code to handle exceptions for User Controls in Enterprise Portal has the following basic form. This code calls the TryHandleException method to determine the category of the Enterprise Portal exception. Based on the category, the code will try to correctly respond to the exception.

``` csharp
try
{
    // Code that may encounter exceptions goes here.
}
catch (System.Exception ex)
{
    AxExceptionCategory exceptionCategory;

    // Determine whether the exception can be handled.
    if (AxControlExceptionHandler.TryHandleException(this, ex, out exceptionCategory) == false)
    {
        // The exception was fatal and cannot be handled. Rethrow it.
        throw;
    }

    if (exceptionCategory == AxExceptionCategory.NonFatal)
    {
        // Application code to properly respond to the exception goes here.
    }
}
```


> [!NOTE]
> <P>The Enterprise Portal framework will automatically display the exception message in the Infolog web part on the page.</P>



The code that runs in response to the exceptions should leave Enterprise Portal in a valid state. For example, if a validation exception occurs when the user clicks the OK button to save the values on a page, data will not be saved. The code in the exception handler should prevent Enterprise Portal from redirecting to a different page. This allows for the user to see the error on the page, correct it, and then perform the action again.

## Exception Example

The CalculateGrade method is an X++ method that is part of the Test class added to Microsoft Dynamics AX. The method takes a numeric grade value and returns the corresponding letter grade. If the input value is outside the valid range (0 to 100), an exception is thrown. The proxy was used to make this method available to User Controls.

The following example is the click method for a button added to a User Control. It calls the CalculateGrade method to retrieve a letter grade based on a test score. The code handles the exception that occurs if the input value is out of range. In this case, it displays text that indicates the grade is out of range.

``` csharp
protected void Button1_Click(object sender, EventArgs e)
{
    string letterGrade;

    // Method can throw an exception, so an exception handler is used.
    try
    {
        letterGrade = Test.CalculateGrade(this.AxSession.AxaptaAdapter, Convert.ToInt16(TextBoxScore.Text));
        TextBoxGrade.Text = letterGrade;
    }
    catch (System.Exception ex)
    {
        AxExceptionCategory exceptionCategory;
        if(AxControlExceptionHandler.TryHandleException(this, ex, out exceptionCategory) == false)
        {
            // The exception was fatal, so rethrow it.
            throw;
        }

        if(exceptionCategory == AxExceptionCategory.NonFatal)
        {
            if (ex.InnerException.Message.Equals("Grade is out of range"))
            {
                TextBoxGrade.Text = "<<Grade out of range>>";
            }
        }
    }
}
```

