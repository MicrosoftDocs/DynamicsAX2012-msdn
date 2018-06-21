---
title: 'How to: Add a Collapsible and Expandable Section'
TOCTitle: 'How to: Add a Collapsible and Expandable Section'
ms:assetid: 8cef6086-1e82-4179-86b0-ddc124a210b5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn155873(v=AX.60)
ms:contentKeyID: 53906253
ms.date: 04/29/2013
mtps_version: v=AX.60
dev_langs:
- html
---

# How to: Add a Collapsible and Expandable Section [AX 2012]


You can add collapsible and expandable sections to a content element. A collapsible section temporarily hides part of the content element when you click the section title. When collapsed, the section title is visible but the content is hidden. If you click the title again, the hidden content reappears. You can also collapse and expand a section by clicking the heading and then pressing the Enter key. You add collapsible sections when you want the user to select the amount of documentation that appears in the Help viewer.

To add a collapsible and expandable section, you add a function that runs when you click the section title. The Microsoft Dynamics AX Help documentation uses a Jscript function named ExpandCollapse. You can find the function in a file that is named script\_manifold.js. This file and the other files that are used to add collapsible and expandable sections are found in the following folder of the Help server:

    C:\inetpub\wwwroot\DynamicsAX6HelpServer\Content\Microsoft\EN-US\Local\

You may want to copy the Local folder to the folder where you publish your content. This makes it easier to specify names and locations for the Jscript and image files you will use. The following steps describe how to add a collapsible and expandable section.

### To Add a Collapsible and Expandable Section

1.  Add a \<script\> element to the \<head\> of the HTML document. Use the attributes of the \<script\> element to add a reference to the file that contains the ExpandCollapse function. The following table shows the attributes and values that you use to add the reference to the script\_manifold.js file.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Attribute</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>type</p></td>
    <td><p>text/javascript</p></td>
    </tr>
    <tr class="even">
    <td><p>src</p></td>
    <td><p>Specify the location of the script_manifold.js file.</p>
    <p>Typically, you use a relative path. A relative path specifies how to get from the folder where the content element is published to the location of the script_manifold.js file.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following code example adds the \<script\> element. Notice how the src attribute specifies the relative path of the script\_manifold.js file. In this example, the folder that contains this content element and the local folder will have a common parent folder. You might have to change the src value to reflect the location of these files on your Help server.
    
    ``` html
    <script type="text/javascript" src="../local/script_manifold.js"></script>
    ```

2.  Add two \<img\> elements to the \<body\> of the HTML document. You use the images to help identify collapsible and expandable sections. Use the collapse\_all.gif and expand\_all.gif images from the local folder. The following table shows the attributes and values that you use to add the images.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Attribute</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>id</p></td>
    <td><p>Specify collapseImage for one &lt;img&gt; and expandImage for the second &lt;img&gt; element.</p></td>
    </tr>
    <tr class="even">
    <td><p>style</p></td>
    <td><p>display:none</p></td>
    </tr>
    <tr class="odd">
    <td><p>height</p></td>
    <td><p>0</p></td>
    </tr>
    <tr class="even">
    <td><p>width</p></td>
    <td><p>0</p></td>
    </tr>
    <tr class="odd">
    <td><p>src</p></td>
    <td><p>Specify the location of the image file. Use collapse_all.gif for the element that has the id of collapseImage. Use expand_all.gif for the element that has the id of expandImage.</p>
    <p>Typically, you use a relative path. A relative path specifies how to get from the folder where the content element is published to the location of the image file.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following code example adds two \<img\> elements. Notice how the src attributes specify the relative path of each image file. In this example, the folder that contains this content element and the local folder will have a common parent folder. You might have to change the src value to reflect the location of these files on your Help server.
    
    ``` html
    <img id="collapseImage" style="display:none; height:0; width:0;" src="../local/collapse_all.gif" alt="" title="" />
    <img id="expandImage" style="display:none; height:0; width:0;" src="../local/expand_all.gif" alt="" title="" />
    ```

3.  Add an \<h1\> element to the \<body\> of the HTML document. Use the \<h1\> element to add the section title.
    
    The following code example adds the \<h1\> element. The section will have the title **Collapsible section heading**. You may notice that the \<h1\> element includes a class attribute. The value of class specifies style information for the title.
    
    ``` html
    <h1 class="heading">Collapsible section heading</h1>
    ```

