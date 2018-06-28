---
title: Methods on Form Controls
TOCTitle: Methods on Form Controls
ms:assetid: 5ae30149-fee2-4937-aa0e-0d815fa521dc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa607131(v=AX.60)
ms:contentKeyID: 35244364
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Methods on Form Controls 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Each control on a form has a standard group of methods that you can override to customize the behavior of the control. The methods that you can override depend on the type of control. Use the following steps to access these methods.

1.  In the AOT, expand the node for the control.

2.  Right-click the **Methods** node.

3.  Click **Override Method**.

The methods available in the **Override Method** menu are a subset of those available on the system class for that control type. For example, methods for manipulating **CheckBox** controls are in the FormCheckBoxControl class. The methods for manipulating **Grid** controls are in the FormGridControl class. For a list of these classes, see [Form Control Classes](form-control-classes.md).


> [!NOTE]
> <P>Code written on forms cannot be re-used or inherited. If possible, write your code on the underlying table or in a class.</P>



The following table lists methods that you can override. Some of the methods are used by several types of controls although others are unique to a single type of control. For more information about a method, see the related topic in the class reference section of Help. For example, the copy method for a **ComboBox** control is described in the FormComboBoxControl.copy method topic. The copy method for a **Tree** control is described in the FormTreeControl.copy method topic.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method name</p></th>
<th><p>Executed when</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>activateItem</p></td>
<td><p>The user activates an item in a <strong>ListView</strong> control.</p></td>
<td><p>The super call manages the activation of the item (for example, a program) represented by the icon.</p></td>
</tr>
<tr class="even">
<td><p>activeCellChanged</p></td>
<td><p>The user makes a change to the current cell in a <strong>Table</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>allItemsDeleted</p></td>
<td><p>The user has deleted all items in a <strong>ListView</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>beginDrag</p></td>
<td><p>The user starts to drag a form control or item in a control.</p></td>
<td><p>This method is not called if the DragDrop property is disabled for the control.</p></td>
</tr>
<tr class="odd">
<td><p>beginLabelEdit</p></td>
<td><p>The user starts editing (renaming) the label for a node in a <strong>Tree</strong> control.</p></td>
<td><p>This method returns a Boolean value. You can use it to prevent a user from editing the label.</p></td>
</tr>
<tr class="even">
<td><p>clicked</p></td>
<td><p>The user clicks a control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>colLabel</p></td>
<td><p>Not activated by the system.</p></td>
<td><p>The super call returns the text specified for the column heading in a <strong>Table</strong> control.</p></td>
</tr>
<tr class="even">
<td><p>columnClicked</p></td>
<td><p>When the user clicks a column header in a <strong>ListView</strong> control.</p></td>
<td><p>Pass in the column index (zero-based) to determine which column the control will be sorted on.</p></td>
</tr>
<tr class="odd">
<td><p>command</p></td>
<td><p>The method is deprecated and should not be used. The method might be removed in a future version of Microsoft Dynamics AX.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>context</p></td>
<td><p>The user right-clicks the control.</p></td>
<td><p>The super call displays the shortcut menu.</p></td>
</tr>
<tr class="odd">
<td><p>copy</p></td>
<td><p>The user copies content from a control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>cut</p></td>
<td><p>The user cuts content from a control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>data</p></td>
<td><p>Not activated by the system.</p></td>
<td><p>The super) call returns the contents of a cell in a table control.</p>

> [!note]  
> <P>Do not override the data method. An override might prevent users from accessing their data.</P>

