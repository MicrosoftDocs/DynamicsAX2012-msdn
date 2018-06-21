---
title: 'How To: Update a Postal Address for a Contact Person'
TOCTitle: 'How To: Update a Postal Address for a Contact Person'
ms:assetid: 4b748300-b527-4dbd-ae2d-994877cb9017
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh608238(v=AX.60)
ms:contentKeyID: 39555627
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How To: Update a Postal Address for a Contact Person [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you add postal and electronic address information to entities such as customer, vendor, or contact person by using the **DirPartyPostalAddressView** and **DirPartyContactInfoView** views.

The following X++ job illustrates how to add postal and electronic address information to a contact person. To create a job in the AOT, right-click the **Jobs** node, and then click **New Job**.

    static void AddressJob(Args _args)  // X++ job.
    {
    
        // Declare variables: views.
        DirPartyContactInfoView contactInfo;
        DirPartyPostalAddressView postalAddress;
    
        // Declare variables: tables.
        ContactPerson contactperson;
        DirPartyTable partyTable = DirPartyTable::findByName("Contoso", DirPartyType::Organization);
        LogisticsPostalAddress logisticsPostalAddressInfo;
    
        // Declare variables: classes.
        ContactPersonEntity contactPersonEntity;
        LogisticsLocationEntity entity;
    
        // Declare variables: extended data types.
        Phone phone;
    
        // Declare variables: primitives.
        str firstName;
        str middleName;
        str lastName;
        
        // Create and populate the contact person.
        contactPersonEntity = ContactPersonEntity::construct(contactPerson);
        contactPersonEntity.parmFirstName('Contact');
        contactPersonEntity.parmMiddleName('M.');
        contactPersonEntity.parmLastName('Person');
        contactPersonEntity.parmAssistantName('AssistantName');
        contactPersonEntity.parmBillingInformation('Billing info');
        contactPersonEntity.parmCharacter('Character description');
        contactPersonEntity.parmComputerNetworkName('Computer network name');
        contactPersonEntity.parmContactForParty(partyTable.RecId);
        contactPersonEntity.parmContactMemo('Memo');
        contactPersonEntity.parmContactPersonId('CP61');
        contactPersonEntity.parmLoyalty('Loyalty');
        contactPersonEntity.parmMileage('Mileage');
        contactPersonEntity.parmOfficeLocation('Office location');
        contactPersonEntity.parmOutlookCategories('Outlook categories');
        contactPersonEntity.parmProfession('Profession');
        contactPersonEntity.parmSensitivity(smmSensitivity::Personal);
        contactPersonEntity.parmSpouse('Spouse');
        contactPersonEntity.parmTimeAvailableFrom(1000);
        contactPersonEntity.parmTimeAvailableTo(2000);
        contactPersonEntity.write();
    
        // Populate the postal address information by using the view.
        postalAddress.Street = 'One Microsoft Way';
        postalAddress.City = 'Redmond';
        postalAddress.State = 'WA';
        postalAddress.ZipCode = '98052';
        postalAddress.CountryRegionId = 'US';
    
    
    
    
        // Update the postal address information.
        contactPersonEntity.createOrUpdatePostalAddress(postalAddress);
    
        // Populate the contact information by using the view.
        contactInfo.Locator = '555-555-5555';
        contactInfo.Type = LogisticsElectronicAddressMethodType::Phone;
        contactInfo.IsPrimary = true;
        // Update the contact information.
        contactPersonEntity.createOrUpdateContactInfo(contactInfo);
        
        // Verify that the data was stored correctly.
        firstName = contactPersonEntity.parmFirstName();
        middleName = contactPersonEntity.parmMiddleName();
        lastName = contactPersonEntity.parmLastName();
        
        logisticsPostalAddressInfo = entity.getPostalAddress(); 
        phone = contactPersonEntity.getPrimaryElectronicAddressLocation().getPhone();
    
        info(firstName + " " + middleName + " " + LastName +
            " is located at " + logisticsPostalAddressInfo.StreetNumber +
            " " + logisticsPostalAddressInfo.Street + ", " +
            logisticsPostalAddressInfo.City + ", " +
            logisticsPostalAddressInfo.State + " " +
            logisticsPostalAddressInfo.ZipCode +
            ". They can be contacted at " + phone + ".");
    }
    /***** Infolog display
    Message (03:09:43 pm)
    Contact M. Person is located at One Microsoft Way, Redmond, WA 98052. Phone number is 555-555-5555.

## See also

[Global Address Framework](global-address-framework.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

