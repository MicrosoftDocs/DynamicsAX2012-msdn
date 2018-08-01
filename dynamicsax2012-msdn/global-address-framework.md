---
title: Global Address Framework
TOCTitle: Global Address Framework
ms:assetid: 0f09e758-0d3f-42f4-937e-bd26e0e9b583
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh608233(v=AX.60)
ms:contentKeyID: 39555622
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Global Address Framework [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The global address book (GAB) framework allows information to be shared across companies and entities. Records in the GAB contain fields for postal address, email address, and other similar information. GAB records also contain fields for the associated person or organization, which is called the party. The following table lists key concepts of the global address book.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Term</p></th>
<th><p>Definition</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Party</p></td>
<td><p>An entity that assumes a legally binding role when participating in contractual relationships. A party can be a person or organization and it can be internal or external to an organization.</p>
<p>A person or organization that participates in economic activities. A party can be internal or external to an organization.</p></td>
</tr>
<tr class="even">
<td><p>Address book</p></td>
<td><p>A list of address book records.</p></td>
</tr>
<tr class="odd">
<td><p>Location</p></td>
<td><p>A broad term that can mean any of the following loosely related items:</p>
<ul>
<li><p>A geographic point or region.</p></li>
<li><p>A physical address.</p></li>
<li><p>An electronic address.</p></li>
<li><p>A functional facility.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Roles that are associated with party records include customer, vendor, prospect, and contact. An individual party can be associated with one or more party roles in a Microsoft Dynamics AX company.

## Date Effective Names

Names for organization and person are date-effective. Date-effective names are supported by the use of the **ValidTimeStateFieldType** property of the table. The affected tables include:

1.  DirOrganizationName

2.  DirPersonName

## Security Policies and Address Book

You can use the security policies that are under **AOT** \> **Security** \> **Policies** to restrict which parties or locations can be accessed by users. You can use policies to restrict access to parties or locations by legal entity or by address book.

## Restricting Party by Legal Entity

You can restrict user access to party records by legal entity. Users belonging to that legal entity can view only the party records associated with that legal entity. There are two policies in this group, and they must be implemented together to meet the full requirement of this data restriction:

  - DirRestrictViewPartyInLegalEntity

  - DirRestrictViewPartyTableInLegalEntity

## Restricting Parties by Address Book

You can restrict access to party records by address book. Once an address book is created and populated, you create a team and add users to the team. You then assign the team to one or more address books. Only members of a team assigned to an address book will have access to its records. The following policies are used together to meet the full requirement of this data restriction:

  - DirRestrictPartyTableInAddressBook

  - DirRestrictViewPartyInAddressBook

  - DirRestrictViewPartyInAddressBook\_Cust

  - DirRestrictViewAddressBook

## Restricting Locations

You restrict user access to private address and contact information through the LogisticsLocationPrivacy policy. This policy is automatically enabled and is integrated into the address book infrastructure through the global address book parameters. The restrictions are role-based.

1.  DirRestrictPartyTableInAddressBook

2.  DirRestrictViewPartyInAddressBook

3.  DirRestrictViewPartyInAddressBook\_Cust

4.  DirRestrictViewAddressBook

## Associating Address Information to a Party Record

The **DirParty** class handles most of the operations related to address book for a party. You can also use the concrete classes for certain roles, such as CustomerEntity, VendorEntity, and ContactPersonEntity. The address related methods in the DirParty class include the following:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>createOrUpdateContactInfo</p></td>
<td><p>Creates or updates an electronic address record for a party. This method takes a DirPartyContactInfoView parameter.</p></td>
</tr>
<tr class="even">
<td><p>createOrUpdatePostalAddress</p></td>
<td><p>Creates or updates a postal address record for a party. This method takes a DirPartyPostalAddressView parameter.</p></td>
</tr>
<tr class="odd">
<td><p>getPrimaryElectronicAddressLocation</p></td>
<td><p>Retrieves the primary electronic address of a particular party record for a particular method type, such as Phone, Fax, Telex, E-mail, or URL. This method returns a LogisticsLocationEntity class instance.</p></td>
</tr>
<tr class="even">
<td><p>getPrimaryPostalAddressLocation</p></td>
<td><p>Retrieves the primary postal address of a particular party record. This method returns a LogisticsLocationEntity class instance.</p></td>
</tr>
<tr class="odd">
<td><p>parm* methods</p></td>
<td><p>These are attributes of party information that can be either retrieved or updated.</p></td>
</tr>
<tr class="even">
<td><p>addLocation</p></td>
<td><p>A static method that creates a relationship between a party and a location. This method also creates the roles relationship table.</p></td>
</tr>
<tr class="odd">
<td><p>findElectronicAddressByRole</p></td>
<td><p>A static method that finds the contact information about a party of a certain type and purpose. If no primary record is found, it returns the first record, based on the date of creation. This method returns a LogisticsElectronicAddress record.</p></td>
</tr>
<tr class="even">
<td><p>findPostalAddressByRole</p></td>
<td><p>A static method that finds the contact information about a party of a certain purpose. If no primary record is found, it returns the first record, based on the date of creation. This method returns a LogisticsPostalAddress record.</p></td>
</tr>
<tr class="odd">
<td><p>primaryElectronicAddress</p></td>
<td><p>A static method that retrieves the primary electronic address of a party, based on the method type. This method returns a LogisticsElectronicAddress record.</p></td>
</tr>
<tr class="even">
<td><p>primaryPostalAddress</p></td>
<td><p>A static method that retrieves the primary postal address of a party. This method returns a LogisticsPostalAddress record.</p></td>
</tr>
<tr class="odd">
<td><p>write</p></td>
<td><p>Commits any changes to the party record information.</p></td>
</tr>
</tbody>
</table>



> [!TIP]
> <P>Concepts such as customer and vendor are more specific than party is. Some of those concepts correspond to X++ classes that derive from the DirParty class. Examples include the classes CustomerEntity, VendorEntity, and ContactPersonEntity. We recommend that you use the most specific class that applies to whichever party concept you are working with.</P>




> [!NOTE]
> <P>Classes such as DirParty, and the enhancements that make address updates necessary in only one location, were introduced in Microsoft Dynamics AX 2012.</P>



## See also

[How To: Update a Postal Address for a Contact Person](how-to-update-a-postal-address-for-a-contact-person.md)

[DirParty Class](https://msdn.microsoft.com/en-us/library/gg738910\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

