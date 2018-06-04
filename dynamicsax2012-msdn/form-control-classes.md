---
title: Form Control Classes
TOCTitle: Form Control Classes
ms:assetid: 57bd9381-d528-4381-ab05-b8bd72d3ff1b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa606405(v=AX.60)
ms:contentKeyID: 35244334
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Form Control Classes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A system class exists for each type of form control. You use the methods of the form control system classes to work with controls by using X++ code. If you use the Application Object Tree (AOT), you can use the **Override Method** shortcut to see many of the methods for the control. To use the AOT to override a method, you follow these steps:

1.  In the AOT, expand the control, and then right-click the **Methods** node of the control.

2.  Click **Override Method**, and then click the method that you want to override.

The form system classes for controls have names such as Form Controlname Control. For example, FormIntControl, FormTabPageControl, and FormCheckBoxControl. However, there are cases where the ControlName in the Application Object Tree (AOT) and the name of the form control class do not match. For more information about these methods, see [Methods on Form Controls](methods-on-form-controls.md).

The following table describes which class contains the methods for manipulating each type of form control.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Form control type</p></th>
<th><p>Class</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ActionPane</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg843603(v=ax.60)">FormActionPaneControl</a></p></td>
</tr>
<tr class="even">
<td><p>ActionPaneTab</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg843943(v=ax.60)">FormActionPaneTabControl</a></p></td>
</tr>
<tr class="odd">
<td><p>ActiveX</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg861449(v=ax.60)">FormActiveXControl</a></p></td>
</tr>
<tr class="even">
<td><p>Animate</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg845213(v=ax.60)">FormAnimateControl</a></p></td>
</tr>
<tr class="odd">
<td><p>Button</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg889850(v=ax.60)">FormButtonControl</a></p></td>
</tr>
<tr class="even">
<td><p>ButtonGroup</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg890311(v=ax.60)">FormButtonGroupControl</a></p></td>
</tr>
<tr class="odd">
<td><p>CheckBox</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg890941(v=ax.60)">FormCheckBoxControl</a></p></td>
</tr>
<tr class="even">
<td><p>ComboBox</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg891331(v=ax.60)">FormComboBoxControl</a></p></td>
</tr>
<tr class="odd">
<td><p>CommandButton</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg857250(v=ax.60)">FormCommandButtonControl</a></p></td>
</tr>
<tr class="even">
<td><p>DateEdit</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg873892(v=ax.60)">FormDateControl</a></p></td>
</tr>
<tr class="odd">
<td><p>DropDialogButton</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg893377(v=ax.60)">FormDropDialogButtonControl</a></p></td>
</tr>
<tr class="even">
<td><p>Grid</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg894164(v=ax.60)">FormGridControl</a></p></td>
</tr>
<tr class="odd">
<td><p>Group</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg894673(v=ax.60)">FormGroupControl</a></p></td>
</tr>
<tr class="even">
<td><p>GuidEdit</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg895325(v=ax.60)">FormGuidControl</a></p></td>
</tr>
<tr class="odd">
<td><p>HTML</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg876732(v=ax.60)">FormHTMLControl</a></p></td>
</tr>
<tr class="even">
<td><p>Int64Edit</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg895959(v=ax.60)">FormInt64Control</a></p></td>
</tr>
<tr class="odd">
<td><p>IntEdit</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg877272(v=ax.60)">FormIntControl</a></p></td>
</tr>
<tr class="even">
<td><p>ListBox</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg902508(v=ax.60)">FormListBoxControl</a></p></td>
</tr>
<tr class="odd">
<td><p>ListView</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg878403(v=ax.60)">FormListControl</a></p></td>
</tr>
<tr class="even">
<td><p>ManagedHost</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg903721(v=ax.60)">FormManagedHostControl</a></p></td>
</tr>
<tr class="odd">
<td><p>MenuItemButton</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg874914(v=ax.60)">FormFunctionButtonControl</a></p></td>
</tr>
<tr class="even">
<td><p>MenuButton</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg878839(v=ax.60)">FormMenuButtonControl</a></p></td>
</tr>
<tr class="odd">
<td><p>Progress</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg904585(v=ax.60)">FormProgressControl</a></p></td>
</tr>
<tr class="even">
<td><p>RadioButton</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg904915(v=ax.60)">FormRadioControl</a></p></td>
</tr>
<tr class="odd">
<td><p>RealEdit</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg905259(v=ax.60)">FormRealControl</a></p></td>
</tr>
<tr class="even">
<td><p>ReferenceGroup</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg898464(v=ax.60)">FormReferenceGroupControl</a></p></td>
</tr>
<tr class="odd">
<td><p>SegmentedEntry</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg937101(v=ax.60)">FormSegmentedEntryControl</a></p></td>
</tr>
<tr class="even">
<td><p>Separator</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg856149(v=ax.60)">FormButtonSeparatorControl</a></p></td>
</tr>
<tr class="odd">
<td><p>StaticText</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920432(v=ax.60)">FormStaticTextControl</a></p></td>
</tr>
<tr class="even">
<td><p>StringEdit</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg920847(v=ax.60)">FormStringControl</a></p></td>
</tr>
<tr class="odd">
<td><p>Tab</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg907639(v=ax.60)">FormTabControl</a></p></td>
</tr>
<tr class="even">
<td><p>TabPage</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg908347(v=ax.60)">FormTabPageControl</a></p></td>
</tr>
<tr class="odd">
<td><p>Table</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg921037(v=ax.60)">FormTableControl</a></p></td>
</tr>
<tr class="even">
<td><p>TimeEdit</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg938926(v=ax.60)">FormTimeControl</a></p></td>
</tr>
<tr class="odd">
<td><p>Tree</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg939434(v=ax.60)">FormTreeControl</a></p></td>
</tr>
<tr class="even">
<td><p>Window</p></td>
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg909772(v=ax.60)">FormWindowControl</a></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>You will also find a set of system classes called the form build control classes. The names of these are the same as the classes in the previous table except that they are prefixed with "FormBuild" instead of "Form." The form build classes contain methods that you can use to set the values of the properties for the control.</P>



## See also

[Overview of Form Control Types](overview-of-form-control-types.md)

[Form Control Properties](form-control-properties.md)

[Form Classes](form-classes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

