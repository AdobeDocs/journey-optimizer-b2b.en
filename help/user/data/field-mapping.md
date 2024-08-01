---
title: XDM Field Mapping
description: Review the field mapping between the AEP XDM schema, Marketo Engage, and Journey Optimizer B2B Edition.
exl-id: 8c65fdec-e32d-4ba8-be7b-48522cc3dace
---
# XDM field mapping

The Data Transfer Service (DTS) is responsible for synchronizing data from Adobe Experience Platform to Journey Optimizer B2B Edition. DTS relies on mappings between Experience Platform XDM schema fields and their equivalents in Marketo Engage.

## XDM Business Person default field mappings

|[XDM Business Person](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/profile/b2b-person-details.schema.md) |XDM display name |Marketo Engage display name |XDM type |Marketo yype |XDM Description |
|------------------- |---------------------------------- |--------------------------- |-------- |------------ |--------------- |
|`b2b.companyName` |Company Name    |Company Name |string  |string      |Name of the company a business person is associated with. |
|`b2b.companyWebsite` |Company Website   |Website    |string  |url         |Website of the company a business person is associated with. |
|`b2b.isMarketingSuspended` |Marketing Suspended Indicator   |Marketing Suspended    |boolean |boolean     |The value indicates whether marketing is suspended for the person.   |
|`b2b.marketingSuspendedCause`    |Marketing Suspended Cause  |Marketing Suspended Cause  |string  |string      |If marketing is suspended for the person, this property provides the reason why.   |
|`b2b.personStatus` |Person Status      |Lead Status       |string  |string     |Field recording the current marketing/sales status of the Person.  |
|`consents.marketing.email.reason` |Opt-out reason       |Unsubscribed Reason        |string  |string      | Reason associated with the email opt-out. |
|`consents.marketing.email.val`   |Unsubscribed    |Unsubscribed   |string  |boolean     |If unsubscribed is true (for example, value = 1), then set `consents.marketing.email.val` as (n). If unsubscribed is false (for example, value = 0), then set consents.marketing.email.val as null.    |
|`extendedWorkDetails.jobTitle` |Job Title     |Job Title     |string  |string      |Job title of the person.   |
|`faxPhone.number`     |Number       |Fax Number    |string  |phone       |Fax phone number.    |
|`mobilePhone.number`  |Number   |Mobile Phone Number   |string  |phone       |The mobile phone number associated with the person.      |
|`person.birthDate` |Birth date(YYY-MM-DD)    |Date of Birth     |string  |date        |The full date that a person was born. YYYY-MM-DD       |
|`person.name.courtesyTitle`  |Courtesy Title  |Salutation   |string  |string      |Normally an abbreviation of a person's title, honorific, or salutation. The courtesyTitle is used in front of the full or last name in opening texts. For example, Mr., Ms., or Dr. |
|`person.name.firstName`   |First Name      |First Name     |string  |string      |The first segment of the name in the written order that is most commonly accepted in the language of the name. In many cultures, it is the preferred personal or given name. The firstName and lastName properties have been introduced to maintain compatibility with existing systems that model names in a simplified, non-semantic, and non-internationalizable way. Using `xdm:fullName` is always preferable.   |
|`person.name.lastName` |Last Name      |Last Name    |string  |string      |The last segment of the name in the written order that is most commonly accepted in the language of the name. In many cultures, it is the inherited family name, surname, patronymic, or matronymic name. The firstName and lastName properties have been introduced to maintain compatibility with existing systems that model names in a simplified, non-semantic, and non-internationalizable way. Using `xdm:fullName` is always preferable.|
|`person.name.middleName`  |Middle Name    |Middle Name   |string  |phone       |Middle, alternative, or additional names supplied between the first name and last name. |
|`workAddress.city ` |City            |City      |string  |string      |The name of the city.                          |
|`workAddress.country` |Country      |Country      |string  |string      |The name of the government-administered territory. Other than `xdm:countryCode`, it is a free-form field that can have the country name in any language.        |
|`workAddress.postalCode`  |Postal code   |Postal Code    |string  |string      |The postal code of the location. Postal codes are not available for all countries. In some countries, it contains only part of the postal code. |
|`workAddress.state`    |State    |State   |string  |string      |The name of the state for the address. It is a free-form field.|
|`workAddress.street1`|Street 1  |Address   |string  |text        |Primary street level information, apartment number, street number, and street name. |
|`workEmail.address` |Address        |Email Address    |string  |email       |The technical address, for example, `<name@domain.com>` as commonly defined in RFC2822 and subsequent standards. |
|`workEmail.status` |Status   |Email Suspended            |string  |boolean     |An indication as to the ability to use the email address.    |
|`workPhone.number`    |Number        |Phone Number     |string  |phone       |Work phone number.  |

## XDM Business Account default field mappings

|[XDM Business Account](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/account/account-details.schema.md) |XDM display name |Marketo Engage display name |XDM type |Marketo Engage type |XDM description |
|------------------- |---------------------------------- |--------------------------- |-------- |------------ |--------------- |
|`accountBillingAddress.city`|City  |City  |string |string  | The name of the city used in the billing address. |
|`accountBillingAddress.country` | Country   |Country   |string   |string   |The name of the government-administered territory used in the billing address. Other than `xdm:countryCode`, it is a free-form field that can have the country name in any language. |
|`accountBillingAddress.postalCode` | Postal code | Address Postal Code | string | string  | The postal code of the location of the billing address. Postal codes are not available for all countries. In some countries, it contains only part of the postal code. |
|`accountBillingAddress.region` | Region | Address Region | string | string | The region, county, or district portion of the billing address. |
|`accountBillingAddress.state` | State | State | string | string | The name of the state for the billing address. It is a free-form field. |
|`accountBillingAddress.street1` | Street 1 | Street 1  | string | string  | Primary street level information for the billing address, which would typically include the apartment number, street number, and street name. |
|`accountName` | Name | Name | string | string | Name of the company. Up to 255 characters are allowed in this field. | 
|`accountOrganization.annualRevenue.amount` | Annual Revenue | Annual Revenue | number | currency | Estimated amount of annual revenue of the organization. |
|`accountOrganization.industry` | Industry | Industry | string | string | The industry attributed to the organization. It is a free-form field, and it is advisable to use a structured value for queries or to use the `xdm:classifier` property. |
|`accountOrganization.logoUrl`  | Logo Url | Logo Url | string | string | Path to be combined with the URL of a Salesforce instance (for example, `https://yourInstance.salesforce.com/`) to generate a URL to request the social network profile image associated with the account. The generated URL returns an HTTP redirect (code 302) to the social network profile image for the account. |
|`accountOrganization.numberOfEmployees` | Number of employees | Num Employees | integer | integer | The number of employees at the organization. | 
|`accountOrganization.SICCode` | SIC Code | SIC Code | string | string | The Standard Industrial Classification (SIC) code, which is a four-digit code that categorizes the industries that companies belong to based on their business activities. |
|`accountOrganization.website` | Website URL | Domain Name  | string | string | The URL of the organization's website. |
|`accountPhone.number` | N/A | Account Phone Number | string | string | The phone number associated with the account.  |
|`accountSourceType` | N/A  | Source Type | string | string | Source type for the account. |
