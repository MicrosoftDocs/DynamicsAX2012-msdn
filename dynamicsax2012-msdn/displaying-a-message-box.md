---
title: Displaying a Message Box
TOCTitle: Displaying a Message Box
ms:assetid: b9774ddb-c081-4c87-83ee-bbc9fa670bd6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa860308(v=AX.60)
ms:contentKeyID: 35249871
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Displaying a Message Box 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can display a message in a modal dialog box by using the Box class.

Some methods in the Box class display a dialog box that contains multiple buttons. These methods have a parameter for choosing which button has focus when the dialog box is first displayed. This parameter is of type DialogButton enum. Most of these multiple-button methods return a value of type DialogButton enum. This returned value enables your program to branch based on which button the user clicked.


> [!NOTE]
> <P>The Box application class calls the DialogBox system class. Don't call it directly—always call the Box class instead.</P>



## Creating a Message Box

The following are guidelines to help you create an effective message box:

  - Choose a Box method that matches your purpose.

  - Write the information text to match the buttons in the box.

  - Choose the button best suited for having initial focus.

  - Use the returned DialogButton value to direct the branching in your code.

## Box Class Methods

The following table describes the Box class methods and their associated DialogBoxType system enum values.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Box class static method name</p></th>
<th><p>Associated DialogBoxType enum value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>info</p></td>
<td><p>InfoBox</p></td>
<td><p>The <strong>OK</strong> button is the only one that the info method displays in the dialog box.</p>
<p>Use this method to display general information messages rather than for warning or error messages.</p></td>
</tr>
<tr class="even">
<td><p>infoOnce</p></td>
<td><p>InfoBox</p></td>
<td><p>The infoOnce method is similar to the info method but with the following differences:</p>
<ul>
<li><p>Your code cannot set the text in the title bar.</p></li>
<li><p>An additional header section is displayed under the title bar, and you can set the text that displays in the header.</p></li>
<li><p>A <strong>More info...</strong> button is present. When clicked, it opens a Web browser to the URL string that you supply through a parameter.</p></li>
</ul>
<p>The infoOnce method returns void, even though it has two buttons.</p></td>
</tr>
<tr class="odd">
<td><p>infoOnceEx</p></td>
<td><p>InfoBox</p></td>
<td><p>The infoOnceEx method is similar to the infoOnce method but with the following differences:</p>
<ul>
<li><p>The infoOnceEx method has a parameter that can be passed in to set the text in the title bar.</p></li>
<li><p>The infoOnceEx method has a Boolean parameter for choosing whether to have the caller thread continue processing while the user reads the message in the dialog box.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>okCancel</p></td>
<td><p>OkCancelBox</p></td>
<td><p>The <strong>OK</strong> and <strong>Cancel</strong> buttons are displayed in the dialog box. Call this method when the user must confirm or reject an action.</p></td>
</tr>
<tr class="odd">
<td><p>stop</p></td>
<td><p>StopBox</p></td>
<td><p>The <strong>OK</strong> button is the only one displayed in the dialog box.</p>
<p>Use this method to display a message when the user should stop attempting their action or when a process has stopped running.</p></td>
</tr>
<tr class="even">
<td><p>warning</p></td>
<td><p>WarnBox</p></td>
<td><p>The <strong>OK</strong> button is the only one displayed in the dialog box. Use this dialog box for a warning message.</p></td>
</tr>
<tr class="odd">
<td><p>yesAllNoAllCancel</p></td>
<td><p>YesToAllNoToAllBox</p></td>
<td><p>The buttons displayed in this dialog box are <strong>Yes</strong>, <strong>Yes to all</strong>, <strong>No</strong>, <strong>No to all</strong>, and <strong>Cancel</strong>.</p></td>
</tr>
<tr class="even">
<td><p>yesNo</p></td>
<td><p>YesNoBox</p></td>
<td><p>The buttons displayed in this dialog box are <strong>Yes</strong> and <strong>No</strong>. Call this method when you need the user to make a choice.</p></td>
</tr>
<tr class="odd">
<td><p>yesNoNoAllCancel</p></td>
<td><p>NoToAllBox</p></td>
<td><p>The buttons displayed in this dialog box are <strong>Yes</strong>, <strong>No</strong>, <strong>No to all</strong>, and <strong>Cancel</strong>.</p></td>
</tr>
<tr class="even">
<td><p>yesNoAxaptaForm</p></td>
<td><p>YesNoBox</p></td>
<td><p>The yesNoAxaptaForm method is similar to the yesNo method but with the following differences:</p>
<ul>
<li><p>The yesNoAxaptaForm dialog box has a different image.</p></li>
<li><p>The yesNoAxaptaForm dialog box is wider.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>yesNoCancel</p></td>
<td><p>YesNoCancelBox</p></td>
<td><p>The buttons displayed in this dialog box are <strong>Yes</strong>, <strong>No</strong>, and <strong>Cancel</strong>. Call this method when the yesNo method is insufficient.</p></td>
</tr>
<tr class="even">
<td><p>yesNoOnce</p></td>
<td><p>YesNoBox</p></td>
<td><p>The yesNoOnce method is similar to the yesNo method but with the following differences:</p>
<ul>
<li><p>The yesNoOnce dialog box has a different image.</p></li>
<li><p>The yesNoOnce dialog box has a check box that the user can select to suppress any further occurrence of an associated message.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>yesYesAllNoCancel</p></td>
<td><p>YesToAllBox</p></td>
<td><p>The <strong>Yes</strong>, <strong>Yes to all</strong>, <strong>No</strong>, and <strong>Cancel</strong> buttons are displayed.</p></td>
</tr>
</tbody>
</table>


## Example

The following example displays a message box that contains buttons labeled **Yes**, **No**, and **Cancel**. The **No** button has initial focus. When a button is clicked, a message is displayed in the **Print Window** to indicate which button was clicked. Run this example as a job in the Application Object Tree (AOT).

    static void JobBoxDemo(Args _args)
    {
        DialogButton diagBut;
        str strMessage = "The No button should have initial focus.";
        str strTitle = "Title";
        ;
        diagBut = Box::yesNoCancel(
            strMessage,
            DialogButton::No, // Initial focus is on the No button.
            strTitle);
        if (diagBut == DialogButton::No)
            {
                print "The No button was clicked.";
            }
        else
            {
                print "The button that was clicked was: ", diagBut;
            }
        pause;
    }

## See also

[DialogBoxType Enumeration](https://msdn.microsoft.com/en-us/library/gg882119\(v=ax.60\))

[DialogButton Enumeration](https://msdn.microsoft.com/en-us/library/gg882120\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

