---
title: CLR Interop Issues Across Tiers
TOCTitle: CLR Interop Issues Across Tiers
ms:assetid: eefd8d89-7a03-47fa-bac4-e5b205d939db
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc308397(v=AX.60)
ms:contentKeyID: 35253283
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# CLR Interop Issues Across Tiers [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

CLRObject instances cannot be passed between Microsoft Dynamics AX tiers.

An X++ method marked with the keyword server runs on the Application Object Server (AOS) tier. Your server method SS cannot return a .NET Framework object to another method CC that calls SS from the client tier.

## Example

The following X++ code example has a server method that is called by a client method. The server method returns a .NET Framework object of type System.String. However, .NET Framework objects cannot be serialized and de-serialized by Microsoft Dynamics AX. Therefore they cannot be returned to a caller that is running on a different tier (in this case, the client tier).

An attempt to run this code example causes an error message that states that the CLRObject is not initialized.

### ![Cc308397.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc308397.collapse_all(en-us,AX.60).gif")Server Method

This code represents the server method that is called from the client.

    public class RunOnTheServerClass
    {
        public static server System.String GetASystemStringMethod()
        {
            System.String sNet;
            ;
            // Enable CLR interop on a server method.
            new InteropPermission(InteropKind::ClrInterop).assert();
    
            sNet = "The return value.";
            return sNet;
        }
    }

### ![Cc308397.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc308397.collapse_all(en-us,AX.60).gif")Client Method, the Caller

This code represents the client job that calls the server method.

    static void RunOnClientJob(Args _args)
    {
        System.String sNet;
        str strXpp;
        ;
        // This call fails.
        sNet = RunOnTheServerClass ::GetASystemStringMethod();
    
        strXpp = sNet;
        info(strXpp);
    }

## See also

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

