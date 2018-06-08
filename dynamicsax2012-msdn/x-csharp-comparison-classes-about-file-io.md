---
title: 'X++, C# Comparison: Classes about File IO'
TOCTitle: 'X++, C# Comparison: Classes about File IO'
ms:assetid: cc002c80-5fa7-462f-b4bb-930b4e4f30b6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967427(v=AX.60)
ms:contentKeyID: 35251547
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++, C\# Comparison: Classes about File IO 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX provides several classes that perform file input and output (IO) operations. In the .NET Framework that is used in C\#, the counterparts to these classes reside in the System.IO namespace.

## Table of Class Comparisons

The following table lists several .NET Framework classes for C\# that are in the System.IO namespace. Each row in the table shows the X++ class or method that best corresponds to the .NET Framework class.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BinaryIo</p></td>
<td><p>FileStream</p>
<p>BinaryReader</p>
<p>BinaryWriter</p></td>
<td><p>X++ classes such as BinaryIo that extend from the abstract class Io serve as a stream, and they also serve as a reader and writer for that stream.</p>
<p>In C# the stream is a separate class the from the class that has the more specific read and write methods.</p></td>
</tr>
<tr class="even">
<td><p>TextBuffer</p></td>
<td><p>MemoryStream</p></td>
<td><p>These classes contain an in-memory buffer, and some of the methods treat the buffer as if it were a file on the hard disk.</p></td>
</tr>
<tr class="odd">
<td><p>WINAPI::createDirectory</p>
<p>WINAPI::folderExists</p>
<p>WINAPI::removeDirectory</p></td>
<td><p>Directory</p>
<p>DirectoryInfo</p>
<p>Path</p></td>
<td><p>X++ can use static methods in the WINAPI class for many basic operating system functions that involve directories.</p></td>
</tr>
<tr class="even">
<td><p>WINAPI::getDriveType</p></td>
<td><p>DriveInfo</p>
<p>DriveType</p></td>
<td><p>These classes and methods are used to obtain drive related information.</p></td>
</tr>
<tr class="odd">
<td><p>WINAPI::copyFile</p>
<p>WINAPI::createFile</p>
<p>WINAPI::deleteFile</p>
<p>WINAPI::fileExists</p></td>
<td><p>File</p>
<p>FileAttributes</p>
<p>FileInfo</p></td>
<td><p>X++ can use static methods in the WINAPI class for many basic operating system functions that involve files.</p></td>
</tr>
<tr class="even">
<td><p>CommaIo</p>
<p>Comma7Io</p></td>
<td><p>(No corresponding class.)</p></td>
<td><p>These X++ classes can generate files that Microsoft Excel can import. In X++ the <a href="https://msdn.microsoft.com/en-us/library/gg959078(v=ax.60)">SysExcel Class</a> provides additional interaction with Excel.</p></td>
</tr>
<tr class="odd">
<td><p>AsciiIo</p>
<p>TextIo</p></td>
<td><p>FileStream</p>
<p>TextReader</p>
<p>TextWriter</p></td>
<td><p>These classes use different code pages.</p></td>
</tr>
<tr class="even">
<td><p>Io</p></td>
<td><p>Stream</p>
<p>StreamReader</p>
<p>StreamWriter</p>
<p>FileStream</p></td>
<td><p>These are often used as base classes that other classes extend.</p></td>
</tr>
<tr class="odd">
<td><p>CodeAccessPermission</p>
<p>FileIoPermission</p></td>
<td><p>System.Security</p>
<p>.CodeAccessPermission</p>
<p>The namespace System.Security.Permissions includes the following classes:</p>
<ul>
<li><p>CodeAccessSecurityAttribute</p></li>
<li><p>FileIOPermissionAttribute</p></li>
<li><p>FileIOPermission</p></li>
<li><p>FileIOPermissionAccess</p></li>
</ul></td>
<td><p>The concepts and methods of assert, demand, and revertAssert apply to both languages. However, the deny and revertDeny methods that are available in C# are not available in X++.</p></td>
</tr>
</tbody>
</table>


## See also

[X++, C\# Comparison: Classes](x-csharp-comparison-classes.md)

[Performing File IO with the TextIo Class](performing-file-io-with-the-textio-class.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

