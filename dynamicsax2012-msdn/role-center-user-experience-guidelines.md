---
title: Role Center User Experience Guidelines
TOCTitle: Role Center
ms:assetid: d4d576d1-639f-464b-a27e-d39123340384
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886608(v=AX.60)
ms:contentKeyID: 35267972
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Role Center User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Role center should answer these questions for the user:

  - What is my workload?

  - What do I need to do next?

  - Are there any urgent actions that I need to carry out?

  - What is the status of the things that I should be most concerned about?

Example of a Role center for a CEO in the Microsoft Dynamics AX client

  
![A Role center in the client](images/Gg886608.RoleCenter_client_01(AX.60).png "A Role center in the client")Example of a Role center for a CEO in the Microsoft Dynamics AX client

## Overview

A Role center should be set up for each role in the company, and it should provide a user with the right content for the job.

In a Role center, content is displayed inside SharePoint® Web parts from a variety of sources, as follows:

  - Microsoft Dynamics AX

  - Windows® SharePoint Services

  - Microsoft® Office SharePoint Server 2007

This content should be specifically tailored for each role.

## Guidelines

Role centers in Microsoft Dynamics AX should be:

  - Simple and cleanly designed.

  - Easy to skim and read.

  - Aligned with the design guidelines.

  - Easy to localize and customize.

When creating a Role center, follow these general guidelines:

1.  Identify the needs for a role. For example, consider the following:
    
      - What information does this role frequently need to do the job?
    
      - What information would help this role be more efficient at the job?

2.  Create content around those needs.

3.  Determine the best Web part to display for each type of content.

4.  Validate the value of the Role center with real users who match the role.

### Content and layout

Prioritizing the content is extremely important for a great user experience. Make sure that critical content such as activities, work lists, key charts, and other important components are visible at first glance and are clearly organized.

Tailor the content to be useful at a glance. The most important content should be immediately visible at a screen resolution of 1280 x 800, without scrolling.

#### Web parts

  - Web parts should be organized in two columns.

  - There should be at least 4 and a maximum of 10 Web parts.

  - The title of each Web part in a Role center should be in sentence case.

  - All Web part content should be sized appropriately. There should be no scroll bars in the Web part. All the content should be visible by default.

  - To maximize the use of vertical space, there should be no filter controls (quick and advanced filters) displayed in a Web part that contains a grid.

  - No error messages should be displayed by default in the Web part.

#### Activities parts

  - The activities part should have a title name that does not contain the word “Cues.”

  - Each stack in the activities part should navigate to the appropriate list page when clicked and have the same filter applied. When navigated to, that list page should also have the same name as the activities stack title.

  - The recommended number of stacks is 6 or fewer.
    
    Example of an activities part
    
      
    ![An activities part](images/Gg886604.RoleCenter_activities_02(AX.60).png "An activities part")Example of an activities part

#### Work list parts

  - There should be only one work list part for each Role center.

  - The work list part should have a title that contains the words “work list”.
    
    Example of work list part
    
      
    ![A work list part](images/Gg886604.RoleCenter_worklist_03(AX.60).png "A work list part")Example of work list part

#### Charts

To learn more about how to arrange and display chart information in Web parts, follow the guidelines for the [General Reporting User Experience Guidelines](general-reporting-user-experience-guidelines.md) and the [Charts in Reports User Experience Guidelines](charts-in-reports-user-experience-guidelines.md). Avoid overusing charts and graphs in a single Role center, because overuse impairs usability and decreases product performance.

