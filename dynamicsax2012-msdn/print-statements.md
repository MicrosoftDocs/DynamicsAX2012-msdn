---
title: Print Statements
TOCTitle: Print Statements
ms:assetid: 7e57d45e-49dc-4263-a745-8c7e802e4882
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa676511(v=AX.60)
ms:contentKeyID: 35246124
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Print Statements 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

X++ provides a print statement that allows you to display text or selected results in a temporary window. The messages are displayed in a **Print** window that appears when the first print statement is executed.

The print statement can be a convenient alternative to the Global::info method during testing. The info method displays text in the **Infolog** window. The following table compares the print statement against the Global::info method.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>Print statement</p></th>
<th><p>Info method</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ease of invocation</p></td>
<td><p>The Print statement automatically converts various data types to strings. It can convert multiple data types in one invocation.</p></td>
<td><p>The Info method requires that the input parameter be a string.</p></td>
</tr>
<tr class="even">
<td><p>Copy to clipboard</p></td>
<td><p>The <strong>Print</strong> window contents cannot be copied to the clipboard.<br />
You cannot give the <strong>Print</strong> window focus.</p></td>
<td><p><strong>Infolog</strong> contents are easily copied to the clipboard.</p></td>
</tr>
<tr class="odd">
<td><p>Scope of lifetime</p></td>
<td><p>The <strong>Print</strong> window closes when the X++ job ends.</p>
<p>Therefore, always write a pause statement at the end of the job, whenever a print statement occurs in the job. Otherwise the <strong>Print</strong> window contents will display too briefly to be read. The pause statement displays a dialog with buttons labeled <strong>Yes</strong> and <strong>No</strong>. Click <strong>Yes</strong> if the job should continue beyond the pause statement.</p></td>
<td><p>The <strong>Infolog</strong> window persists for the whole client session.</p></td>
</tr>
<tr class="even">
<td><p>Size and location</p></td>
<td><p>The Print window can be a specific size, and in a specific location on the screen. For example, consider the following X++ window at statement:</p>
<p>window 55,4 at 22,3;</p>
<p>The following list explains the meaning of each numeric parameter:</p>
<ul>
<li><p>55 – the maximum character length per line in the <strong>Print</strong> window.</p></li>
<li><p>4 – the number of lines the Print window can fit in its display.<br />
The <strong>Print</strong> window has no scrollbars, and you cannot give the <strong>Print</strong> window focus.</p></li>
<li><p>22 – the location on the horizontal x-axis of the client area for the upper left corner of the <strong>Print</strong> window.</p></li>
<li><p>3 – the location on the vertical y-axis of the client area for the upper left corner of the <strong>Print</strong> window.</p></li>
</ul></td>
<td><p>The Infolog window is sized and placed by the system.</p></td>
</tr>
<tr class="odd">
<td><p>Common usage</p></td>
<td><p>The Print statement is used for convenience during testing. It can help you debug small problems without needing to run a formal debugger.</p></td>
<td><p>The Info method is appropriate for use in production.</p></td>
</tr>
</tbody>
</table>


## X++ Code Example

The following X++ job demonstrates that the print statement automatically converts any data type to a string. To create a job in the AOT, right-click the **Jobs** node, and then click **New Job**.
```X++  
    static void PrintJob2(Args _args)
    {
        str s1 = "Hello";
        int n2 = 42;
        utcDateTime udt3 = DateTimeUtil::utcNow();
        Dialog dlog4 = new Dialog();
    
        window 55,4 at 22,3;
    
        print "The print statement automatically converts data types to strings.";
        print s1, " -- ", n2, " -- ", udt3, " -- ", dlog4;
        
        pause;
        
        Global::info("User clicked 'Yes' to continue to this call to info.");
        info(int2Str(n2)); // int2Str converter is needed.
    }
    
    /***  Output to the Print window:
    The print statement automatically converts data types to strings.
    Hello -- 42 -- 10/3/2011 09:18:10 pm -- 1
    ***/
    
    /***  Output to Infolog window:
    Message (02:18:10 pm)
    User clicked 'Yes' to continue to this call to info.
    ***/
```
## See also

[Statements and Loops](statements-and-loops.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

