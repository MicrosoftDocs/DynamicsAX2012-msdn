---
title: Modal Prompts
TOCTitle: Modal Prompts
ms:assetid: af69b5bc-5653-4c60-b54c-5880865a28c1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh745330(v=AX.60)
ms:contentKeyID: 42607681
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Modal Prompts [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you write code for a User Control in Enterprise Portal, you may want to prompt the user or display important information related to the current task. You can use the AxModalPrompt control to do this.

## Creating a modal prompt dialog box with AxModalPrompt

To create a modal prompt dialog box with the AxModalPrompt control is a multiple-step process. All steps must be completed for the modal prompt to work correctly.

### To create a modal prompt dialog box

1.  In the code for the User Control, create a variable for the modal prompt. For example, the following code creates a variable of type AxModalPrompt that will be used for a verification modal prompt dialog box.
    
    ``` csharp
    // Create a modal prompt object.
    private AxModalPrompt<MessagePromptInputData, PromptResult> verificationPrompt;
    ```

2.  Add a function that will return a new MessagePrompt object. This function will be used when the modal prompt object is configured.
    
    ``` csharp
    private MessagePrompt CreateMessagePrompt()
    {
        return new MessagePrompt();
    }
    ```

3.  In the Page\_Load method for the User Control, add code that initializes the modal prompt object, registers the function that is called when the prompt is created, and adds the control to the page. Continuing the previous example, the following code in the Page\_Load method performs these steps for the verification modal prompt dialog box.
    
    ``` csharp
    // Initialize the modal prompt.
    verificationPrompt = new AxModalPrompt<MessagePromptInputData, PromptResult>();
    
    // Register the function that is called when the prompt is created.
    verificationPrompt.SetRuntimeHostedUserControlProvider<MessagePrompt>(this.CreateMessagePrompt);
    
    // Add the modal prompt to page.
    this.Controls.Add(verificationPrompt);
    ```

4.  In the Page\_Load method for the User Control, add code that registers the PromptDismissed event for the modal prompt. The following example shows the registration code and the event handler code for the verification modal prompt dialog box.
    
    ``` csharp
    // Register the PromptDismissed event.
    verificationPrompt.PromptDismissed += new EventHandler<PromptDismissedEventArgs<PromptResult>>(validationPrompt_PromptDismissed);
    
    void validationPrompt_PromptDismissed(object sender, PromptDismissedEventArgs<PromptResult> e)
    {
    
    }
    ```

5.  Add code to the PromptDismissed event handler to perform the appropriate action based what action the user performed in the modal prompt. For the example verification modal prompt dialog, the ClickedButton property of the event arguments is examined. If the OK button was clicked, a method is run to restrict the work orders that are displayed.
    
    ``` csharp
    void validationPrompt_PromptDismissed(object sender, PromptDismissedEventArgs<PromptResult> e)
    {
        if (e.ClickedButton == PromptClickedButton.Ok)
        {
            this.WorkOrderListDataSource.GetDataSet().DataSetRun.AxaptaObjectAdapter.Call("MyWorkOrders");
        }
    }
    ```

6.  Add code that displays the modal prompt. For the example verification modal prompt dialog box, this code is added to a push button.
    
    ``` csharp
    protected void MyWorkOrders_Click(object sender, EventArgs e)
    {
        // Verify that the user wants to restrict the list of work orders.
        MessagePromptInputData mpid = new MessagePromptInputData("Facility Management", "Restrict the work order list to show only your work orders?", PromptAutoButtons.OkCancel);
    
        // Show the modal prompt.
        verificationPrompt.Show(mpid, null);
    }
    ```

The following illustration shows the modal prompt dialog box that is created.

![Modal Prompt Dialog](images/Hh745330.EP_ModalDialogPrompt(AX.60).gif "Modal Prompt Dialog")

## Size of the Modal Prompt

The size of the modal prompt is determined automatically. If necessary, you can use a specific size for the modal prompt. Do this by setting the DialogSize property of the modal prompt dialog object. The available size values are defined in the DialogSize enumeration, which is part of the Microsoft.Dynamics.Framework.Portal.UI namespace. The following example sets the size of the modal prompt dialog box to the medium size.

``` csharp
// Verify that the user wants to restrict the list of work orders.
MessagePromptInputData mpid = new MessagePromptInputData("Facility Management", "Restrict the work order list to show only your work orders?", PromptAutoButtons.OkCancel);

// Set the size of the modal prompt.
verificationPrompt.DialogSize = DialogSize.Medium;

// Show the modal prompt.
verificationPrompt.Show(mpid, null);
```

## Multiple-line Modal Prompts

You may want to display multiple lines in the modal prompt dialog box. To do this, you must create a MultiLineMessagePromptInputData type that lets you add more lines to the text displayed in the modal prompt. The following example shows the class that defines the MultiLineMessagePromptInputData object. This class has a dependency on the HtmlUtilities object, which is part of the Microsoft.Dynamics.AX.Framework.Utilities namespace. The code for your User Control must reference this namespace.

``` csharp
[Serializable]
public class MultiLineMessagePromptInputData : MessagePromptInputData
{
     public MultiLineMessagePromptInputData(string headerText, string bodyText, PromptAutoButtons buttons)
        : base(HtmlUtilities.EncodeHtml(headerText),
        "<p>" + HtmlUtilities.EncodeHtml(bodyText) + "</p>",
        buttons)
    {
    }

    public void AddBodyTextLine(string text)
    {
        this.BodyText += "<p>" + HtmlUtilities.EncodeHtml(text) + "</p>";
    }
}
```

To define the content of a multiple-line modal prompt, you will create an instance of the MultiLineMessagePromptInputData object, and then add more lines to it. The following example shows how to create and display a multi-line modal prompt.

``` csharp
// Verify that the user wants to restrict the list of work orders.
MultiLineMessagePromptInputData mpid = new MultiLineMessagePromptInputData("Facility Management", "Restrict the work orders?", PromptAutoButtons.OkCancel);

// Add an additional line to the modal prompt.
mpid.AddBodyTextLine("Only your work orders will be displayed.");

// Show the modal prompt.
verificationPrompt.Show(mpid, null);
```

