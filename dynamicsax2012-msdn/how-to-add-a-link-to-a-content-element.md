---
title: 'How to: Add a Link to a Content Element'
TOCTitle: 'How to: Add a Link to a Content Element'
ms:assetid: 5ab20dc1-1a85-4290-92a5-bbb59feaca61
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn155872(v=AX.60)
ms:contentKeyID: 53906254
ms.date: 04/29/2013
mtps_version: v=AX.60
dev_langs:
- html
---

# How to: Add a Link to a Content Element [AX 2012]


A link is the blue text that appears in the Help viewer that you click to view related Help documentation. A link provides access to other important information that helps you complete a task. You can add a link when you create or update Help documentation for the Help server. You use the link to specify the documentation you want the user to see. The sections that follow show how to add links that can open the following types of documentation:

  - A content element found on the Help server.

  - A document found on an internal or external web site.


> [!WARNING]
> <P>The link guidelines in the following sections do not work with the Word template. To add a link in the template, you use Word to insert a hyperlink. For information about the Word template, see <A href="using-templates-to-create-documentation.md">Using Templates to Create Documentation</A>.</P>



## Creating a link to a document on the Help server

This section describes how to add a link that opens a content element that is published on the Help server. The following table describes the two types of HTML elements that you can use to add a link.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Element</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;dynHelp:topicLink&gt;</p></td>
<td><p>The &lt;dynHelp:topicLink&gt; element is an HTML element that is unique to Microsoft Dynamics AX Help. You use this element when the content element that has the link and the content element that the link opens are published to the same Help server. You use the attributes of the element to specify the content element you want the link to open. You cannot use the &lt;dynHelp:topicLink&gt; element to link to a document on another web site.</p>
<p>A link that uses the &lt;dynHelp:topicLink&gt; element will appear disabled in most HTML editors or Web browsers. However, the link will appear enabled when you view the content element in the Help viewer. If you view the HTML of the content element that appears in the Help viewer, you will notice that the &lt;dynHelp:topicLink&gt; element has been converted to an HTML &lt;a&gt; element. The Help server performs the conversion when the content element is sent to the Help viewer.</p></td>
</tr>
<tr class="even">
<td><p>&lt;a&gt;</p></td>
<td><p>The HTML &lt;a&gt; element is the element you use to create a link in a standard HTML document. You use this element when you want to be able to click the link from an application other than the Help viewer. For example, you want to use the link from an HTML editor or Web browser. To create the link, you have to specify the URL for the content element that you want the link to open.</p>
<p>You can also use an &lt;a&gt; element to link to a document on an internal or external web site. For more information, view the section that describes how to create a link to a document on a web site.</p></td>
</tr>
</tbody>
</table>


The following procedures show how to create a link with the \<dynHelp:topicLink\> element or the \<a\> element. Choose the procedure that matches the type of link you want to use. The following steps show how to use the \<dynHelp:topicLink\> element.

### To add the \<dynHelp:topicLink\> element to the HTML file

1.  Find the Microsoft.Help.F1 document property for the content element that you want the link to open. Microsoft.Help.F1 is a required document property that you can find in a \<meta\> element in the \<head\> section of any content element. To create the link, use the value assigned to the content attribute. If the content attribute has more than one value, use any one of the listed values.
    
    To find the Microsoft.Help.F1 value, open the content element you want to link to in the Help viewer, right-click the viewing pane, and then click View source. The HTML for the content element appears in an HTML or text editor. Use the editor to search for **Microsoft.Help.F1**.
    
    The following code example shows the Microsoft.Help.F1 document property from the default Help topic. Notice how the content attribute lists three ID values. You will use one of these values in the link.
    
    ``` html
    <meta name="Microsoft.Help.F1" content="default_aot_topic; DEFAULT_TOPIC; bd46c98a-04bd-41d8-a210-4bbc08dd7d62" />
    ```

2.  Use an HTML or text editor to open the file for the content element where you want to add the link. Move to the location in the HTML where you want the link to appear.

3.  Add a span element together with an sdata attribute. Set the value of the sdata attribute to link. The attribute helps ensure that links in the Help viewer have a consistent appearance. The following code example adds the \<span\> element and sets the value of the sdata attribute.
    
    ``` html
    <span sdata="link"> </span>
    ```

