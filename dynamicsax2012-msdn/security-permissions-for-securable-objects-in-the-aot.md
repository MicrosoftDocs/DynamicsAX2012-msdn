---
title: Security Permissions for Securable Objects in the AOT
TOCTitle: Security Permissions for Securable Objects in the AOT
ms:assetid: 0ab8b4a8-0594-4bad-9196-fd8465b89eb8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg843558(v=AX.60)
ms:contentKeyID: 35240364
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Security Permissions for Securable Objects in the AOT 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the Application Object Tree (AOT) to create and modify permissions on securable objects. Permissions apply to items such as forms, SSRS reports, and services. For the detailed information about permissions, see [Role-Based Security Concepts Overview](role-based-security-concepts-overview.md).

## Securable Object Nodes in the AOT

The following list represents the AOT expanded as necessary to reveal the major security related nodes:

  - AOT
    
      - Forms
        
          - YourForm
            
              - Permissions
    
      - Parts
        
          - Info Parts
            
              - YourInfoPart
                
                  - Permissions
    
      - SSRS Reports
        
          - YourSSRSReport
            
              - Designs
                
                  - RoleCenter
                    
                      - Permissions
    
      - Reports
        
          - YourReport
            
              - Permissions
    
      - Services
        
          - YourService
            
              - Operations
                
                  - YourOperation
                    
                      - Permissions
    
      - Security

## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

[Security Node in the AOT](https://msdn.microsoft.com/en-us/library/gg731863\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

