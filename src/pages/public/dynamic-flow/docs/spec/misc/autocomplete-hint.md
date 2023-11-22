---
title: Autocomplete Hint
---

# Autocomplete Hint



A hint applied to a field that tells the client what kind of field it is. This can enable the user agent or assistive
technologies running to automatically suggest or fill in information specific to the user.

Please note that not all values will work on all platforms. For the most benefit, it is helpful to combine controls
with autocomplete hints - i.e a common pattern is to have password control on string schemas that can be combined
with the `PASSWORD` or `NEW_PASSWORD` hints for the best possible user experience.

## Values

| Value | Description |
| ---| --- |
| `additionalName` | An additional (or middle) name. For example: "John" |
| `addressLevel1` | Describes the address in terms of increasing levels of precision within the country in which the address is located. Each country has its own system of administrative levels, and may arrange the levels in different orders when addresses are written. This is the broadest administrative level in the address, i.e. the province within which the locality is found; for example, in the US, this would be the state; in the UK, the post-town. For example: "MA" |
| `addressLevel2` | The second administrative level, in addresses with two or more administrative levels; in the countries with two administrative levels, this would typically be the city, town, village, or other locality within which the relevant street address is found. For example: "Cambridge" |
| `addressLevel3` | The third administrative level, in addresses with three or more administrative levels. |
| `addressLevel4` | The most fine-grained administrative level, in addresses with four administrative levels. |
| `billing` | A modifier that can be combined with other tokens (e.g. `FULL_STREET_ADDRESS`), to indicate that the field is part of the billing address or contact information. |
| `birthdate` | A birthdate, as a full date. For example: "1955-06-08" |
| `birthdateDay` | The day of the month of a birthdate. For example: "8" |
| `birthdateMonth` | The month of the year of a birthdate. For example: "6" |
| `birthdateYear` | The year of a birthdate. For example: "1955" |
| `countryCode` | Valid [ISO 3166-1-alpha-2](https://www.iso.org/iso-3166-country-codes.html) country codes. For example: "US" |
| `countryName` | A country or territory name (could be the same as `COUNTRY_CODE` or the full name). For example: "United States" |
| `creditCardExpiration` | A payment method expiration date. For example: "2014-12" |
| `creditCardExpirationMonth` | The month in which the payment method expires. For example: "12" |
| `creditCardExpirationYear` | The year in which the payment method expires. For example: "2023" |
| `creditCardFamilyName` | A family name, as given on a credit card. For example: "Berners-Lee" |
| `creditCardGivenName` | A given (first) name as given on a payment instrument like a credit card. For example: "Tim" |
| `creditCardMiddleName` | A middle name as given on a payment instrument or credit card. For example: "John" |
| `creditCardName` | The full name as printed on or associated with a payment instrument such as a credit card. For example: "Tim Berners-Lee" |
| `creditCardNumber` | A credit card number or other number identifying a payment method, such as an account number. For example: "4114360123456785" |
| `creditCardSecurityCode` | The security code for the payment instrument; on credit cards, this is the 3-digit verification number on the back of the card. For example: "443" |
| `creditCardType` | The type of payment instrument. For example: "Visa" |
| `email` | An email address. For example: "timbl@w3.org" |
| `familyName` | A family (or "last") name. For example: "Berners-Lee" |
| `fax` | A modifier that can be combined with other tokens (e.g. `PHONE_NUMBER`), to indicate that the field describes a fax machine's contact details |
| `fullStreetAddress` | A street address. This can be multiple lines of text, and should fully identify the location of the address within its second administrative level (typically a city or town), but should not include the city name, ZIP or postal code, or country name. For example: "32 Vassar Street               MIT Room 32-G524" |
| `gender` | A gender identity (e.g. "Female", "Fa'afafine" or "Nonbinary"). For example: "Male" |
| `givenName` | A given (or "first") name. For example: "Timothy" |
| `home` | A modifier that can be combined with other tokens (e.g. `PHONE_NUMBER`), to indicate that the field is for contacting someone at their residence. |
| `impp` | URL representing an instant messaging protocol endpoint (for example, "aim:goim?screenname=example" or "xmpp:fred@example.net") For example: "irc://example.org/timbl,isuser" |
| `jobTitle` | A job title, or the title a person has within an organization. For example: "Professor" |
| `language` | A preferred language, given as a valid [BCP 47 language tag](https://en.wikipedia.org/wiki/IETF_language_tag). For example: "en" |
| `mobile` | A modifier that can be combined with other tokens (e.g. `PHONE_NUMBER`), to indicate that the field is for contacting someone regardless of location. |
| `name` | A person's full name. For example: "Sir Timothy John Berners-Lee, OM, KBE, FRS, FREng, FRSA" |
| `namePrefix` | A prefix or title, such as "Mrs.", "Mr.", "Miss", "Ms.", "Dr.", or "Mlle.". For example: "Sir" |
| `nameSuffix` | A name suffix, such as "Jr.", "B.Sc.", "PhD.", "MBASW", or "IV". For example: "OM, KBE, FRS, FREng, FRSA" |
| `newPassword` | A new password. For example: "GUMFXbadyrS3" |
| `newUsername` | A newly created username or account name. For example: "timblee" |
| `nickname` | A nickname or handle. For example: "Tim" |
| `on` | Let the user agent provide the user with autocompletion values, but do not provide any further information about what kind of data the user might be expected to enter. The user agent would have to use heuristics to decide what autocompletion values to suggest. **This is not recommended.** It is preferable to use a specific value instead. |
| `oneTimeCode` | A one-time password (OTP). For example: "1234" |
| `organizationName` | A company or organisation name. For example: "World Wide Web Consortium" |
| `pager` | A modifier that can be combined with other tokens (e.g. `PHONE_NUMBER`), to indicate that the field describes a pager's or beeper's contact details |
| `password` | The user's current password. For example: "qwerty" |
| `phoneAreaCode` | The area code, with any country-internal prefix applied if appropriate. For example: "617" |
| `phoneCountryCode` | The country code, such as "1" for the United States, Canada, and other areas in North America and parts of the Caribbean. For example: "+1" |
| `phoneExtension` | A phone extension code within the phone number, such as a room or suite number in a hotel or an office extension in a company. For example: "1000" |
| `phoneLocal` | The phone number without the country or area code. For example: "2535702" |
| `phoneLocalPrefix` | First part of the component of the phone number that follows the area code, when that component is split into two components. For example: "253" |
| `phoneLocalSuffix` | Second part of the component of the phone number that follows the area code, when that component is split into two components. For example: "5702" |
| `phoneNational` | The entire phone number without the country code component, including a country-internal prefix. For the phone number "1-855-555-6502", this field's value would be "855-555-6502". For example: "617 253 5702" |
| `phoneNumber` | A full phone number, including the country code. For example: "+1 617 253 5702" |
| `photo` | The URL of an image representing the person, company, or contact information given in the other fields in the form. For example: "https://www.w3.org/Press/Stock/Berners-Lee/2001-europaeum-eighth.jpg" |
| `postalCode` | Postal code, post code, ZIP code, CEDEX code (if CEDEX, append "CEDEX", and the arrondissement, if relevant, to the `ADDRESS_LEVEL_2` field). For example: "02139" |
| `shipping` | A modifier that can be combined with other tokens (e.g. `FULL_STREET_ADDRESS`), to indicate that the field is part of the shipping address or contact information. |
| `streetAddressLine1` | Individual line of the street address. This should only be present if `FULL_STREET_ADDRESS` is not present. For example: "32 Vassar Street" |
| `streetAddressLine2` | Individual line of the street address. This should only be present if `FULL_STREET_ADDRESS` is not present. For example: "MIT Room 32-G524" |
| `streetAddressLine3` | Individual line of the street address. This should only be present if `FULL_STREET_ADDRESS` is not present. |
| `transactionAmount` | The amount, given in the currency specified by `TRANSACTION_CURRENCY`, of the transaction, for a payment form. For example: "401.95" |
| `transactionCurrency` | The currency in which the transaction is to take place. For example: "GBP" |
| `url` | A URL, such as a home page or company website address as appropriate given the context of the other fields in the form. For example: "https://www.w3.org/People/Berners-Lee/" |
| `username` | A username or account name. For example: "timbl" |
| `work` | A modifier that can be combined with other tokens (e.g. `PHONE_NUMBER`), to indicate that the field is for contacting someone at their workplace. |