4.  Add the \<dynHelp:topicLink\> element between \<span\> and \</span\> from the previous step. Add the text for the link between \<dynHelp:topicLink\> and \</dynHelp:topicLink\>. The following code example shows how to add the \<a\> element and text. The text for the link will appear as **Using Help for Microsoft Dynamics AX**.
    
    ``` html
    <span sdata="link"><dynHelp:topicLink>Using Help for Microsoft Dynamics AX</dynHelp:topicLink></span>
    ```

5.  Add attributes to the \<dynHelp:topicLink\> element that specify the content element you want the link to open. The following table shows the attributes and values that you have to add.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Name</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>topicId</p></td>
    <td><p>Specify the Microsoft.Help.F1 value of the content element that you want the link to open in the Help viewer.</p></td>
    </tr>
    <tr class="even">
    <td><p>documentSet</p></td>
    <td><p>UserDocumentation</p></td>
    </tr>
    </tbody>
    </table>
    
    The following code example adds the \<dynHelp:topicLink\> element. Notice how topicId specifies the GUID value from the example in the earlier step. Also notice how documentSet is set to UserDocumentation.
    
    ``` html
    <span sdata="link"><dynHelp:topicLink topicId="bd46c98a-04bd-41d8-a210-4bbc08dd7d62" documentSet="UserDocumentation">Using Help for Microsoft Dynamics AX</dynHelp:topicLink></span>
    ```

6.  Save the changes to the HTML file.

The following steps show how to use the \<a\> element. However, you should use the \<dynHelp:topicLink\> element and the previous procedure whenever possible.

### To add the \<a\> element to the HTML file

1.  Find the Microsoft.Help.F1 and ms.locale document properties for the content element that you want the link to open. Microsoft.Help.F1 and ms.locale are required document properties that you can find in the \<meta\> elements in the \<head\> section of any content element. To create the link, you will use the value assigned to the content attribute of both elements. If the content attribute of Microsoft.Help.F1 has more than one value, you can use any one of the listed values.
    
    To find the Microsoft.Help.F1 and ms.locale values, you can open the content element you want to link to in the Help viewer, right-click the viewing pane, and then click **View source**. The HTML for the content element appears in an HTML or text editor. Use the editor to search for **Microsoft.Help.F1** and **ms.locale**.
    
    The following code example shows the Microsoft.Help.F1 and ms.locale document properties from the default Help topic. Notice how the content attribute for Microsoft.Help.F1 lists three ID values. You will use one of these values in the link.
    
    ``` html
    <meta name="Microsoft.Help.F1" content="default_aot_topic; DEFAULT_TOPIC; bd46c98a-04bd-41d8-a210-4bbc08dd7d62" />
    <meta name="ms.locale" content="EN-US" />
    ```

2.  Use an HTML or text editor to open the file for the content element where you want to add the link. Move to the location in the HTML where you want the link to appear.

3.  Add a span element together with an sdata attribute. Set the value of the sdata attribute to link. The attribute helps ensure that links in the Help viewer have a consistent appearance. The following code example adds the \<span\> element and sets the value of the sdata attribute.
    
    ``` html
    <span sdata="link"> </span>
    ```

4.  Add the \<a\> element between \<span\> and \</span\>. Add the text for the link between \<a\> and \</a\>. The following code example shows how to add the \<a\> element and text. The text for the link will appear as **Using Help for Microsoft Dynamics AX**.
    
    ``` html
    <span sdata="link"><a>Using Help for Microsoft Dynamics AX</a></span>
    ```

