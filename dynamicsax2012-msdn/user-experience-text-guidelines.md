---
title: User Experience Text Guidelines
TOCTitle: Text Guidelines
ms:assetid: 24041411-b49b-445a-94b1-4e9f8e36b422
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886580(v=AX.60)
ms:contentKeyID: 35267944
ms.date: 11/07/2012
mtps_version: v=AX.60
f1_keywords:
- UX
- User interface
- UI
---

# User Experience Text Guidelines [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

User interface (UI) text is text that appears on the user interface. UI text includes titles of list pages, forms, and reports, and the labels of controls that they may contain, such as fields and buttons. UI text also includes tooltip text that appears when the user moves the pointer over a button or a menu, short Help text that is displayed in the status bar, and the messages that the user may receive, such as Infologs. The specific UI text guidelines for Microsoft Dynamics AX 2012 list pages, forms, reports, and so on, are included in the "Labels and text" sections of the topics under the Client, Enterprise Portal, and Reporting User Experience Guidelines. Therefore, this topic documents only general UI text guidelines that are not covered in those topics. This topic includes the following sections:

  - Guiding principles

  - Top things to do

  - Top things not to do

  - Short Help text guidelines

  - General error message guidelines

## Guiding principles

When you create UI text, the following should be your guiding principles:

  - Make all UI text clear. A user should never be puzzled by any UI text.

  - Make all UI text concise. A user should never have to read more than absolutely necessary.

  - Use terminology consistently. A user should never be given multiple wording for the same UI element.

  - Avoid technical jargon. Although appropriate for some audiences, an end-user should never have to decipher technical jargon.

## Top things to do

When you create UI text, the top things you should do are as follows:

  - Use correct capitalization. Approved abbreviations, acronyms, and intialisms should use all uppercase letters. For example, use "ID," and not "Id." Use sentence case for everything else.

  - Use correct punctuation. Do not use punctuation after labels or after short Help text that is displayed in the status bar. Use correct punctuation (period or question mark) for messages.

  - Use the verb-object construction for things that are tasks, for example the **Enter customer payments** form or the **Service** \> **Create service orders** menu option in the **Projects** form. Use singular objects unless the task can apply to multiple instances of an entity at the same time.

  - Use instructional text on forms if necessary. Start the instructional text with a present tense, active verb, for example, "Enter your locale, region, and language".

  - Limit short Help text to 100 characters.

  - Limit message text to 200 characters.

  - Use only one space between sentences, not two.

  - Use only the present tense for UI text, unless an occasional odd situation demands another tense.

  - Use an error message style that first gives the cause of the problem and the name of the specific object involved, and then tells briefly how to fix the problem.

  - Use the articles *a*, *an*, and *the* in error messages and instructional text wherever possible because articles help people who localize and people for whom English is a second language. For the same reason, also use prepositions, such as *of*, and demonstrative pronouns, such as *this* and *that*, wherever possible.

## Top things not to do

When you create UI text, the top things you should not do are as follows:

  - Do not use "Please" or "Sorry" in messages.

  - Do not use exclamation points in messages.

  - Do not use question marks with sentence fragments.

  - Do not use abbreviations, acronyms, or initialisms in instructional text or messages.

  - Do not use uppercase for the first letter of Microsoft Dynamics AX Application Object Tree (AOT) or Microsoft Dynamics AX element names unless they are uppercase in Microsoft Dynamics AX. Avoid unnecessary use of uppercase letters.

  - Do not use double quotation marks for variables. If quotation marks are needed, use single quotation marks, as in "There are illegal characters in the identifier '%1'."

## Short Help text guidelines

Status bar messages, also known as *short Help* or *Help text*, provide additional information about a specific control when the focus is on a UI element. Short Help also appears as a tooltip when the user moves the pointer over a button or a menu in the area pages. Unlike Help that appears when the user presses F1, text strings for short Help are stored in the label file. The reference to the label ID is coded in the properties for an application object.

Short Help text appears at the bottom of a form when the user's pointer is located in a field.

Example of short Help text at the bottom of a form

  
![Short help text at the bottom of a form](images/Gg886580.GeneralUITextGuidelines_01(AX.60).png "Short help text at the bottom of a form")Example of short Help text at the bottom of a form

