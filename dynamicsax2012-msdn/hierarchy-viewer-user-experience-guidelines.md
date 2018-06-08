---
title: Hierarchy Viewer User Experience Guidelines
TOCTitle: Hierarchy Viewer
ms:assetid: 56a7adca-4007-4568-9a2f-d535a9d4e06e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886594(v=AX.60)
ms:contentKeyID: 35267958
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Hierarchy Viewer User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The *Hierarchy viewer control* makes it possible to view and manage large hierarchies, which was not possible in previous versions of Microsoft Dynamics AX. Business users need to work with the hierarchies of companies, departments, bill of materials components, accounts, and more. Both the existing Windows® Tree control and the Microsoft Dynamics AX 2009 Directory View control limit the hierarchy view to just a few nodes and levels. This limitation makes it difficult to obtain an overview of how a leaf node fits into a large hierarchy. It also makes it difficult to quickly browse specific nodes because users do not get a sense of the overview for that node. Users also cannot get an idea of the size of a branch unless they navigate to every leaf in that branch. The Hierarchy viewer control removes this limitation.

Example of the Windows Tree control and the Microsoft Dynamics AX 2009 Directory view control

![Windows Tree control](images/Gg886594.HierarchyViewer01(AX.60).png "Windows Tree control") ![Microsoft Dynamics AX Directory view control](images/Gg886594.HierarchyViewer02(AX.60).png "Microsoft Dynamics AX Directory view control")

## Overview

The Hierarchy viewer control is a generic control that should be used for displaying large hierarchies. The control can browse hierarchies of more than 50,000 nodes (by limiting the view to *n* levels away from the focus node). It lets users navigate the hierarchy, step-by-step, while the view keeps focus on the next few levels. At the same time, the representation of levels further away indicates the size and density of branches to help users orient themselves.

## Design concepts

This section discusses the visualization principle of the Hierarchy viewer control and how users use the control to interact in the hierarchy.

### Visualization principle

The Hierarchy viewer control uses an adapted fish-eye zoom, which emphasizes a specific node and its nearest children. In addition, the Hierarchy viewer control bends the horizontal lines of sibling nodes into semicircles. This approach creates longer lines in the same horizontal space, which means that more nodes can fit into view. And because nodes are wider than they are tall, the near-vertical segments of the semicircles allow nodes to be stacked at a higher density so even more nodes fit per degree of angle of the semicircle.

Example of a dense hierarchy presentation

  
![Dense display of hierarchy](images/Gg886594.HierarchyViewer03(AX.60).png "Dense display of hierarchy")Example of a dense hierarchy presentation

### Interaction in the hierarchy

Users should not spend time adjusting the viewport by zooming or scrolling to fit the relevant data in view. To avoid this, the Hierarchy viewer control lets users browse the hierarchy by clicking a node towards the edge of the visualization. This animates the node to the top and center, showing additional levels of hierarchy under that node. The animation helps users follow the node through the transition so that users are not disoriented when the new view appears.

The hierarchy is always laid out based on a center node, which is shown at the top-center position.

If parents exist for the current center node, then they are shown in a horizontal node Address bar in the upper-left corner of the visualization. When the node Address bar fills up, nodes in the middle of the sequence will be hidden, and an ellipsis (…) will appear to indicate that one or more nodes are hidden.

Example of the node Address bar over the center node

  
![Node address bar shown over center node](images/Gg886594.HierarchyViewer04(AX.60).png "Node address bar shown over center node")Example of the node Address bar over the center node

The focus node is highlighted in orange. By default, the center node is also the focus node. Users can move their pointers over a node or use arrow keys to move keyboard focus around the hierarchy. As this is happening, the focus moves around while the same center node is at the top.

Example showing that the user moved the focus node to a node other than the center node

  
![Focus node (in orange) moved from center node](images/Gg886594.HierarchyViewer05(AX.60).png "Focus node (in orange) moved from center node")Example showing that the user moved the focus node to a node other than the center node

If the top ring of nodes has more nodes than can fit in view, then a “rotation arrow” appears at the top of the hierarchy, as you can see in the image above. Selecting this arrow will rotate the visualization around the center node to show a new set of children of the same center node.

## Guidelines

This section includes both general and specific guidelines for the Hierarchy viewer control.

