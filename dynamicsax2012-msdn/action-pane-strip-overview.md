---
title: Action Pane Strip Overview
TOCTitle: Action Pane Strip Overview
ms:assetid: f1a37d00-94bd-4a14-a099-ecaf05251154
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg848145(v=AX.60)
ms:contentKeyID: 35253382
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Action Pane Strip Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An action pane strip is a collection of controls that organize and display action pane buttons. Like the action pane found on list pages and details forms, the buttons in an action pane strip represent specific tasks and operations that you can perform. For information about action panes, see [Action Pane Overview](action-pane-overview.md).

The following illustration shows an action pane strip for a form. An action pane strip can also appear with a FastTab, or a grid control.

![Action pane strip at the top of a form](images/Gg848145.ActionPaneStrip_02(en-us,AX.60).png "Action pane strip at the top of a form")

## Action Pane Strip Design

An action pane strip is a simplified version of an action pane that includes a single row of buttons. The small number of buttons reduces the amount of work that you have to do to design and build an action pane strip. To design an action pane strip, you use many of the same guidelines as an action pane. For example, the most used buttons appear on the left side of the action pane strip. In addition, you can add icons to the buttons that represent the task the button performs. For more information about how to design an action pane strip, see [Action Pane Strip User Experience Guidelines](action-pane-strip-user-experience-guidelines.md).

You use an action pane strip with a smaller form where a full action pane uses too much space or the form does not have enough actions to justify an action pane. You can also use an action pane strip when you want to put actions closer to relevant records and data fields. For example, you might want to show actions that apply to the records that appear in a grid or a FastTab.

You customize the action pane strip by adding action pane buttons. For example, a form that supports creating or deleting records should have **New** and **Delete** buttons. In the illustration, the buttons are labeled **New**, **Delete**, **Variant suggestions**, **Product image**, **Release products**, and **Translations**.

You use the buttons to perform a specified action using the record or information shown on the form. If the action pane strip does not contain any buttons, the strip will not be visible.

### ![Gg848145.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg848145.collapse_all(en-us,AX.60).gif")Forms with action pane strips

The form design guidelines include an action pane strip across the top of the following types of forms:

  - Simple details

  - Simple list

  - Simple list and details

You can use templates to create simple list and simple list and details forms. The template adds the controls for the action pane strip to the **Design** node of the form. You customize the action pane strip by modifying existing buttons or adding new buttons. When used at the top of a form, the action pane strip appears next to the **File** menu.


> [!NOTE]
> <P>The <STRONG>File</STRONG> menu is a system-generated menu that displays commands you use across all forms. The menu includes clipboard commands, filtering, personalization, tools, and other options.</P>



### ![Gg848145.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg848145.collapse_all(en-us,AX.60).gif")FastTabs and grids on a form

You can add an action pane strip that appears with the following controls on a form:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Control type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FastTab</p></td>
<td><p>Add the action pane strip to a FastTab to show the actions that apply to the contents of the tab. You can use the action pane strip to show relevant actions that might be difficult to find in the action pane at the top of the form. For more information about FastTabs, see <a href="fasttabs.md">FastTabs</a>.</p></td>
</tr>
<tr class="even">
<td><p>Grid</p></td>
<td><p>Add an action pane strip that appears above the grid to show actions that are relevant to the records that appear in the grid. Typically, the action pane strip includes <strong>Add</strong>, <strong>Remove</strong>, and <strong>Details</strong> buttons that you use to create, delete, or view records that appear in the grid.</p></td>
</tr>
</tbody>
</table>


## Action Pane Strip Controls

To build an action pane strip, you use the same controls that you use to create an action pane. For information about how to add an action pane strip to a form, see [How to: Create an Action Pane Strip](how-to-create-an-action-pane-strip.md).

The following table describes how an action pane strip differs from an action pane. For more information about the controls you use with an action pane strip, see [Action Pane Overview](action-pane-overview.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Control type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Action pane</p></td>
<td><p>You add an action pane control in the <strong>Design</strong> node of the form. You use the <strong>Style</strong> property of the action pane control to specify the appearance of the action pane strip.</p></td>
</tr>
<tr class="even">
<td><p>Action pane tab</p></td>
<td><p>You add a single action pane tab to the action pane. You do not have to provide a caption for the tab.</p></td>
</tr>
<tr class="odd">
<td><p>Button group</p></td>
<td><p>You add a single button group to the action pane. You do not have to provide a caption for the group.</p></td>
</tr>
<tr class="even">
<td><p>Buttons</p></td>
<td><p>You add one or more buttons to the button group on the action pane strip. You should limit the number of buttons to what can appear in the strip. For more information about buttons, see <a href="action-pane-button-overview.md">Action Pane Button Overview</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[Action Panes and Action Pane Strips](action-panes-and-action-pane-strips.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