4.  Add a \<span\> element after the \<h1\> element from the previous step. Add \<span\> and \</span\> so that it surrounds the text you specified for the section title.
    
    Add attributes to the \<span\> element that associate functions from the script\_manifold.js file together with onclick and onkeypress events. The following table shows the attributes and values that you use to specify the events and functions.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Attribute</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>onclick</p></td>
    <td><p>ExpandCollapse(imageItem)</p></td>
    </tr>
    <tr class="even">
    <td><p>style</p></td>
    <td><p>cursor:default;</p></td>
    </tr>
    <tr class="odd">
    <td><p>onkeypress</p></td>
    <td><p>ExpandCollapse_CheckKey(imageItem, event)</p></td>
    </tr>
    <tr class="even">
    <td><p>tabindex</p></td>
    <td><p>0</p></td>
    </tr>
    </tbody>
    </table>
    
    The following code example adds the \<span\> element. Notice how the values of the onclick and onkeypress attributes specify functions. Also notice how the \<span\> includes the **Collapsible section heading** text from the example in the previous step.
    
    ``` html
    <h1 class="heading">
    <span onclick="ExpandCollapse(imageItem)" style="cursor:default;" onkeypress="ExpandCollapse_CheckKey(imageItem, event)" tabindex="0">Collapsible section heading</span>
    </h1>
    ```

5.  Add an \<img\> element after the \<span\> element from the previous step. The image will appear in the Help viewer next to the section title and shows that the section is collapsible. Use the collapse\_all.gif that is used by existing content elements.
    
    To add the image, you add attributes and values to the \<img\> element that specify the file that contains the image. The following table shows the attributes and values that you use for the collapsible section image.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Attribute</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>id</p></td>
    <td><p>Specify a value that uniquely identifies this element.</p></td>
    </tr>
    <tr class="even">
    <td><p>class</p></td>
    <td><p>toggle</p></td>
    </tr>
    <tr class="odd">
    <td><p>name</p></td>
    <td><p>toggleSwitch</p></td>
    </tr>
    <tr class="even">
    <td><p>src</p></td>
    <td><p>Specify the location of the collapse_all.gif file.</p>
    <p>Typically, you use a relative path. A relative path specifies how to get from the folder where the content element is published to the location of the collapse_all.gif file.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following code example adds the \<img\> element. Notice how the src attribute specifies the relative path of the collapse\_all.gif file. In this example, the folder that contains this content element and the local folder will have a common parent folder. You might have to change the src value to reflect the location of these files on your Help server.
    
    ``` html
    <h1 class="heading">
    <span onclick="ExpandCollapse(imageItem)" style="cursor:default;" onkeypress="ExpandCollapse_CheckKey(imageItem, event)" tabindex="0">
    <img id="sectionToggle0" class="toggle" name="toggleSwitch" src="../local/collapse_all.gif" />
    Collapsible section heading</span>
    </h1>
    ```

6.  Update the parameter values of the ExpandCollapse and ExpandCollapse\_CheckKey functions that you added to the \<span\> element. Replace the existing value with the value of the id attribute from the \<img\> element that you added in the previous step.
    
    The ExpandCollapse\_CheckKey function also includes a second parameter. Set the value of that parameter to event. The parameter specifies the key code of the key that was pressed.
    
    The following code example shows how to update the parameters of the ExpandCollapse and ExpandCollapse\_CheckKey functions. Notice how that the parameter values use sectionToggle0. The value is taken from the id attribute of the \<img\> element found in the code example of the previous step.
    
    ``` html
    <span onclick="ExpandCollapse(sectionToggle0)" style="cursor:default;" onkeypress="ExpandCollapse_CheckKey(sectionToggle0, event)" tabindex="0">
    ```

