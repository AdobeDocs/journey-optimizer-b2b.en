---
title: XDM Fields
description: Review the default attribute fields that are synchronized between the Adobe Experience Platform and Journey Optimizer B2B Edition.
exl-id: 8c65fdec-e32d-4ba8-be7b-48522cc3dace
---
# XDM fields

Account audience data is stored as attributes in both XDM Business Account and XDM Business Person classes. The data is periodically synchronized between Adobe Experience Platform and Journey Optimizer B2B Edition. The following sections list the default sets of attributes.

>[!TIP]
>
>You can model XDM Business Person and XDM Business Account classes in a many-to-many relationship by using the XDM Business Account Person Relation class as described in the [Experience Platform XDM documentation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/relationship-b2b).

## XDM Business Account Person Relation attributes

|[Property](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/profile/b2b-person-details.schema.md) |Display name |Journey Optimizer B2B display name |Data type |Description |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
|`personRoles` | Person Roles   | Role | String array | An array of roles associated with the person on the account, such as `owner, accountant, designer`. |

## XDM Business Person attributes

>[!IMPORTANT]
>
>The `workEmail.Address` attribute is required. If it is empty for an account audience member, that person is not ingested and is omitted from account journeys and buying groups that reference the audience. 

|[Property](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/profile/b2b-person-details.schema.md) |Display name |Journey Optimizer B2B display name |Data type |Description |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
|`b2b.companyName` |Company Name    |Company Name |String  |Name of the company a business person is associated with. |
|`b2b.companyWebsite` |Company Website   |Website    |String  |Website of the company a business person is associated with. |
|`b2b.isMarketingSuspended` |Marketing Suspended Indicator   |Marketing Suspended    |Boolean |The value indicates whether marketing is suspended for the person.   |
|`b2b.marketingSuspendedCause`  |Marketing Suspended Cause  |Marketing Suspended Cause  |String |If marketing is suspended for the person, this property provides the reason why.   |
|`b2b.personStatus` |Person Status      |Lead Status  |String  |Field recording the current marketing/sales status of the Person.  |
|`consents.marketing.email.reason` |Opt-out reason  |Unsubscribed Reason        |String  |Reason associated with the email opt-out. |
|`consents.marketing.email.val`   |Unsubscribed    |Unsubscribed   |String  |If unsubscribed is true (for example, value = 1), then set `consents.marketing.email.val` as (n). If unsubscribed is false (for example, value = 0), then set `consents.marketing.email.val` as null.    |
|`extendedWorkDetails.jobTitle` |Job Title  |Job Title     |String  |Job title of the person.   |
|`faxPhone.number`     |Number       |Fax Number    |String  |Fax phone number.    |
|`mobilePhone.number`  |Number   |Mobile Phone Number   |String  |The mobile phone number associated with the person.      |
|`person.birthDate` |Birth date(YYY-MM-DD)    |Date of Birth     |String  |The full date that a person was born. YYYY-MM-DD       |
|`person.name.courtesyTitle`  |Courtesy Title  |Salutation   |String  |Normally an abbreviation of a person's title, honorific, or salutation. The courtesyTitle is used in front of the full or last name in opening texts. For example, Mr., Ms., or Dr. |
|`person.name.firstName`   |First Name      |First Name     |String  |The first segment of the name in the written order that is most commonly accepted in the language of the name. In many cultures, it is the preferred personal or given name. The firstName and lastName properties have been introduced to maintain compatibility with existing systems that model names in a simplified, non-semantic, and non-internationalizable way. Using `xdm:fullName` is always preferable.   |
|`person.name.lastName` |Last Name      |Last Name    |String  |The last segment of the name in the written order that is most commonly accepted in the language of the name. In many cultures, it is the inherited family name, surname, patronymic, or matronymic name. The firstName and lastName properties have been introduced to maintain compatibility with existing systems that model names in a simplified, non-semantic, and non-internationalizable way. Using `xdm:fullName` is always preferable.|
|`person.name.middleName`  |Middle Name    |Middle Name   |String  |Middle, alternative, or additional names supplied between the first name and last name. |
|`workAddress.city ` |City            |City      |String  |The name of the city.                          |
|`workAddress.country` |Country      |Country      |String  |The name of the government-administered territory. Other than `xdm:countryCode`, it is a free-form field that can have the country name in any language.        |
|`workAddress.postalCode`  |Postal code   |Postal Code    |String  |The postal code of the location. Postal codes are not available for all countries. In some countries, it contains only part of the postal code. |
|`workAddress.state`    |State    |State   |String  |The name of the state for the address. It is a free-form field.|
|`workAddress.street1`|Street 1  |Address   |String  |Primary street level information, apartment number, street number, and street name. |
|`workEmail.address` |Address        |Email Address    |String  |**Required field** <br/>The technical address, for example, `<name@domain.com>` as commonly defined in RFC2822 and subsequent standards. |
|`workEmail.status` |Status   |Email Suspended  |String  |An indication as to the ability to use the email address.    |
|`workPhone.number`    |Number        |Phone Number     |String  |Work phone number.  |

