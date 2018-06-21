---
title: Enterprise Portal Wizard User Experience Guidelines
TOCTitle: Enterprise Portal Wizard
ms:assetid: e3b25666-1d36-4122-82df-4662037ff420
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886613(v=AX.60)
ms:contentKeyID: 35267977
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enterprise Portal Wizard User Experience Guidelines [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An Enterprise Portal wizard page guides the user through a series of simple steps in order to complete a task.

## Overview

Wizard pages are recommended for:

  - Infrequent tasks

  - Complex tasks

  - Tasks that can be split into simple subtasks in a meaningful way

  - Tasks that should be performed in a specific sequence

Wizard page for vendor signup

  
![Enterprise Portal Wizard](images/Gg886613.EPwizard_01(AX.60).png "Enterprise Portal Wizard")Wizard page for vendor signup

An Enterprise Portal wizard is made up of the following elements:

  - **Step overview** – This section, near the top of the page, shows all the steps in the wizard, separated by “greater than” symbols (\>).
    
      - The active step should be displayed in bold type.
    
      - Completed steps should be coded as links so that the user can return to them.

  - **Content area** – This is where the fields and other controls are placed. You should keep this part relatively simple so that a user can easily understand each step.

  - **Navigation buttons** – The wizard page has navigation buttons at the bottom of the page. The navigation buttons are as follows:
    
      - On step 1: **Next** \> | **Finish** (disabled) | **Cancel**
        
        When a user clicks **Cancel**, the user should be returned to the page where the wizard was initiated. If the page cannot be identified, the user should be taken to the default starting page of the area where the wizard is located.
    
      - On subsequent steps: \< **Previous** | **Next** \> | **Finish** (disabled) | **Cancel**
        
        When a user clicks **Cancel**, the user should be returned to the page where the wizard was initiated. If the page cannot be identified, the user should be taken to the default start page of the area where the wizard is located.
    
      - On the last step: \< **Previous** | **Next** \> (disabled) | **Finish** | **Cancel**
        
        When a user clicks **Finish** or **Cancel**, the user should be returned to the page where the wizard was initiated.

## Guidelines

  - All the controls described in the *Overview* section are highly recommended for a wizard page.

### What an Enterprise Portal wizard should not have

  - FactBoxes.

  - FastTabs.

  - An introductory page with no data entry on step 1. (Users should be able to start using the wizard immediately. They do not want to read just introduction text.)

  - Fields in the content area than cannot be seen without scrolling.

