---
title: 'Code Example: SecurityUtil Class for Accessing Role and Object Permissions'
TOCTitle: 'Code Example: SecurityUtil Class for Accessing Role and Object Permissions'
ms:assetid: 18a156b1-34a8-4179-b473-233a7ce5f589
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ190221(v=AX.60)
ms:contentKeyID: 47985886
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Code Example: SecurityUtil Class for Accessing Role and Object Permissions 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic provides code examples that use the SecurityUtil class. You can use the SecurityUtil class to access security permissions information about roles and objects.

The following system classes are available for accessing information about role-based security settings:

  - [SecurityInferencePermissions Class](https://msdn.microsoft.com/en-us/library/gg926142\(v=ax.60\))

  - [SecurityPolicy Class](https://msdn.microsoft.com/en-us/library/gg957658\(v=ax.60\))

  - [SecurityRights Class](https://msdn.microsoft.com/en-us/library/gg957675\(v=ax.60\))

  - [SecurityTableRights Class](https://msdn.microsoft.com/en-us/library/gg957689\(v=ax.60\))

  - [SecurityUtil Class](https://msdn.microsoft.com/en-us/library/gg957695\(v=ax.60\))

## Code Example 1: getRolePermissions

You give the SecurityUtil::getRolePermissions method a security role ID number, and receive a set of containers that describe all the security permissions that are associated with the role. The comment in the following code example documents the elements in each returned container.
```X++  
    static void GSecUtil_getRolePermissions_Job2(Args _args)
    {
        container      conrOuter, conrInner;
        SecurityRole   xrecSecurityRole;
        str            sTemp3;
        str            sAccRight, sSecuTyp;
        SecurableType  secuTyp;
        AccessRight    accRight;
        int            ii = 0;
    
        select RecId from xrecSecurityRole
            where xrecSecurityRole.AotName == 'SystemUser';
       
        conrOuter = SecurityUtil::getRolePermissions
            (xrecSecurityRole.RecId);  // 495054 in our test.
        
        // The returned conrOuter holds numerous inner containers.
        // The format of each inner container is:
        //  1. NameOfObject
        //  2. ObjectType       // enum SecurableType
        //  3. ChildObjectName  // Such as a table field name, or a form control name.
        //  4. AccessRight      // enum AccessRight
        
        for (ii=1; ii<conLen(conrOuter); ii++)
        {
            conrInner = conPeek(conrOuter, ii);
            
            secuTyp  = conPeek(conrInner, 2);
            sSecuTyp = enum2str(secuTyp);
            
            accRight  = conPeek(conrInner, 4);
            sAccRight = enum2str(accRight);
            
            sTemp3 = con2Str(conrInner, "  ,  ");
            info("getRolePermissions:  " + sTemp3 + ".   (" + sSecuTyp + " / " + sAccRight + ")");
        }
            
        // The input parameters of method SecurityUtil::getRoleEffectiveAccess
        // are similar to the output container format 
        // of method SecurityUtil::getRolePermissions.
    }
    /*** Subset of the 600 lines shown in the Infolog window.
    *** The italicized row of data, which mentions 'AIFOPERATIONCONTEXT',
    *** is used as input in the next code example section:
    
    getRolePermissions:  WORKFLOWWORKITEMDELEGATIONPARAMETERS  ,  44  ,    ,  5.   (Table field / Full control)
    getRolePermissions:  WORKFLOWWORKITEMQUEUE  ,  44  ,    ,  1.   (Table field / View)
    getRolePermissions:  WORKFLOWWORKITEMQUEUEASSIGNEE  ,  44  ,    ,  1.   (Table field / View)
    getRolePermissions:  WORKFLOWWORKITEMQUEUEGROUP  ,  44  ,    ,  1.   (Table field / View)
    getRolePermissions:  WORKFLOWWORKITEMQUEUEGROUPRELATION  ,  44  ,    ,  1.   (Table field / View)
    getRolePermissions:  WORKFLOWWORKITEMTABLE  ,  44  ,    ,  2.   (Table field / Edit)
    getRolePermissions:  XREFTABLERELATION  ,  44  ,    ,  1.   (Table field / View)
    getRolePermissions:  AIFOPERATIONCONTEXT  ,  45  ,  GETSCHEMA  ,  5.   (Class method / Full control)
    getRolePermissions:  AIFPORTMANAGER  ,  45  ,  GETSERVICESVERSIONID  ,  5.   (Class method / Full control)
    getRolePermissions:  AIFRUNTIMECACHEMANAGER  ,  45  ,  CACHEENTRY  ,  5.   (Class method / Full control)
    getRolePermissions:  AIFRUNTIMECACHEMANAGER  ,  45  ,  CACHINGENABLED  ,  5.   (Class method / Full control)
    getRolePermissions:  AIFRUNTIMECACHEMANAGER  ,  45  ,  FLUSHCACHE  ,  5.   (Class method / Full control)
    getRolePermissions:  AIFRUNTIMECACHEMANAGER  ,  45  ,  RETRIEVEENTRY  ,  5.   (Class method / Full control)
    getRolePermissions:  AIFSCHEMAINFO  ,  45  ,  PARMSCHEMAXML  ,  5.   (Class method / Full control)
    getRolePermissions:  AIFSCHEMAREPOSITORY  ,  45  ,  GETSHAREDTYPESSCHEMA  ,  5.   (Class method / Full control)
    getRolePermissions:  AIFUSERSESSIONSERVICE  ,  45  ,  APPLYTIMEZONE  ,  5.   (Class method / Full control)
    ***/
```
## Code Example 2: getRoleEffectiveAccess

You give the SecurityUtil::getRoleEffectiveAccess method a role and a securable object, and receive a value of the [AccessRight](https://msdn.microsoft.com/en-us/library/gg882002\(v=ax.60\)) system enum that indicates the access rights that the role has to the object.
```X++  
    static void GSecUtil_getRoleEffectiveAccess_Job3(Args _args)  // X++ job in AOT > Jobs.
    {
        AccessRight accRight;  // System enum.
        
        // This input data is from the italicized line in the previous example.
        //getRolePermissions:  AIFOPERATIONCONTEXT  ,  45  ,  GETSCHEMA  ,  5.   (Class method / Full control)
        //
        accRight = SecurityUtil::getRoleEffectiveAccess
            (495054,  // "SystemUser" in our test.
            "AIFOPERATIONCONTEXT",
            SecurableType::ClassMethod,  // 45
            "GETSCHEMA"
            );
        info(strFmt("AccessRight:  %1", accRight));
        
        // The input parameters of method SecurityUtil::getRoleEffectiveAccess
        // are partly similar to the output container format 
        // of method SecurityUtil::getRolePermissions.
    }
    /*** Pasted from Infolog:
    Message (12:58:54 pm)
    AccessRight:  Full control
    ***/
```
## See also

[Microsoft.Dynamics.AX.Framework.Services.Metadata.Enums.AccessRight](https://msdn.microsoft.com/en-us/library/hh186891\(v=ax.60\))

[Set up user security in Microsoft Dynamics AX](https://msdn.microsoft.com/en-us/library/aa834424\(v=ax.60\))

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