</td>
</tr>
<tr class="even">
<td><p>dateTextChange</p></td>
<td><p>The method is deprecated and should not be used. The method might be removed in a future version of Microsoft Dynamics AX.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>dialogClosed</p></td>
<td><p>The user has closed a dialog box.</p></td>
<td><p>Add code that finishes the actions performed in a drop dialog control.</p></td>
</tr>
<tr class="even">
<td><p>dialogInitialized</p></td>
<td><p>The user has opened a dialog box.</p></td>
<td><p>Add code that initializes the contents of the drop dialog control.</p></td>
</tr>
<tr class="odd">
<td><p>doubleClick</p></td>
<td><p>The user has double-clicked an item in a <strong>ListView</strong> or <strong>ListBox</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>dragLeave</p></td>
<td><p>The user is dragging a control or item in a control from the current control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>dragOver</p></td>
<td><p>The user is dragging a control or an item in a control over another item.</p></td>
<td><p>This method is called only if the <strong>DragDrop</strong> property is enabled for the control and a beginDrag event has already been started.</p></td>
</tr>
<tr class="even">
<td><p>dragOverEx</p></td>
<td><p>The user is dragging a control or an item in a control over the current control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>dragText</p></td>
<td><p>The user is dragging an item in a <strong>Tree</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>drop</p></td>
<td><p>The user drops a control or an item in a control into a new position.</p></td>
<td><p>This method is called only if the DragDrop property is enabled for the control and a beginDrag event has already been started.</p></td>
</tr>
<tr class="odd">
<td><p>dropEx</p></td>
<td><p>The user drops a control or an item in a control onto the current control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>dropFile</p></td>
<td><p>The user drags a file from outside Microsoft Dynamics AX and drops it onto a <strong>Window</strong> control.</p></td>
<td><p>The dropFile method is called by using the file name as the parameter.</p></td>
</tr>
<tr class="odd">
<td><p>editControl</p></td>
<td><p>The user moves their mouse pointer over a <strong>Tree</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>endDrag</p></td>
<td><p>The user stops dragging a form control or an item in a control.</p></td>
<td><p>This method is called only if the DragDrop property is enabled for the control, and a beginDrag event has already been started.</p></td>
</tr>
<tr class="odd">
<td><p>endLabelEdit</p></td>
<td><p>The user has finished editing (renaming) the label for a node.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>enter</p></td>
<td><p>The user moves focus to a control.</p></td>
<td><p>This method is useful for controls where a user can select a particular item, such as a grid cell.</p>
<p>For more information, see the gotFocus method in this topic.</p></td>
</tr>
<tr class="odd">
<td><p>expanded</p></td>
<td><p>A <strong>Tree</strong> control has been expanded.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>expanding</p></td>
<td><p>A <strong>Tree</strong> control is expanding.</p></td>
<td><p>This method returns a Boolean value. You can use the value to prevent a user from expanding the tree.</p></td>
</tr>
<tr class="odd">
<td><p>filter</p></td>
<td><p>The user clicks the <strong>Filter by Selection</strong> command in the shortcut menu on a form control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>gotFocus</p></td>
<td><p>The user brings the control into focus.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>hasControlPositionOverride</p></td>
<td><p>Used only with the <strong>User Personalization</strong> form.</p></td>
<td><p>Returns a value if the tabchange or tabchanged overrides are present.</p></td>
</tr>
<tr class="even">
<td><p>helpField</p></td>
<td><p>The user clicks the control.</p></td>
<td><p>The super call displays the text in the HelpText property for the control. If not specified on the control, this text is inherited from the field or from the extended data type.</p>
<p>You can display another Help text by overriding the method.</p></td>
</tr>
<tr class="odd">
<td><p>hotTrackItem</p></td>
<td><p>The user moves the mouse pointer over a list control.</p></td>
<td><p>Pass in an integer that specifies the index value from the form list control.</p></td>
</tr>
<tr class="even">
<td><p>inputSearch</p></td>
<td><p>The user enters input in a control that has the SearchMode property set.</p></td>
<td><p>You can set up a control to search for the value a user types into the control by setting the SearchMode property. When search starts, the inputSearch method is called by using the search string as a parameter.</p></td>
</tr>
<tr class="odd">
<td><p>isResolvingReference</p></td>
<td><p>The user opens a form that contains a <strong>ReferenceGroup</strong> control and the <strong>ReplacementFieldGroup</strong> maps to a subset of a key on the primary key table.</p></td>
<td><p>You can use this method within lookupReference to know whether the lookup is being presented to help with reference disambiguation.</p></td>
</tr>
<tr class="even">
<td><p>itemChanged</p></td>
<td><p>An item in a <strong>ListView</strong> control is changed.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>itemChanging</p></td>
<td><p>An item in a <strong>ListView</strong> control is changing.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>itemCopy</p></td>
<td><p>The user has copied an item in a <strong>ListView</strong> or <strong>Tree</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>itemDeleted</p></td>
<td><p>The user has deleted an item in a <strong>ListView</strong> or <strong>Tree</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>itemInserted</p></td>
<td><p>The user has inserted an item in a <strong>ListView</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>itemMoved</p></td>
<td><p>The user has moved an item in a <strong>ListView</strong> or <strong>Tree</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>jumpRef</p></td>
<td><p>The user starts the <strong>View details</strong> command on the shortcut menu for the control or by pressing CTRL+ALT+F4.</p></td>
<td><p>The super call opens the main table that contains data for the field.</p></td>
</tr>
<tr class="odd">
<td><p>keyDown</p></td>
<td><p>The user presses the DOWN ARROW key in a <strong>ListView</strong> or <strong>Tree</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>labelMouseDblClick</p></td>
<td><p>The user double-clicks on the label for the control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>labelMousedown</p></td>
<td><p>The user clicks the mouse pointer when it is over the label for the control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>labelMouseup</p></td>
<td><p>The user releases the mouse pointer over the label for the control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>leave</p></td>
<td><p>The user moves focus out of a control.</p></td>
<td><p>This method is useful for controls where a user can select a particular item, such as a grid cell.</p>
<p>For more information, see the lostFocus method in this topic.</p></td>
</tr>
<tr class="even">
<td><p>loadAutoCompleteData</p></td>
<td><p>The user moves focus to a segment in a segmented entry control.</p></td>
<td><p>Gets the most recently used (MRU) information to present to the user. MRU information should be related to the current segment in context with the existing segments. Microsoft Dynamics AX includes a set of DimensionController classes you can use to get this information. Override this method and call the loadAutoCompleteData method of the appropriate dimension controller class. For more information, see <a href="how-to-add-a-segmented-entry-control-to-a-form.md">How to: Add a Segmented Entry Control to a Form</a>.</p></td>
</tr>
<tr class="odd">
<td><p>loadSegments</p></td>
<td><p>The user uses a segmented entry control to view, update, or enter a segmented account number.</p></td>
<td><p>Clears all dimension segments and asks for them to be reloaded. This occurs upon initial focus, or when the dimension segments have dynamically changed because of business rules. Microsoft Dynamics AX includes a set of DimensionController classes you can use to manage dimensions. Override this method and call the loadSegments method of the appropriate dimension controller class. For more information, see <a href="how-to-add-a-segmented-entry-control-to-a-form.md">How to: Add a Segmented Entry Control to a Form</a>.</p></td>
</tr>
<tr class="even">
<td><p>lookupReference</p></td>
<td><p>The user clicks on the lookup button, or presses the DOWN ARROW key.</p></td>
<td><p>Opens the lookup form you use to pick a new value to include in the <strong>ReferenceGroup</strong> control.</p>
<p>This differs from the lookup method because it returns the record selected in the lookup.</p>
<p>Typically, you override this method when you want to use a custom lookup form that includes custom filtering, sorting, and form layout.</p></td>
</tr>
<tr class="odd">
<td><p>lookup</p></td>
<td><p>The user uses the Lookup facility.</p></td>
<td><p>For more information, see <a href="how-to-add-a-control-with-a-lookup-form.md">How to: Add a Control with a Lookup Form</a>.</p></td>
</tr>
<tr class="even">
<td><p>lostFocus</p></td>
<td><p>The user brings the control out of focus.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>menuFunction</p></td>
<td><p>Not called by the system.</p></td>
<td><p>This method returns the menu item that is called by the control.</p></td>
</tr>
<tr class="even">
<td><p>modified</p></td>
<td><p>The user exits an edit field (for example, a <strong>StringEdit</strong> or <strong>IntEdit</strong> control) after changing it.</p>
<p>–or–</p>
<p>The user changes a value in a <strong>CheckBox</strong>, <strong>ComboBox</strong>, <strong>ListBox</strong>, or <strong>RadioButton</strong> control.</p></td>
<td><p>The super call manages the table update (by a sequence of calls to validate on the data source, validateField on the table, and modified on the data source).</p>
<p>If you change the visibility of the control, add element.redraw() to this method. You use redraw to also update the appearance of the form.</p></td>
</tr>
<tr class="odd">
<td><p>mouseDblClick</p></td>
<td><p>The user double-clicks a control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>mouseDown</p></td>
<td><p>The user releases the left mouse pointer button after clicking a control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>mouseEnter</p></td>
<td><p>The user moves the mouse pointer into the control area.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>mouseLeave</p></td>
<td><p>The user moves the mouse pointer out of the control area.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>mouseMove</p></td>
<td><p>The user moves the mouse pointer over the control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>mouseUp</p></td>
<td><p>The user presses the left mouse pointer button.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>onHScroll</p></td>
<td><p>The user horizontally scrolls the image or content that appears in a window control</p></td>
<td><p>You use a window control to display images. If the size of the window control is smaller than the image, the control adds scrollbars that you can use to view the image. This method is called when you use the scrollbar.</p></td>
</tr>
<tr class="even">
<td><p>onVScroll</p></td>
<td><p>The user vertically scrolls the image or content that appears in a window control</p></td>
<td><p>You use a window control to display images. If the size of the window control is smaller than the image, the control adds scrollbars that you can use to view the image. This method is called when you use the scrollbar.</p></td>
</tr>
<tr class="odd">
<td><p>paint</p></td>
<td><p>A <strong>Window</strong> control is redrawn.</p></td>
<td><p>The super call draws the background and displays the .bmp file.</p></td>
</tr>
<tr class="even">
<td><p>paste</p></td>
<td><p>The user pastes content into a control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>performFormLookup</p></td>
<td><p>The user clicks a <strong>Lookup</strong> button on a control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>processBase</p></td>
<td><p>The method is deprecated and should not be used. The method might be removed in a future version of Microsoft Dynamics AX.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>processForm</p></td>
<td><p>The method is deprecated and should not be used. The method might be removed in a future version of Microsoft Dynamics AX.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>processLink</p></td>
<td><p>The method is deprecated and should not be used. The method might be removed in a future version of Microsoft Dynamics AX.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>processPicture</p></td>
<td><p>The method is deprecated and should not be used. The method might be removed in a future version of Microsoft Dynamics AX.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>processTitle</p></td>
<td><p>The method is deprecated and should not be used. The method might be removed in a future version of Microsoft Dynamics AX.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>resolveReference</p></td>
<td><p>The user moves focus from the <strong>ReferenceGroup</strong> control after typing a value into the control.</p></td>
<td><p>You use this method to translate the new value into a related record.</p>
<p>Typically, you override this method when you have special filtering requirements or the <strong>ReferenceGroup</strong> control is displaying a subset of a key and there is some external context which provides the missing part of the key.</p></td>
</tr>
<tr class="even">
<td><p>rowLabel</p></td>
<td><p>Not activated by the system.</p></td>
<td><p>The super call returns the text specified as the row heading in a <strong>Table</strong> control.</p></td>
</tr>
<tr class="odd">
<td><p>segmentEntered</p></td>
<td><p>The user moves focus to an individual segment in a segmented entry control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>segmentValueChanged</p></td>
<td><p>The user changes the value in a segment.</p></td>
<td><p>Runs when focus leaves a segment and the segment value changed. For more information, see <a href="how-to-add-a-segmented-entry-control-to-a-form.md">How to: Add a Segmented Entry Control to a Form</a>.</p></td>
</tr>
<tr class="odd">
<td><p>selectionChanged</p></td>
<td><p>The user has moved the selection to another item in a <strong>ListView</strong> or <strong>Tree</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>selectionChange</p></td>
<td><p>The user alters the selection in a <strong>ComboBox</strong>, <strong>ListBox</strong>, or <strong>RadioButton</strong> control.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>selectionChanging</p></td>
<td><p>The user is moving the selection to another item in a <strong>ListView</strong> or <strong>Tree</strong> control.</p></td>
<td><p>This method returns a Boolean value. You can use the value to prevent a user from being able to change the selection. For example, to disable the selection of a particular item.</p></td>
</tr>
<tr class="even">
<td><p>setScrollInfo</p></td>
<td><p>Not activated by the system.</p></td>
<td><p>This method turns on horizontal and vertical scrollbars for the windows control and sizes them correctly. You can also use this method to turn off horizontal and vertical scrollbars.</p></td>
</tr>
<tr class="odd">
<td><p>showContextMenu</p></td>
<td><p>The shortcut menu for a control is opened.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>size</p></td>
<td><p>The window control is sized.</p></td>
<td><p>The window control is sized when it is first drawn, the form is resized, or the window control is programmatically resized.</p></td>
</tr>
<tr class="odd">
<td><p>sort</p></td>
<td><p>The user changes the sort order of a control.</p></td>
<td><p>Use the SortOrder enumeration to specify the sort direction.</p></td>
</tr>
<tr class="even">
<td><p>tabChange</p></td>
<td><p>A change of tabbed pages has occurred.</p></td>
<td><p>Do not override the tabChange or tabChanged methods on Tab controls. Instead, override the pageActivated and allowPageDeactivate methods on <strong>Tabpage</strong> controls.</p>
<p>If you override tabChange or tabChanged, the user setup level for the tab cannot be higher than <strong>Restricted</strong>. The user cannot fully customize the layout and content.</p>
<p>The parameters received for tabChange and tabChanged are based on tabbed page indexes. They depend on the current position of the tabbed page. Prevent users from moving a tabbed page if either of these methods are overridden. The pageActivated and allowPageDeactivate methods do not pass any information about the current position of the tabbed page and enable full user setup.</p></td>
</tr>
<tr class="odd">
<td><p>tabChanged</p></td>
<td><p>Immediately before the change of the tabbed page.</p>
<p>If the method returns false, the system does not change the tabbed page.</p></td>
<td><p>Do not override this method.</p>
<p>For more information, see the tabChange method in this topic.</p></td>
</tr>
<tr class="even">
<td><p>textChange</p></td>
<td><p>The user types in a field.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>toolTip</p></td>
<td><p>The user points to the control with the mouse pointer.</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>validate</p></td>
<td><p>The user exits a control after entering data.</p></td>
<td><p>The super call starts the validateField method on the database table.</p></td>
</tr>
</tbody>
</table>


## See also

[Methods on a Form](methods-on-a-form.md)

[Methods on a Form Data Source](methods-on-a-form-data-source.md)

[Overview of Form Control Types](overview-of-form-control-types.md)

[Form Control Properties](form-control-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