7.  Add a \<div\> element after the \<h1\> element. The contents of the \<div\> will disappear or reappear when you click the section title in the Help viewer. The ExpandCollapse function targets the element that is the next sibling of the \<h1\> element. Add your content between \<div\> and \</div\>.
    
    The following code example shows how to add the \<div\> element and adds a paragraph to that section. The value of the id attribute provides a unique name for the section.
    
    ``` html
    <h1 class="heading">
    <span onclick="ExpandCollapse(sectionToggle0)" style="cursor:default;" onkeypress="ExpandCollapse_CheckKey(sectionToggle0, event)" tabindex="0">
    <img id="sectionToggle0" class="toggle" name="toggleSwitch" src="../local/collapse_all.gif" />
    Collapsible section heading</span>
    </h1>
    
    <div id="sectionSection0">
    <p>The text in this section disappears and reappears when you click the section heading. </p>
    </div>
    ```

## Example

The following is a complete HTML code example for a content element that has a collapsible and expandable section. The example includes the code from the previous steps. Notice how the values of the src attributes have changed. The relative paths show that the elements for the collapsible and expandable section use Jscript and image files that are in the folder C:\\inetpub\\wwwroot\\DynamicsAX6HelpServer\\Content\\Microsoft\\EN-US\\Local\\. In addition, the paths reflect that this content element will be published to a folder on the Help server named C:\\inetpub\\wwwroot\\DynamicsAX6HelpServer\\Content\\Contoso.

``` html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"[]>
<html DIR="LTR" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:dynHelp="http://schemas.microsoft.com/dynamicsHelp/2008/11" xmlns:dynHelpAx="http://schemas.microsoft.com/dynamicsHelpAx/2008/11" xmlns:MSHelp="http://msdn.microsoft.com/mshelp" xmlns:mshelp="http://msdn.microsoft.com/mshelp" xmlns:ddue="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:msxsl="urn:schemas-microsoft-com:xslt">
<head>

  <script type="text/javascript" src="../Microsoft/EN-US/local/script_manifold.js"></script>

  <title>Code Example</title>
  <meta name="Title" content="Code example" />
  <meta name="Microsoft.Help.Id" content="3FFFC1DB-6CF5-41E6-8331-096313C157E0" />
  <meta name="ms.locale" content="EN-US" />
  <meta name="publisher" content="Contoso" />
  <meta name="documentSets" content="UserDocumentation" />
  <meta name="Microsoft.Help.Keywords" content="Contoso" />
  <meta name="suppressedPublishers" content="" />
  <meta name="Microsoft.Help.F1" content="ContosoCodeExample" />
  <meta name="description" content="A basic code example of a section that can collapse and expand." />
  
  <style type="text/css">
    .style1
    {
      font-weight: normal;
      font-family: "Segoe UI";
    }
  </style>

  <link rel="stylesheet" type="text/css" href="../Microsoft/EN-US/local/presentation.css" />
  <link rel="stylesheet" type="text/css" href="../Microsoft/EN-US/local/AX.css" />

</head>

<body>

  <img id="collapseImage" style="display:none; height:0; width:0;" src="../Microsoft/EN-US/local/collapse_all.gif" alt="" title="" />
  <img id="expandImage" style="display:none; height:0; width:0;" src="../Microsoft/EN-US/local/expand_all.gif" alt="" title="" />

  <div id="header">
      <table id="bottomTable">
          <tr id="headerTableRow2">
              <td align="left">
                  <h1>
                      <span id="nsrTitle">Code Example</span>
                  </h1>
              </td>
          </tr>
      </table>

      <hr class="title-divider" />
  </div>

  <div id="mainSection">

    <div id="mainBody">
      <div id="allHistory" class="saveHistory" onsave="saveAll()" onload="loadAll()" />

      <div class="introduction">
        <p>This code example shows how to create a section that you can collapse or expand with a click on the section heading.</p>
      </div>

      <h1 class="heading">
        <span onclick="ExpandCollapse(sectionToggle0)" style="cursor:default;" onkeypress="ExpandCollapse_CheckKey(sectionToggle0, event)" tabindex="0">
          <img id="sectionToggle0" class="toggle" name="toggleSwitch" src="../Microsoft/EN-US/local/collapse_all.gif" />
          Click to collapse or expand the section
        </span>
      </h1>
    
      <div id="sectionSection0">
        <p>The text in this section disappears and reappears when you click the section heading. </p>
      </div>

    </div>
  </div>

</body>
</html>
```

## See also

[Authoring Help Documents](authoring-help-documents.md)