5.  Add the href attribute to the \<a\> element. Set the value of the attribute to the URL of the content element that you want the link to open. The following table describes the URL and query string parameters you use to specify the content element:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>URL</p></td>
    <td><p>Specify the URL for the Topic.aspx page from the Help server. For example, http://HelpServerName/DynamicsAX6HelpServer/Topic.aspx? where HelpServerName is the name of the server where you installed the Help server.</p></td>
    </tr>
    <tr class="even">
    <td><p>DocumentSet</p></td>
    <td><p>Specify the name of the documentation set. For documents on the Help server, always set this to <strong>UserDocumentation</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Ids</p></td>
    <td><p>Specify the ID of the content element. You use the value of the content attribute for the Microsoft.Help.F1 document property that you found in the earlier step.</p></td>
    </tr>
    <tr class="even">
    <td><p>ContentLanguage</p></td>
    <td><p>Specify the language code for the content element. You use the value of the ms.locale document property that you found in the earlier step.</p></td>
    </tr>
    <tr class="odd">
    <td><p>ResourceLanguage</p></td>
    <td><p>Specify the language code to use for the labels that appear in the content element. Typically, this is the same language code you used for ContentLanguage.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following code example shows how to add the href attribute to the \<a\> element. Notice how the URL specifies Topic.aspx on the Help server named HelpServerName. Also notice how the query string parameters identify the content element and that each parameter is separated with \&amp;.
    
    ``` html
    <span sdata="link"><a href="http://HelpServerName/DynamicsAX6HelpServer/Topic.aspx?DocumentSet=UserDocumentation&amp;Ids=bd46c98a-04bd-41d8-a210-4bbc08dd7d62&amp;ContentLanguage=EN-US&amp;ResourceLanguage=EN-US">Using Help for Microsoft Dynamics AX</a></span>
    ```

6.  Save the HTML file.

## Creating a link to a document on a web site

This section describes how to add a link that opens a document that is published to an internal or external web site. You have to use the HTML \<a\> element for any document that is not on the Help server. The \<a\> element is the same element you use to create a link in a standard HTML document. To create the link, you add an attribute and specify the URL for the document. A link to a document from a web site will cause that document to open in a Web browser window and not the Help viewer.

### To add the \<a\> element to the HTML file

1.  Find the URL of the document that you want the link to open. To create the link, you will use the URL value to specify the document.
    
    For example, you could use http://msdn.microsoft.com to open the default page from the specified web site.

2.  Use an HTML or text editor to open the file for the content element where you want to add the link. Move to the location in the HTML where you want the link to appear.

3.  Add a span element together with an sdata attribute. Set the value of the sdata attribute to link. The attribute helps ensure that links in the Help viewer have a consistent appearance. The following code example adds the \<span\> element and sets the value of the sdata attribute.
    
    ``` html
    <span sdata="link"> </span>
    ```

4.  Add the \<a\> element between \<span\> and \</span\>. Add the text for the link between \<a\> and \</a\>. The following code example shows how to add the element and text. The text for the link will appear as **View MSDN**.
    
    ``` html
    <span sdata="link"><a>View MSDN</a></span>
    ```

5.  Add the href attribute to the \<a\> element. Set the value of the attribute to the URL of the document that you want to open. The following code example populates the href attribute with the URL example from the earlier step.
    
    ``` html
    <span sdata="link"><a href="http://msdn.microsoft.com">View MSDN</a></span>
    ```

6.  Save the HTML file.

## Example

The following code example shows a content element that has links that use both the \<dynHelp:topicLink\> and \<a\> elements. Notice that two of the links target the default Help topic and the third targets the MSDN web site. If you click **View MSDN**, the default page for MSDN opens in a Web browser window.

Notice how several elements include references to Jscript, CSS, or image files. These references use relative path information to specify the file. The path information indicates the referenced files are located in a Help server folder like C:\\inetpub\\wwwroot\\DynamicsAX6HelpServer\\Content\\Contoso\\Local\\. In addition, the paths reflect that this content element will be published to a Help server folder like C:\\inetpub\\wwwroot\\DynamicsAX6HelpServer\\Content\\Contoso\\EN-US\\. To use this code example, you might want to change the relative path information to reflect the location of the files on your Help server.