### General guidelines

  - The Hierarchy viewer control should be used for tasks where users need to view and browse hierarchies that are likely to have more than 25 nodes. This control can be used for hierarchies with fewer than 20 nodes, but another control, such as the Tree control, might present the nodes in less space.

  - Consider whether a hierarchical grid might be a better choice for tasks that require a comparison of column values other than node name, or that require mass editing of such column values.

  - The default size of the Hierarchy viewer control should be set to a 4:3 ratio. If you know that the hierarchies being displayed will be wide but shallow, the control should be made even wider.

  - Like other visualizations, the Hierarchy viewer control does not display a tooltip when the pointer is hovering over a node because that would block the view of other nodes. Instead, the Hierarchy viewer control supports an event that is triggered on mouse hover and keyboard focus change. You should use this event to update a Preview pane below the Hierarchy viewer control with details about the node in focus.

  - The Hierarchy viewer control also supports an event for changed node selection. You can use this event to update FactBoxes with information related to the selected node.
    

    > [!NOTE]
    > <P>You should not update FactBoxes on the <STRONG>MouseHover</STRONG> event because this would cause frequent updates if users were to drag pointers across the screen.</P>



### Specific guidelines

The following sections describe the specific guidelines for a Hierarchy viewer control.

#### Embedding the control in pages

  - The Hierarchy viewer control is intended to be embedded on list pages where it will provide a visual overview of the nodes that would otherwise be shown in a flat list. The Hierarchy viewer control can also be embedded in details forms for browsing a particular hierarchy, and in selection dialogs where users select a node to bring back the page where they came from.
    
    The following image shows the Hierarchy viewer control embedded in a list page.
    
    ![List page with embedded Hierarchy viewer control](images/Gg886594.HierarchyViewer06(AX.60).png "List page with embedded Hierarchy viewer control")

  - It is important to include a Preview pane in the list page and hook it up to the **MouseHover** event of the Hierarchy viewer control, so that details will be displayed about the node that is under the mouse pointer or selected with the keyboard. If relevant, also include FactBoxes that display information related to the hierarchy or to the selected node.

  - If multiple hierarchies can dynamically be created and named for the same purpose (as in the image above, which shows reporting relationships), then include a drop-down combo box above the Hierarchy viewer control where users can select the hierarchy name that they want to see.

  - Hierarchies cannot be filtered because that would leave orphaned nodes if their parent nodes were filtered out. Instead, the Hierarchy viewer control supports **Find** functionality. This functionality is similar to the **Find** functionality in Microsoft Office Word 2010, where the first match is brought into focus and other matches highlighted, and users can then jump from match to match.
    
    The following image shows where to include a **Find** field.
    
    !["Find" field location](images/Gg886594.HierarchyViewer07(AX.60).png "\"Find\" field location")

  - The **Find** field and related buttons should be placed above the Hierarchy viewer control, and they should be right-aligned with the Hierarchy viewer control. The field and buttons should be hooked up to the find, clear, previous, and next events of the control.

#### Action pane

User actions should be presented on an action pane, and the action pane should include as many of the following actions as you can support:

\<**EntityName**\> **tab**

  - New
    
      - Node

  - Maintain
    
      - Insert node
    
      - Insert placeholder (dummy node with default values)
    
      - Remove node
    
      - Undo

  - Related information
    
      - Hierarchy details
    
      - \<NodeType\> details
    
      - Plus any domain-specific actions

  - List
    
      - Refresh

**View tab**

  - View as of date
    
      - Calendar
    
      - Effective date
    
      - Compare
    
      - Show markup (changes node color to highlight nodes that are cut or inserted between two dates)
    
      - Plus any domain-specific actions for viewing data related to the hierarchy or the selected node

#### Node Colors

  - Developers can specify a separate node color and node icon for each type of node used in a hierarchy. If multiple colors are needed, then the following colors should be used.
    
    ![Table of node colors](images/Gg886594.HierarchyViewer08(AX.60).png "Table of node colors")

  - Users who are partially color blind have the highest chance of distinguishing the colors in this table if the colors are applied from left to right (so that the right-most colors are left out if not all the colors are needed). We recommend that you do not use more than the six colors in the table. However, it is acceptable to use completely white nodes (for example, for not-yet-active data).

## See also

[Action Pane User Experience Guidelines](action-pane-user-experience-guidelines.md)

