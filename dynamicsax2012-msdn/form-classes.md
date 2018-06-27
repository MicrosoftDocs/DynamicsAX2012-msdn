---
title: Form Classes
TOCTitle: Form Classes
ms:assetid: d64523ff-e269-4698-b605-1626d07894c5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa873725(v=AX.60)
ms:contentKeyID: 35252038
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Form Classes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You use Form classes to create, modify, or run forms by using X++ code. You often use classes to modify forms during run time. For example, you want to hide one or more controls on a form when you click a specified type of record in the form.

The form classes are all system classes and are prefixed with Form. Examples of form classes include FormRun, FormStringControl, FormBuildDesign.

The form classes are in the following class type categories:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Class type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Form build</p></td>
<td><p>Used when you design the form.</p></td>
</tr>
<tr class="even">
<td><p>Form run</p></td>
<td><p>Used when the form is executed.</p></td>
</tr>
</tbody>
</table>


The following table describes the most frequently used form classes. For a complete list of form classes, expand the **System Documentation\\Classes** node in the Application Object Tree (AOT).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Class name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg839596(v=ax.60)">Form</a></p></td>
<td><p>Use the methods of the class to add data sources and controls to the form. This is a form run type class that contains methods that you can use to access the properties of the form.</p>
<p>You can use this class to create a form with X++ code instead of using the AOT. For more information, see <a href="using-classes-to-create-forms.md">Using Classes to Create Forms</a>.</p>
<p>Some of the methods in this class are available for overriding on a form in the AOT. For more information, see <a href="methods-on-a-form.md">Methods on a Form</a>.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920249(v=ax.60)">FormRun</a></p></td>
<td><p>Use the methods of the class to execute a form. This is a form run type class.</p>
> [!note]  
> <P>To follow best practices for instantiating a form, use MenuFunction instead of FormRun.</P>
</td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg859330(v=ax.60)">FormDesign</a></p></td>
<td><p>Use the methods of the class to add controls to the form. This is a form run type class that contains methods that you can use to access the properties on the <strong>Design</strong> node for a form.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg848126(v=ax.60)">FormBuildDesign</a></p></td>
<td><p>Use the methods of the class to add controls to the form. This is a form build type class that contains methods that you can use to access the properties in the <strong>Design</strong> node of the form;</p>
<p>You can use this class to specify the graphical layout of a form by using X++ code.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg892246(v=ax.60)">FormDataSource</a></p></td>
<td><p>Use the methods of the class to change the behavior of the data source (caching, validation, and others). You can use methods to change the notification events for a record in the form. This is a form run type class that contains methods that you use to access the properties of a form data source.</p>
<p>A subset of the methods in this class is available for overriding on form data sources. For more information, see <a href="methods-on-a-form-data-source.md">Methods on a Form Data Source</a>.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg847530(v=ax.60)">FormBuildDataSource</a></p></td>
<td><p>Use the methods of the class to work with the properties on a form data source. This is a form build type class that contains methods that you use to access the properties of the form data source.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857551(v=ax.60)">FormControl</a></p></td>
<td><p>Use the methods of the class to work with a control. This is a form run type class that contains property methods that you use to access the properties that are common to all control types.</p>
<p>FormControl is the parent class for all form control classes. To access the properties of a specific type of control, you should use methods from the class for that control instead of this parent class.</p></td>
</tr>
<tr class="even">
<td><p>Form&lt;control name&gt;Control</p>
<p>For example, <a href="https://msdn.microsoft.com/en-us/library/gg920847(v=ax.60)">FormStringControl</a>, and <a href="https://msdn.microsoft.com/en-us/library/gg939434(v=ax.60)">FormTreeControl</a>.</p></td>
<td><p>Use the methods of the class to work with a specified control type. This is a form run type class that contains methods that you use to work with the specified control type.</p>
<p>For a list of all the form control classes, see <a href="form-control-classes.md">Form Control Classes</a>. A subset of the methods in these classes is available for overriding on controls. For more information, see <a href="methods-on-form-controls.md">Methods on Form Controls</a>.</p></td>
</tr>
<tr class="odd">
<td><p>FormBuild&lt;control name&gt;Control</p>
<p>For example, <a href="https://msdn.microsoft.com/en-us/library/gg869773(v=ax.60)">FormBuildStringControl</a>, and <a href="https://msdn.microsoft.com/en-us/library/gg889598(v=ax.60)">FormBuildTreeControl</a>.</p></td>
<td><p>Use the methods of the class to work with the properties of a specified control type. This is a form build type class that contains methods that you use to work with a specified control type.</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

