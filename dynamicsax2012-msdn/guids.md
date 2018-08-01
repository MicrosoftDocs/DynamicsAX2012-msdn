---
title: GUIDs
TOCTitle: GUIDs
ms:assetid: 14ae701e-530b-48ed-a363-7f1292ce54ef
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967363(v=AX.60)
ms:contentKeyID: 35240606
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# GUIDs [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A GUID (a globally unique identifier) is a 16 byte, or a 128 bit integer that can be used across all computers and networks wherever a unique identifier is required. Such a number has a very low probability of being duplicated.

## String Representations of a GUID

Here are two examples of string literals that are valid representations of a GUID value:

  - "12345678-BBBb-cCCCC-0000-123456789012"

  - "{12345678-BBBb-cCCCC-0000-123456789012}"

The string representation of a GUID must follow the restrictions described in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Number of digits</p></td>
<td><p>Must have 32 hexadecimal digits.</p></td>
</tr>
<tr class="even">
<td><p>Dashes</p></td>
<td><p>Must have four dash characters embedded at the locations 8-4-4-4-12.</p></td>
</tr>
<tr class="odd">
<td><p>Braces</p></td>
<td><p>It is optional to have the string start and end with {} braces.</p></td>
</tr>
<tr class="even">
<td><p>Length</p></td>
<td><p>The string must have a total of either 36 or 38 characters, depending on whether braces are added.</p></td>
</tr>
<tr class="odd">
<td><p>Casing</p></td>
<td><p>The hexadecimal digits a-f (or A-F) can be either uppercase or lowercase, or mixed.</p></td>
</tr>
</tbody>
</table>


## GUID Functions

X++ functions that input or output the guid type are listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Function</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>any2guid</p></td>
<td><p>Converts an anytype to a guid.</p></td>
</tr>
<tr class="even">
<td><p>guid2str</p></td>
<td><p>Converts a guid to an str.</p></td>
</tr>
<tr class="odd">
<td><p>newGuid</p></td>
<td><p>Generates a random guid value.</p></td>
</tr>
<tr class="even">
<td><p>str2guid</p></td>
<td><p>Converts an str to a guid.</p></td>
</tr>
<tr class="odd">
<td><p>Global::guidFromString</p></td>
<td><p>Calls str2guid.</p></td>
</tr>
<tr class="even">
<td><p>Global::stringFromGuid</p></td>
<td><p>Calls guid2str.</p></td>
</tr>
</tbody>
</table>


## Example

The following X++ code example illustrates how to use the GUID functions.

```X++
    static void GuidRoundTripJob(Args _args)
    {
        guid guid2;
        str string3;
        ;
        // Convert a guid to a string, and back to a guid.
        guid2 = newGuid();
        info(strFmt("Info_a1:  guid2 == %1", guid2));
    
        string3 = guid2str(guid2);
        info(strFmt("Info_a2:  string3 == %1", string3));
    
        guid2 = str2guid(string3);
        info(strFmt("Info_a3:  guid2 == %1", guid2));
        
        // Test string representations of a guid.
        // Upper versus lower case does not matter.
        guid2 = str2guid("BB345678-abcd-ABCD-0000-bbbbffff9012");
        string3 = guid2str(guid2);
        info(strFmt("Info_b1:  8-4-4-4-12 format for dashes works (%1)", string3));
        info(strFmt("Info_b2:  Mixed upper and lower case works."));
    
        // Dash locations must be exact.
        // Test invalid dash locations, see output is all zeros.
        guid2 = str2guid("CC2345678abcd-ABCD-0000-cccc9012");
        string3 = guid2str(guid2);
        info(strFmt("Info_c1:  These embedded dash locations are required.  %1", string3));
    
        // Braces {} are optional.
        guid2 = str2guid("{DD345678-abcd-ABCD-0000-ddddaaaa9012}");
        string3 = guid2str(guid2);
        info(strFmt("Info_d1:  Braces {} are optional (%1)", string3));
    }
```

#### ![Cc967363.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967363.collapse_all(en-us,AX.60).gif")Output

The output that is displayed in the Infolog is as follows. Notice that Microsoft Dynamics AX includes the optional braces when it converts a GUID to a string.

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">Message (02:26:46 pm)
Info_a1:  guid2 == {93945629-734B-475E-99CE-6AA7AFA43259}
Info_a2:  string3 == {93945629-734B-475E-99CE-6AA7AFA43259}
Info_a3:  guid2 == {93945629-734B-475E-99CE-6AA7AFA43259}
Info_b1:  8-4-4-4-12 format for dashes works ({BB345678-ABCD-ABCD-0000-BBBBFFFF9012})
Info_b2:  Mixed upper and lower case works.
Info_c1:  These embedded dash locations are required.  {00000000-0000-0000-0000-000000000000}
Info_d1:  Braces {} are optional ({DD345678-ABCD-ABCD-0000-DDDDAAAA9012})</pre>


## See also

[Primitive Data Types](primitive-data-types.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