``` html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"[]>
<html DIR="LTR" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:dynHelp="http://schemas.microsoft.com/dynamicsHelp/2008/11" xmlns:dynHelpAx="http://schemas.microsoft.com/dynamicsHelpAx/2008/11" xmlns:MSHelp="http://msdn.microsoft.com/mshelp" xmlns:mshelp="http://msdn.microsoft.com/mshelp" xmlns:ddue="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:msxsl="urn:schemas-microsoft-com:xslt">
<head>
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=UTF-8" />
    <META NAME="save" CONTENT="history" />
    
    <title>Link test for documentation </title>
    
    <link rel="stylesheet" type="text/css" href="../local/presentation.css" />
    <link rel="stylesheet" type="text/css" href="../local/AX.css" />

    <script type="text/javascript" src="../local/script_manifold.js"></script>

    <meta name="Title" content="Link test for documentation" />
    <meta name="Microsoft.Help.Id" content="LinkTestForDoc" />
    <meta name="ms.locale" content="EN-US" />
    <meta name="publisher" content="Contoso" />
    <meta name="documentSets" content="UserDocumentation" />
    <meta name="Microsoft.Help.Keywords" content="LinkTest" />
    <meta name="suppressedPublishers" content="" />
    <meta name="Microsoft.Help.F1" content="LinkTestForDoc" />
    <meta name="description" content="Examples of link elements to use when customizing documentation." />
</head>
<body>
    <input type="hidden" id="userDataCache" class="userDataStyle" />
    <input type="hidden" id="hiddenScrollOffset" />
    
    <img id="collapseImage" style="display:none; height:0; width:0;" src="../local/collapse_all.gif" alt="" title="" />
    <img id="expandImage" style="display:none; height:0; width:0;" src="../local/expand_all.gif" alt="" title="" />
    
    <div id="header">
        <table id="topTable">
            <tr><td><span onclick="ExpandCollapseAll(toggleAllImage)" style="cursor:default;" onkeypress="ExpandCollapseAll_CheckKey(toggleAllImage, event)" tabindex="0"><img ID="toggleAllImage" class="toggleAll" src="../local/collapse_all.gif" /> <label id="collapseAllLabel" for="toggleAllImage" style="display: none;">Hide all</label><label id="expandAllLabel" for="toggleAllImage" style="display: none;">Show all</label> </span></td></tr>
        </table>

        <table id="bottomTable">
            <tr id="headerTableRow1"><td align="left"><span id="runningHeaderText" /></td></tr>
            <tr id="headerTableRow2"><td align="left"><span id="nsrTitle">Link test for documentation </span></td></tr>
        </table>
        
        <hr class="title-divider" />
    </div>
    <div id="mainSection">
        <div id="mainBody">
            <div id="allHistory" class="saveHistory" onsave="saveAll()" onload="loadAll()" />
        
            <div class="introduction">
                <p>Use this topic to test the types of links you can add to a content element. </p>
            </div>
                
            <h1 class="heading"><span onclick="ExpandCollapse(sectionToggle0)" style="cursor:default;" onkeypress="ExpandCollapse_CheckKey(sectionToggle0, event)" tabindex="0"><img id="sectionToggle0" class="toggle" name="toggleSwitch" src="../local/collapse_all.gif" />Microsoft Dynamics AX links</span></h1>
            <div id="sectionSection0" class="section" name="collapsibleSection" style="">
            
                <p>The following Dynamics AX link opens the default documentation page in the Help viewer: </p>
                <p><span sdata="link"><dynHelp:topicLink topicId="bd46c98a-04bd-41d8-a210-4bbc08dd7d62" documentSet="UserDocumentation">Using Help for Microsoft Dynamics AX</dynHelp:topicLink></span></p>
                <p>If you right-click this content element, and then click View source, you will notice that this link is converted to an HTML link when the topic appears in the Help viewer. </p>

            </div>

            <h1 class="heading"><span onclick="ExpandCollapse(sectionToggle1)" style="cursor:default;" onkeypress="ExpandCollapse_CheckKey(sectionToggle1, event)" tabindex="0"><img id="sectionToggle1" class="toggle" name="toggleSwitch" src="../local/collapse_all.gif" />HTML links</span></h1>
            <div id="sectionSection1" class="section" name="collapsibleSection" style="">
                
                <p>The following HTML link opens the default documentation page in the Help viewer: </p>
                <p><span sdata="link"><a href="http://HelpServerName/DynamicsAX6HelpServer/Topic.aspx?DocumentSet=UserDocumentation&amp;Ids=bd46c98a-04bd-41d8-a210-4bbc08dd7d62&amp;ContentLanguage=EN-US&amp;ResourceLanguage=EN-US">Using Help for Microsoft Dynamics AX</a></span></p>
                
                <p>The following HTML link opens MSDN in a web browser window: </p>
                <p><span sdata="link"><a href="http://msdn.microsoft.com">View MSDN</a></span></p>

            </div>
            
        </div>
        <div id="footer">
            <div class="footerLine"><img width="100%" height="3px" src="../local/footer.gif" alt="" title="" /></div>
        </div>
    </div>
</body>
</html>
```

## See also

[Authoring Help Documents](authoring-help-documents.md)

