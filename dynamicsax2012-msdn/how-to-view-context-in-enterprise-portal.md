---
title: 'How to: View Context in Enterprise Portal'
TOCTitle: 'How to: View Context in Enterprise Portal'
ms:assetid: d39eb56f-e236-49d0-a06b-5a0b8cac944b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee330233(v=AX.60)
ms:contentKeyID: 35589490
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: View Context in Enterprise Portal [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When an AxContextList is passed to another page, the values are passed as parameters of the URL that opens the new page. For security reasons, these parameters are encrypted to prevent users from seeing the values that were passed.

When you set up web part communication for an Action Pane or Toolbar, it can be helpful to see the values that are passed to the new page being opened. To do this, you must turn off the encryption for the Enterprise Portal site.


> [!WARNING]
> <P>Turn off encryption only when troubleshooting web part communication. Do not turn off encryption in a production Enterprise Portal installation.</P>



## To view the values for the AxContextList

1.  In the Microsoft Dynamics AX client, display the **System Administration** area page.

2.  In the **Setup** group, expand **Enterprise Portal**. Click **Web sites**.

3.  In the **Administration of Web sites** window, display the **General** tab.

4.  Make sure the **Enable encryption** checkbox is cleared. Click **Close**.

5.  If necessary, reset IIS for the change to take effect.

## Context Example

The following is a portion of the URL that displays the Work Order Details page when an item is chosen from a Toolbar web part. Notice that the values are encrypted.

…/WorkOrderDetails.aspx?mode=0\&WMI=WorkOrderDetails\&WTID=50002\&WKEY=\[65534:5637144581\]\&WCMP=CEU\&WHPV=7CBDD5030AC436E13FFB4FF4D8094F26AE1E98DA1C4D74AF00762508C3C6411A\&IsDlg=1…/WorkOrderDetails.aspx?mode=0\&WMI=WorkOrderDetails\&WTID=50002\&WKEY=\[65534:5637144581\]\&WCMP=CEU\&IsDlg=1

The following is a portion of this same URL when encryption is turned off for the site. Notice that the key values passed through the AxContextList can be seen in the URL.

…/WorkOrderDetails.aspx?mode=0\&WMI=WorkOrderDetails\&WTID=50002\&WKEY=\[65534:5637144581\]\&WCMP=CEU\&IsDlg=1

The first part of the key specifies the ID of the table that contains the record. In this example, this is the table with the ID 50002.

The second part of the key specifies the field ID and the value of the field. The ID of the field is 65534 and the value is 5637144581, which is a record ID.

