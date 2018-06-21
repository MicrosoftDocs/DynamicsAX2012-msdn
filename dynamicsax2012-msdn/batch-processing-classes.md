---
title: Batch Processing Classes
TOCTitle: Batch Processing Classes
ms:assetid: e9c3fe95-acee-440a-9b20-1bbccfb9390a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa882882(v=AX.60)
ms:contentKeyID: 35253229
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Batch Processing Classes [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Implement classes by using the batch processing system, and by extending the [RunBase](runbase-framework.md) and the [RunBaseBatch](https://msdn.microsoft.com/en-us/library/gg822687\(v=ax.60\)) classes.

Remove the **Recurrence** button from the **Batch processing** dialog by using the Args::parmEnum method. For more information, see the procedure later in this topic.

It is recommended that you designate a class to run as a server-bound batch job. Server-bound batch jobs are more secure than jobs that are not server-bound batch for the following reasons:

  - The job executes by using the permissions of the user who submitted the job.

  - The job can interact with the Microsoft Dynamics AX client, which is processing the job, by using only certain [Info](https://msdn.microsoft.com/en-us/library/gg836364\(v=ax.60\)) and [Global](https://msdn.microsoft.com/en-us/library/gg836018\(v=ax.60\)) class methods. This limits interaction with the client.

## Enable a Class to Run as a Server-Bound Batch Job

1.  Create a class that extends the [RunBaseBatch](https://msdn.microsoft.com/en-us/library/gg822687\(v=ax.60\)) class.

2.  Override the [RunBaseBatch.runsImpersonated](https://msdn.microsoft.com/en-us/library/gg822697\(v=ax.60\)) method to return a value of true, as shown in the following example.
    
        public boolean runsImpersonated()
        {
            return true;
        }

3.  Confirm that the class calls only the following Info and Global class methods:
    
      - [add](https://msdn.microsoft.com/en-us/library/gg820509\(v=ax.60\))
    
      - [Info.copy](https://msdn.microsoft.com/en-us/library/gg820972\(v=ax.60\))
    
      - [Info.cut](https://msdn.microsoft.com/en-us/library/gg820980\(v=ax.60\))
    
      - [Info.import](https://msdn.microsoft.com/en-us/library/gg836365\(v=ax.60\))
    
      - [Info.export](https://msdn.microsoft.com/en-us/library/gg821018\(v=ax.60\))
    
      - Info.line
    
      - Info.num
    
      - [Global::error](https://msdn.microsoft.com/en-us/library/gg835677\(v=ax.60\))
    
      - [Global::info](https://msdn.microsoft.com/en-us/library/gg836019\(v=ax.60\))
    
      - [Global::warning](https://msdn.microsoft.com/en-us/library/gg802948\(v=ax.60\))
    
    The Info.line and Info.num methods are inherited from the [xInfo](https://msdn.microsoft.com/en-us/library/gg949025\(v=ax.60\)) class.

## Remove the Recurrence Button from the Batch Processing Dialog

When you implement a class by using the batch processing system, call the Args.parmEnum method, and pass the NoYes::Yes system enumeration value to remove the **Recurrence** button.

The [NoYes](https://msdn.microsoft.com/en-us/library/gg866262\(v=ax.60\)) system enumeration determines whether the recurrence button is removed from the batch processing dialog. The default value is NoYes::No.

In the following code example, the [InventTransferMultiShip](https://msdn.microsoft.com/en-us/library/gg840232\(v=ax.60\)) class is implemented. The [BatchDialog::main](https://msdn.microsoft.com/en-us/library/gg737955\(v=ax.60\)) method creates the **Batch processing** dialog.

static void noRecurrenceButton(Args \_args)

{

Args a;

InventTransferMultiShip inventTransferMultiShip;

;

a = new Args();

inventTransferMultiShip = InventTransferMultiShip::construct();

a.caller(inventTransferMultiShip);

a.parmEnum(NoYes::Yes);

BatchDialog::main(a);

}

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

