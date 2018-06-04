---
title: Common Context Scenarios
TOCTitle: Common Context Scenarios
ms:assetid: 87b020d6-a25c-4ee1-a323-fc0eb47dfc28
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee330228(v=AX.60)
ms:contentKeyID: 35589412
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Common Context Scenarios 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To understand context in Enterprise Portal, it is helpful to look at how common scenarios are configured. These scenarios use the built-in functionality for context. They do not require you to write any code.

## Passing Context into a Web Page

In this scenario, the user has chosen an action that causes a new page in Enterprise Portal to be displayed. The data displayed in the new page is determined by the context that is passed in to the page. This scenario is used as context is passed into Entity Overview pages and Task pages.

![Passing Context into a Web Page](images/Ee330228.EP_ContextIntoPage(AX.60).gif "Passing Context into a Web Page")

The context is passed into the page through the URL. All of the web parts on the page that have been set to the Provider role will retrieve the context from the URL. The AxDataSource User Control components that are set to be in the Consumer role will retrieve the context from the web part and set the current row. Any other User Control components that are linked to the AxDataSource, such as an AxForm, will display the current record.


> [!NOTE]
> <P>Information about how to view the context passed on the URL is discussed in <A href="how-to-view-context-in-enterprise-portal.md">How to: View Context in Enterprise Portal</A>.</P>



## Action Pane and User Control Web Parts

In this scenario, an Action Pane web part is used to perform actions for the item selected or displayed in a User Control web part on the page. It is important to note that the action pane is located in a separate web part on the web page. The Action Pane web part passes the context to the new page where the action is to be performed. This scenario is used for Entity Overview and Task pages.

![Action Pane and User Control](images/Ee330228.EP_ContextActionPaneAndForm(AX.60).gif "Action Pane and User Control")

Within the User Control web part, an AxDataSource is set to the Provider role. The AxDataSource will provide context based on the record it is currently accessing, which is typically the record displayed in an AxForm. The User Control web part is also set to the Provider role. This allows it to use web part communication to send the AxContextList to the Action Pane web part. When the user chooses a command, the Action Pane web part passes the context through the URL of the new page it is displaying.

## Toolbar and User Control Web Parts

In this scenario, a Toolbar web part is used to perform actions for the item selected or displayed in a User Control web part on the page. It is important to note that the toolbar is located in a separate web part on the web page. The Toolbar web part passes the context to the new page where the action is to be performed. This scenario was used extensively for List pages in Microsoft Dynamics AX 2009. It is still supported in Microsoft Dynamics AX 2012, but is not used often.

![Toolbar and User Control](images/Ee330228.EP_ContextToolbarAndGrid(AX.60).gif "Toolbar and User Control")

Within the User Control web part, an AxDataSource is set to the Provider role. The AxDataSource will provide context based on the record it is currently accessing, which is typically specified by the selection the user made in the AxGridView. The User Control web part is also set to the Provider role. This allows it to use web part communication to send the AxContextList to the Toolbar web part. When the user chooses a menu item, the Toolbar web part passes the context through the URL of the new page it is displaying.

## Hyperlink Field in an AxGridView Control

This scenario is an extension of the previous scenario. Often, the AxGridView component of a User Control has key fields that have been converted into AxHyperLinkBoundField controls. When the user clicks the hyperlink field, a new page is opened and the context is passed on the URL. The AxHyperLink field in the AxGridView passes on the context from the AxDataSource that is pointing to the selected row in the grid.

![Hyperlink Field in an AxGridView Control](images/Ee330228.EP_ContextHyperlinkField(AX.60).gif "Hyperlink Field in an AxGridView Control")

## Toolbar and AxGridView User Control Components

In this scenario, the AxToolbar and the AxGridView components are used within a User Control. It is important to note in this scenario that the toolbar is not located in a separate web part on the page. Both components are within a single web part, so no web part communication is required. Both the AxToolbar and the AxGridView point to the same AxDataSource component. When the user chooses an item from the AxToolbar, the context for the current row in the AxDataSource is passed with the URL of the new page to display.

![User Control with Toolbar and AxGridView](images/Ee330228.EP_ContextUserControlWithToolbar(AX.60).gif "User Control with Toolbar and AxGridView")


> [!TIP]
> <P>This same scenario can be applied when an AxActionPane and AxGridView components are used within a User Control.</P>



## User Controls on the Same Web Page

In this scenario, several User Control web parts are on the same web page. When the user selects an item in one of the web parts, the context information will be passed to the other web parts so they can display the data that corresponds to the selection.

![User Controls on the Same Web Page](images/Ee330228.EP_ContextWebPartsOnPage(AX.60).gif "User Controls on the Same Web Page")

In the web part in which the user makes a selection, the AxDataSource component is set to the Provider role. This allows it to provide the context of the selected record to the other web parts on the page. The User Control web part is also set to the Provider role. This allows it to use web part communication to send the AxContextList to the other web parts on the page. The other web parts on the page are set to the Consumer role, so they can receive the context. The AxDataSource components within those web parts are also set to the Consumer role so they will set their value based on the context that was passed to the web part.

