---
title: Context Sensitive Help
TOCTitle: Context Sensitive Help
ms:assetid: f69611b2-2f7d-4b31-b0c6-bb27dd91c170
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882389(v=AX.60)
ms:contentKeyID: 35257216
ms.date: 04/18/2014
mtps_version: v=AX.60
f1_keywords:
- Classes.SysHelpTopicId
---

# Context Sensitive Help 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Context-sensitive help is documentation that appears when you press the F1 key while you are viewing an object in the Microsoft Dynamics AX client or development workspace. Context-sensitive help provides information about the form, table, report, or other object that you are working with.

You can add context-sensitive help for many of the objects that appear in the Microsoft Dynamics AX client. To create context-sensitive help, you use an ID to associate a content element together with the specified object. If you view that object in the client and then press F1, your content element appears in the Help viewer. The following sections provide an overview of context-sensitive help.

## Objects that Support Context-Sensitive Help

The Microsoft Dynamics AX Help server supports context-sensitive help for the following types of client and development workspace objects.

  - Base Enums

  - Classes

  - Configuration keys

  - Data types

  - Forms

  - List Pages

  - Maps

  - Menu items

  - Parts

  - Reports

  - Tables

  - Views

## Viewing Context-Sensitive Help

To get context-sensitive help, you press F1 after you open a form, list page, or other object in the client workspace. When you press F1, the following actions occur.

  - The client sends the ID of each object that is currently open to the Help viewer application.

  - The Help viewer sends a request to the Help server. The request includes the object ID from the previous step. If there is more than one open object, the request includes a list of IDs. The IDs are listed in the order in which the objects were opened.

  - The Help server uses the object ID to create a query. The query searches for a content element that has a **Microsoft.Help.F1** property value that matches the specified object ID.

  - When the query finds a content element that has a **Microsoft.Help.F1** property value that matches the object ID, the Help server returns that documentation to the Help viewer. If the query finds content elements from more than one publisher, the Help server returns a list of links.
    

    > [!NOTE]
    > <P>A group of content elements that have the same value for the <STRONG>Microsoft.Help.F1</STRONG> property is called a topic. As a result, the <STRONG>Microsoft.Help.F1</STRONG> property is sometime called a topic ID.</P>



  - The Help viewer shows the documentation sent by the Help server. If the Help server found more than one content element, the Help viewer shows a list and prompts you to select the documentation you want to review.

## Query Rules for Context-Sensitive Help

The previous section describes a scenario where multiple open objects cause the Help viewer to send a list of object IDs to the Help server. The number and order of the IDs in the list can affect the documentation that appears in the Help viewer. When the Help server receives a list of IDs, it performs the following actions.

  - The Help server use the IDs in the list to create queries. The Help server starts with the first ID in the list. If that query does not find context-sensitive help for that object, the Help server creates a query with the next ID in the list.

  - The Help server returns context-sensitive help after the first successful query for an object ID. If the query finds context-sensitive help for an object that appears early in the list, you might not see the context-sensitive help that you expected.

  - If the Help server queries do not find a content element for any of the IDs, the Help server returns a message that no documentation was found.

For example, you click a button on the action pane of a list page that opens another form. The button uses a menu item to open the form. When you press F1, the Help viewer sends the ID of the list page, the menu item, and the form. The Help server then performs the following actions:

  - To begin, the Help server executes a query using the ID of the list page. If a content element has a **Microsoft.Help.F1** property that has a value that matches the list page ID, the Help server returns that documentation to the Help viewer. No additional queries are completed. As a result, context-sensitive help for the menu item or form will not appear in the Help viewer.

  - If no content element matches the list page ID, the Help server executes a query with the ID of the menu item. If a content element has a **Microsoft.Help.F1** property that has a value that matches the menu item ID, the Help server returns that documentation to the Help viewer. No additional queries are completed. As a result, context-sensitive help for the form will not appear in the Help viewer.

  - If no document matches the menu item ID, the Help server executes a query with the ID of the form. If a content element has a **Microsoft.Help.F1** property that has a value that matches the form ID, the Help server returns that documentation to the Help viewer.

## Creating Context-Sensitive Help

To make a content element context-sensitive, you populate the **Microsoft.Help.F1** property of the content element by using the ID of the client object. For example, a content element that provides context-sensitive help for the customer form would have a **Microsoft.Help.F1** property value of Forms.CustTable.

You can use more than one content element to provide context-sensitive help for a client object. As a result, you can add context-sensitive help for an existing object. For example, you want to add context-sensitive help for the customer form. You create a content element and populate the **Microsoft.Help.F1** property of that content element by using Forms.CustTable. When you press F1 from the customer form, the help viewer shows a summary page that lists the available content elements for the form. To view your documentation, you click the link in the summary page.

For more information about how to create a content element and populate the **Microsoft.Help.F1** and other document properties, see [Authoring Help Documents](authoring-help-documents.md).

## Finding the Object ID

To obtain the ID of an object, use one of the following approaches.

  - Find the object in the AOT and then right-click. In the shortcut menu, click **Add-Ins**, and then click **Help properties**. The **Help properties** window opens and displays the **Topic ID** for that object. Use this value to populate the **Microsoft.Help.F1** property of the context-sensitive content element.

  - You can get the object ID by knowing the path for that object in the AOT. To derive the ID, first locate the object in the AOT. The ID includes the name of each segment that you opened to view the object. Use a period to separate each AOT segment. Within a segment, replace any whitespace in the segment name with an underscore. The format is as follows:
    
    \<AOTElementType\>\[\_\<AOTSubType\>\].\<ElementName\>\[\_\<ElementProperty\>\]
    
    For example, the ID for the form named **Address** would be as follows:
    
    Forms.Address

  - You can also use the **Personalization** form to find the ID for a form or menu item. To begin, open the form, right-click on the form, and then click **Personalize**. To get ID values, click the **Information** tab. The **Form name** and **Menu item** fields show the ID for those objects.
    
    To use the ID in the **Microsoft.Help.F1** property of a content element, you have to provide the element type together with the ID from the **Personalization** form. For example, a form always includes Forms as the element type. To specify the ID for the customer form, you use Forms.CustTable.

## Using Context-Sensitive Help with Menu Items

You can associate context-sensitive help with menu items. The following examples show when you might add context-sensitive help for a menu item.

  - You have two menu items that open a form. You want the Help documentation to change depending on how the form is opened. As a result, you associate each menu item with a separate content element.

  - You add a menu item for an existing form. You know that there is existing context-sensitive help for the form and a related class that were produced by other publishers. However, you want your context-sensitive help to appear when you click F1 from the form. To make sure that your context-sensitive help appears in the Help viewer, you populate the **Microsoft.Help.F1** property of the content element by using the ID of the menu item. Since the menu item ID appears first in the list of IDs sent to the Help server, your Help documentation appears in the Help viewer instead of the documentation for the form or class.

However, not all forms open directly from a menu item. For example, you might have X++ code that uses a menu item to open a form. In this case, you have to be careful about how you use the menu item. If your code does not specifically include the menu item, the menu item ID is not included in the list of IDs sent to the Help server. As a result, any context-sensitive help associated with the menu item will not appear in the Help viewer.

The following X++ code example shows how to have the menu item included in the list of IDs. Notice how the MenuFunction object specifies the menu item, and then uses the create method to open the form.
```X++  
    purchRFQEditLines = new MenuFunction(menuitemDisplayStr(PurchRFQEditLines), MenutItemType::Display).create(FormLetter::newClientArgs(formStr(PurchRFQEditLines), this)); 
```
  


