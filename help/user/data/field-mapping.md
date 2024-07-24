---
title: XDM field mapping
description: Review the field mapping between the AEP XDM schema, Marketo Engage, and Journey Optimizer B2B Edition.
---
# XDM field mapping

The Data Transfer Service (DTS) in  is responsible for synchronizing data from Adobe Experience Platform to Journey Optimizer B2B Edition. DTS relies on mappings between Experience Platform XDM schema fields and their equivalents in Marketo Engage.

## XDM Business Person default field mappings

|XDM Business Person |Marketo Engage Person Display Name |AJO B2B Person Display Name |XDM Type |Marketo Type |XDM Description |
|------------------- |---------------------------------- |--------------------------- |-------- |------------ |--------------- |
|`workAddress.street1`   |Address                    |N/A                          |string  |text        |Primary street level information, apartment number, street number, and street name. |
|`workAddress.city `     |City            |City      |string  |string      |The name of the city.                          |
|`b2b.companyName` |Company Name    |Company  |string  |string      |Name of the company a business person is associated with. |
|`workAddress.country`   |Country      |Country      |string  |string      |The name of the government-administered territory. Other than `xdm:countryCode`, this is a free-form field that can have the country name in any language.        |
|`person.birthDate`    |Date Of Birth    |Date of Birth     |string  |date        |The full date a person was born.  YYYY-MM-DD       |
|`workEmail.address`     |Email Address        |Email Address    |string  |email       |The technical address, for example, '<name@domain.com>' as commonly defined in RFC2822 and subsequent standards.               |
|`workEmail.status`               |Email Suspended            |Email Suspended            |string  |boolean     |An indication as to the ability to use the email address.                                                              |
|`faxPhone.number`     |Fax Number       |N/A     |string  |phone       |Fax phone number.    |
|`person.name.firstName`   |First Name      |First Name     |string  |string      |The first segment of the name in the writing order most commonly accepted in the language of the name. In many cultures this is the preferred personal or given name. The firstName and lastName properties have been introduced to maintain compatibility with existing systems that model names in a simplified, non-semantic, and non-internationalizable way. Using xdm:fullName is always preferable.   |
|`extendedWorkDetails.jobTitle`   |Job Title     |Job Title     |string  |string      |Job title of the person.   |
|`person.name.lastName`  |Last Name      |Last Name    |string  |string      |The last segment of the name in the writing order most commonly accepted in the language of the name. In many cultures this is the inherited family name, surname, patronymic, or matronymic name. The firstName and lastName properties have been introduced to maintain compatibility with existing systems that model names in a simplified, non-semantic, and non-internationalizable way. Using xdm:fullName is always preferable.|
|`b2b.personStatus`     |Lead Status      |N/A       |string  |string     |Field recording the current marketing/sales status of the Person.  |
|`b2b.isMarketingSuspended` |Marketing Suspended   |N/A     |boolean |boolean     |Indicates whether marketing is suspended for the person.   |
|`b2b.marketingSuspendedCause`    |Marketing Suspended Cause  |N/A  |string  |string      |If marketing is suspended for the person, this property provides the reason why.   |
|`person.name.middleName`  |Middle Name    |N/A   |string  |phone       |Middle, alternative, or additional names supplied between the first name and last name. |
|`mobilePhone.number`  |Mobile Phone Number   |Mobile Phone Number   |string  |phone       |Mobile phone number.      |
|`workPhone.number`    |Phone Number        |Phone Number     |string  |phone       |Work phone number.  |
|`workAddress.postalCode`  |Postal Code   |Postal Code    |string  |string      |The postal code of the location. Postal codes are not available for all countries. In some countries, this will only contain part of the postal code. |
|`person.name.courtesyTitle`  |Salutation   |N/A   |string  |string      |Normally an abbreviation of a persons title, honorific, or salutation. The courtesyTitle is used in front of full or last name in opening texts. For example, Mr., Miss, or Dr. |
|`workAddress.state`    |State    |State   |string  |string      |The name of the State. This is a free-form field.|
|`consents.marketing.email.val`   |Unsubscribed    |Unsubscribed   |string  |boolean     |If unsubscribed is true (for example, value = 1), then set `consents.marketing.email.val` as (n). If unsubscribed is false (for example, value = 0), then set consents.marketing.email.val as null.    |
|`consents.marketing.email.reason` |Unsubscribed Reason        |Unsubscribed Reason        |string  |string      |  |
|`b2b.companyWebsite` |Website   |N/A     |string  |url         |Website of the company a business person is associated with. |

