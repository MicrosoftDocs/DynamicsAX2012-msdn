---
title: 'How to: Create Table of Contents Entries'
TOCTitle: 'How to: Create Table of Contents Entries'
ms:assetid: c184e978-77f3-43b6-a490-933beb1d9d7f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882385(v=AX.60)
ms:contentKeyID: 35257212
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- xml
---

# How to: Create Table of Contents Entries [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to add information to the table of contents that appears in the Microsoft Dynamics AX Help viewer. You typically add a table of contents entry when you add documentation that creates a new Help topic. To update the Help viewer, you publish an XML file that contains the entries you want to add to the table of contents. The following steps describe how to create the XML file.

### To create a TableOfContents.xml file

1.  Use a text or XML editor to create a new file.

2.  Use the text or XML editor to add the **xml** and **tableOfContents** elements to the file. The **tableOfContents** element requires that you add XML namespace information. The following XML example shows how to add the **xml** and **tableOfContents** elements.
    
    ``` xml
    <?xml version="1.0" encoding="utf-8"?>
    <tableOfContents xmlns="http://schemas.microsoft.com/dynamicsHelp/2008/11" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    </tableOfContents>
    ```

3.  Add metadata properties that specify a document set, language, and publisher. The help service uses these properties to identify the entries that appear in the table of contents of the help viewer. The following table describes how to populate the properties:
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Required</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>documentSet</p></td>
    <td><p>Yes</p></td>
    <td><p>Specify the ID of a document set. Typically, you set this property to <strong>UserDocumentation</strong>. The document set determines whether the entries appear in the table of contents for the application workspace, developer workspace, or both.</p></td>
    </tr>
    <tr class="even">
    <td><p>Ms.locale</p></td>
    <td><p>Yes</p></td>
    <td><p>Specify the language of the table of contents entries. Use a language code to identify the language. For example, use <strong>EN-US</strong> for United States English. The ms.locale property enables the Help viewer to display localized content.</p></td>
    </tr>
    <tr class="odd">
    <td><p>publisher</p></td>
    <td><p>No</p></td>
    <td><p>Specify the ID of the publisher. Table of contents entries are grouped by publisher.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following XML example adds the metadata properties. Notice how the metadata properties are child elements of the **tableOfContents** element.
    
    ``` xml
    <?xml version="1.0" encoding="utf-8"?>
    <tableOfContents xmlns="http://schemas.microsoft.com/dynamicsHelp/2008/11" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
       <publisher>Contoso</publisher>
       <documentSet>UserDocumentation</documentSet>
       <ms.locale>EN-US</ms.locale>
    </tableOfContents>
    ```

4.  Add the **entries** XML element. The **entries** element follows the metadata properties. The following XML example adds the **entries** element.
    
    ``` xml
    <publisher>Contoso</publisher>
    <documentSet>UserDocumentation</documentSet>
    <ms.locale>EN-US</ms.locale>
    <entries>
    </entries>
    ```

5.  Add an **entry** element for each topic that you want to add to the table of contents. The **entry** element must be a child element of the **entries** element that you added earlier. The following table describes how to populate the properties of an **entry** element.
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Required</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>text</p></td>
    <td><p>Yes</p></td>
    <td><p>Specify the text that appears in the help viewer.</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft.Help.F1</p></td>
    <td><p>No</p></td>
    <td><p>Specify one or more topic IDs that are associated with the entry. When you click an entry in the table of contents, the help viewer uses these IDs to request the content elements associated with that entry.</p></td>
    </tr>
    <tr class="odd">
    <td><p>children</p></td>
    <td><p>No</p></td>
    <td><p>Specify a hierarchy in the table of contents. Use the <strong>children</strong> element when you want to add one or more entry elements that appear in the help viewer as child elements of the current entry. The <strong>children</strong> element is optional.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following XML example adds an **entry** element to the table of contents. Notice how this entry specifies the use of the default help topic.
    
    ``` xml
    <entries>
       <entry>
          <text>Sample help topic</text>
          <Microsoft.Help.F1>DEFAULT_TOPIC</Microsoft.Help.F1>
       </entry>
    </entries>
    ```

6.  If you want the help viewer to display topics in a hierarchical structure, use the **children** element. The use of the **children** element is optional. Add the entries to the **children** element that you want to appear in the help viewer under the current entry. The following XML example uses **children** to add an entry.
    
    ``` xml
    <entry>
       <text>Sample help topic</text>
       <Microsoft.Help.F1>DEFAULT_TOPIC</Microsoft.Help.F1>
       <children>
          <entry>
             <text>Child help topic</text>
             <Microsoft.Help.F1>DEFAULT_TOPIC</Microsoft.Help.F1>
          </entry>
       </children>
    </entry>
    ```

7.  Use the text or XML editor to save the file. The file must be named **TableOfContents.xml**.
    

    > [!NOTE]
    > <P>You use the <STRONG>TableofContents.xml</STRONG> file to publish the new entries to the Help server. For more information about how to publish table of contents entries, see <A href="how-to-publish-table-of-contents-entries.md">How to: Publish Table of Contents Entries</A>.</P>



## Example

The following XML shows the basic structure of the **TableOfContents.xml** file.

``` xml
<?xml version="1.0" encoding="utf-8"?>
<tableOfContents xmlns="http://schemas.microsoft.com/dynamicsHelp/2008/11" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
<publisher>Contoso</publisher>
<documentSet>UserDocumentation</documentSet>
<ms.locale>EN-US</ms.locale>
<entries>
   <entry>
      <text>Sample help topic</text>
      <Microsoft.Help.F1>DEFAULT_TOPIC</Microsoft.Help.F1>
      <children>
         <entry>
            <text>Child help topic</text>
            <Microsoft.Help.F1>DEFAULT_TOPIC</Microsoft.Help.F1>
         </entry>
      </children>
   </entry>
</entries>
</tableOfContents>
```

## See also

[Authoring Help Documents](authoring-help-documents.md)

[How to: Publish Table of Contents Entries](how-to-publish-table-of-contents-entries.md)