Follow these guidelines for short Help:

  - Short Help text should have no more than 100 characters, including spaces. To view the word count, you can highlight the words in a Microsoft Word file, and then click **Word Count** on the **Review** tab.

  - If short Help text consists of only one sentence, do not end that sentence with a period. If it consists of two sentences, end both sentences with a period. Use only one space after a period.

  - Do not use parentheses in short Help text.

  - Do not write short Help text in the form of a question.

  - Do not use the word "default" as a noun in short Help text.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>The default font is Arial.</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Incorrect</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Arial is the default.</p></td>
    </tr>
    </tbody>
    </table>


  - For check boxes or buttons that represent a choice or a command, always use a verb phrase, such as "Open the selected transaction".

  - For fields that the user enters information into or selects an item from, or for buttons that only open another form or dialog box, use a noun phrase, such as "Name of the user account".

  - For fields that are view only, do not start the short Help text with a verb; instead, start the short Help text with "The \<type of item\>…" or "A \<type of item\>…".

  - To help people who localize and people for whom English is a second language, make short Help text as grammatically clear as possible. Use the articles *a*, *an*, and *the*, prepositions, such as *of*, and demonstrative pronouns, such as *this* and *that*, wherever possible.

## General message guidelines

This section contains general information about the following message types:

  - Error messages

  - Message bar messages

  - Message dialogs

  - Infolog messages

### Error messages

Use error messages to inform the user of errors that occur. Follow these guidelines for all types of error messages:

  - State the situation first. Then provide the resolution. Error messages should be in the format of what is and what can or cannot be done.

  - Use a period in error message text, even if there is only one sentence. If there are multiple sentences, use only one space after the periods, not two.

  - Do not concatenate messages. Concatenated messages can be difficult to translate because the sentence structure may be different in other languages.

  - Use variables (%1) to include data in a message. Include the field name for the data immediately preceding the variable, for example, "Purchase order %1 cannot be updated."

  - You can use variables (%1) to include field names or table names in a message. Include the field name in single quotation marks. Include the word "field" immediately preceding the variable, for example, "The value %1 in field ‘%2’ is not found in relating table ‘%3’."

### Message bar messages

Use a message bar message to inform the user of a condition that is related to the field or record that currently has focus, or to inform the user of workflow status issues.

Example of a message bar message

  
![Message bar message](images/Gg886580.GeneralUITextGuidelines_02(AX.60).png "Message bar message")Example of a message bar message

### Message dialogs

Use a message dialog when the user must make a decision before continuing. Follow these guidelines for message dialogs:

  - The first sentence of a message dialog should explain the situation.

  - The second sentence should ask what action the user wants to take.

  - For ease of translation, use the articles *a*, *an*, and *the*, prepositions such as *of*, and demonstrative pronouns such as *this* and *that*.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Selection has been changed. Do you want to cancel the update?</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Incorrect</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Selection has been changed. Cancel update?</p></td>
    </tr>
    </tbody>
    </table>


  - If possible, use descriptive button names that indicate what action will be taken.

For more information about message dialogs, see the [Windows User Experience Interaction Guidelines](http://msdn.microsoft.com/en-us/library/aa511258.aspx).

### Infolog messages

Infolog messages are presented in the **Infolog** form, which does not give the user very much context about the situation. Therefore, strive to make Infolog messages as informative as possible. Include the ID of the record that the message is about.

Use the following guidelines to decide what type of Infolog message to use:

  - **Infolog information messages**
    
    Use an Infolog information message to provide information that does not require the user to take any action.

  - **Infolog warning messages**
    
    Use an Infolog warning message to provide information that requires the user to take action.
    
    Explain what the problem is. Then explain what the user should do about it.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>The value ‘%1’ in field ‘%2’ is not found in relating table ‘%3’.</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Better</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>The value ‘%1’ in field ‘%2’ is not found in relating table ‘%3’. Right-click and select ‘View details’ to add a record.</p></td>
    </tr>
    </tbody>
    </table>


  - **Infolog error messages**
    
    Use an Infolog error message to provide information about a process that could not be completed.

