---
title: HTML Utilities
TOCTitle: HTML Utilities
ms:assetid: 083279fc-3ce4-4ba8-a125-c11326643726
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812490(v=AX.60)
ms:contentKeyID: 44090276
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# HTML Utilities [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Enterprise Portal provides several methods in the Microsoft.Dynamics.AX.Framework.Utilities class that are useful when you must work with HTML in the code for a User Control. Some of the methods are used to improve security. Others are used to make sure that string values are encoded correctly when they are used.

## Improving Security for User Controls

When you write code for User Controls, some of your code may generate raw HTML. When you generate HTML that contains content from data that is outside of your control, such as user-defined data in table fields, you must take precautions to help secure your application.

### Encoding HTML

When you generate HTML that you want to display for the user, you must be careful about the source of the HTML. Without careful coding, your application could be vulnerable to tampering. The following example illustrates the type of issue to look for.

Assume that you have a \<div\> tag that you have added to the markup for your User Control.

\<div id="SampleDiv" runat="server"\>\</div\>

The following code for your User Control sets the HTML that is displayed by this \<div\> tag when the user clicks a button. For the purpose of this example, assume that the text to display comes from a table field that can be configured by a user. The user has set the table field to this value:

Hello world

When the user clicks the button in the User Control, the \<div\> will display the text "Hello world".

``` csharp
public void SecurityExample_Click(object sender, EventArgs e)
{
    // Assume the user_text value came from a table field
    string user_text = "Hello world";

    this.SampleDiv.InnerHtml = user_text;
}
```

Because only plain text is displayed, there is no obvious problem. But assume a malicious user had set the table field value to something such as the following:

\<a href='http://www.microsoft.com'\>Hello world\</a\>

Now when the user clicks the button in the User Control, a live link is added to the page. The malicious user was able to add unwanted HTML code to the page, just by changing the value that they supplied for the table field.

``` csharp
public void SecurityExample_Click(object sender, EventArgs e)
{
    // Assume the user_text value came from a table field
    string user_text = "<a href='http://www.microsoft.com'>Hello world</a>";

    this.SampleDiv.InnerHtml = user_text;
}
```

You can use the EncodeHtml method from the HtmlUtilities class to help reduce this kind of threat. The EncodeHtml method converts any special HTML characters into HTML entities that are displayed by the browser only as text. They cannot be interpreted as HTML commands.

The following example adds the EncodeHtml method to the previous example to help reduce this threat:

``` csharp
public void SecurityExample_Click(object sender, EventArgs e)
{
    // Assume the user_text value came from a table field
    string user_text = "<a href='http://www.microsoft.com'>Hello world</a>";

    // Encode the HTML to help mitigate the threat
    user_text = HtmlUtilities.EncodeHtml(user_text);

    this.SampleDiv.InnerHtml = user_text;
}
```

Now when the user clicks the button, the encoded version of the table field value (shown below) will be displayed in the \<div\>:

\&lt;a href='http://www.microsoft.com'\&gt;Text to display\&lt;/a\&gt;

Notice how all of the special characters in the HTML were converted to HTML entities. The user will see the following text displayed for the \<div\> element:

\<a href='http://www.microsoft.com'\>Text to display\</a\>

Most importantly, the potentially dangerous HTML will not be rendered as a link, but instead as plain text.


> [!TIP]
> <P>For a string that you will display on a page, it is a good practice to encode the string when you do not have complete control over its content.</P>



The EncodeHtml method is used to encode a string. If you want to convert an encoded string back into its original form, you can use the DecodeHtml method.

### Cleaning Unsafe HTML

If you work with a complete HTML document that does not come from a source that is completely under your control, the HTML may contain content that is potentially dangerous. For example, the HTML might contain \<script\> tags that are used for a cross-site scripting attack.

You can use the CleanupUnsafeHtml method from the HtmlUtilities class to remove potentially dangerous tags from HTML that you will display. The method removes things such as \<script\> tags to reduce the chances of a cross-site scripting attack. It is a good idea to use this method when you allow a full raw HTML document to be displayed. The following example shows how this method is used.

``` csharp
this._groupHeaderText = HtmlUtilities.CleanupUnsafeHtml(HTML_source);
```

## Encoding String Values

When code for a User Control generates strings that will be used for HTML attributes, URLs, XPath attributes, or JavaScript, you may to encode the string values so that they will work for the intended purpose. Several methods in the HtmlUtilities class are available to help with this.

### EncodeAttribute

If you create an attribute to use in an HTML element, the attribute could contain special characters. You must encode the string for the special characters to work correctly. The EncodeAttributeValue method replaces special characters in HTML attributes, such as quotation marks ("), ampersands (&), and less than signs (\<) so that invalid tags are not generated.

For example, the following code for a User Control builds a string to use as the href attribute for an HTML link. The EncodeAttributeValue method makes sure that any special characters are correctly encoded in the URL that is retrieved from the InventTable.

``` csharp
string s = string.Format("<a href={0}{1}{0}>{2}</a>", '"', HtmlUtilities.EncodeAttribute(GetProductDetailhref(inventTableRecId)), Labels.GetLabel("@SYS190991"));
```

### EncodeUrl

If you create a URL, the source strings could contain special characters. You must encode the string values for the special characters to work correctly. The EncodeURL method converts special characters such as spaces to the % followed by the two-digit hexadecimal representation. For example, a space becomes the string %20. Other special characters such as ampersands (&) and percents (%) are encoded also.

### EncodeXPathAttribute

If you create an XPath expression, the string values that you use for attributes may have special characters. You must encode the strings for the special characters to work correctly. The EncodeXPathAttribute method converts special characters in strings that will be used for XPath attributes.

### JavaScriptEncode

If you create strings to use in a JavaScript, the strings could contain special characters. To use strings that contain special characters, you must encode them. The JavaScriptEncode method converts special characters to their corresponding hexadecimal representation that can be used in a JavaScript. For example, a quotation mark (") becomes \\x22. An ampersand (&) becomes \\x26.