## XDM Business Account attributes

>[!IMPORTANT]
>
>The `accountName` attribute is required. If it is empty for an account in an account audience, that account is not ingested and is omitted from account journeys and buying groups that reference the audience. 

|[Property](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/account/account-details.schema.md) |Display name |Journey Optimizer B2B display name |Data type |Description |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
|`accountBillingAddress.city`|City  |City  |String |The name of the city used in the billing address. |
|`accountBillingAddress.country` | Country   |Country   |String   |The name of the government-administered territory used in the billing address. Other than `xdm:countryCode`, it is a free-form field that can have the country name in any language. |
|`accountBillingAddress.postalCode` | Postal code | Address Postal Code | String | The postal code of the location of the billing address. Postal codes are not available for all countries. In some countries, it contains only part of the postal code. |
|`accountBillingAddress.region` | Region | Address Region | String |The region, county, or district portion of the billing address. |
|`accountBillingAddress.state` | State | State | String | The name of the state for the billing address. It is a free-form field. |
|`accountBillingAddress.street1` | Street 1 | Street 1  | String |Primary street level information for the billing address, which would typically include the apartment number, street number, and street name. |
|`accountName` | Name | Name | String | **Required field** <br/>Name of the company. Up to 255 characters are allowed in this field. | 
|`accountOrganization.annualRevenue.amount` | Annual Revenue | Annual Revenue | Number |Estimated amount of annual revenue of the organization. |
|`accountOrganization.industry` | Industry | Industry | String |The industry attributed to the organization. It is a free-form field, and it is advisable to use a structured value for queries or to use the `xdm:classifier` property. |
|`accountOrganization.logoUrl`  | Logo Url | Logo Url | String | Path to be combined with the URL of a Salesforce instance (for example, `https://yourInstance.salesforce.com/`) to generate a URL to request the social network profile image associated with the account. The generated URL returns an HTTP redirect (code 302) to the social network profile image for the account. |
|`accountOrganization.numberOfEmployees` | Number of employees | Num Employees | Integer |The number of employees at the organization. | 
|`accountOrganization.SICCode` | SIC Code | SIC Code | String |The Standard Industrial Classification (SIC) code is a four-digit code that categorizes the industries that companies belong to based on their business activities. |
|`accountOrganization.website` | Website URL | Domain Name  | String |The URL of the organization's website. |
|`accountPhone.number` | N/A | Account Phone Number | String |The phone number associated with the account.  |
|`accountSourceType` | N/A  | Source Type | String |Source type for the account. |

<!-- ## XDM Opportunity attributes

|[Property](https://github.com/adobe/xdm/blob/master/docs/reference/adobe/experience/marketo/opportunity-marketo.schema.md) |Display name |Journey Optimizer B2B display name |Data type |Description |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
|`opportunityName` | Opportunity Name   | ? |String  | Subject or descriptive name, such as the expected order or company name, for the opportunity. |
|`opportunityDescription` | Opportunity Description   | ?    |String  | Additional information to describe the opportunity, such as possible products to sell or past purchases from the customer. |
|`opportunityType` | Opportunity Type   | ?   | String | ?   |
|`opportunityStage` | Opportunity Stage   | ?   | String | Sales stage of the opportunity to aid the sales team in their efforts to win it.  |
|`fiscalQuarter` | Fiscal Quarter   | ?   | String | The fiscal quarter that the opportunity is targeted.   |
|`fiscalYear` | Fiscal Year   | ?   | String | The fiscal year that the opportunity is targeted.   |
|`fiscalCategory` | Fiscal Category   | ?   | String | ?   |
|`fiscalCategoryName` | Fiscal Category Name  | ?   | String | Forecast category name that is displayed in reports for a particular forecast category.   |
|`isClosed` | Closed Flag  | ?   | String | Flag that indicates if the opportunity is closed.   |
|`isWon` | Won Flag  | ?   | String | Flag that indicates if the opportunity is won.  |
|`probabilityPercentage` | Probability Percentage  | ?   | String | Likelihood of closing the opportunity, stated as a percentage.  |
|`opportunityAmount.amount` | Opportunity Amount  | ?   | String | Estimated total sale amount for the opportunity.   |
|`expectedRevenue.amount` | Expected Revenue  | ?   | String | Calculated revenue based on the Amount and Probability.   |
|`opportunityQuantity` | Opportunity Quantity  | ?   | String | Total of all quantity field values for all products in the related Products list for the opportunity.   |
|`expectedCloseDate` | Expected Close Date  | ?   | String | Expected date of closure for the opportunity.   |
|`lastActivityDate` | Last Activity Date  | ?   | String | Last activity date for the opportunity.  |
|`leadSource` | Lead Source  | ?   | String | Source of the opportunity, such as Advertisement, Partner, or Web.   |
|`nextStep` | Next Step  | ?   | String | Description of the next task for closing the opportunity.   |
-->
