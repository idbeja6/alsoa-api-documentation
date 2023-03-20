# Alsoa API

> The Alsoa API is still a work in progress

**Base URL**: https://api.alsoa.com

You must fire against the events endpoint when attempting to fire conversions to the different ad channels

> https://api.alsoa.com/api/events


## Authentication

To start using the API you will need to correctly authenticate all requests. There are basically two inputs which are needed for authentication and authorization no matter which ad channel the conversion will be redirected to: token and pixel id.

> You can provide this as headers, query parameters or as body parameters. Providing them as headers is the recommended approach.

### cURL
curl --location 'https://api.alsoa.com/api/events' \
--header 'token:<<PASTE_YOUR_TOKEN_HERE>>' \
--header 'pixel: <<PASTE_YOUR_PIXEL_ID_HERE>>' \
--header 'Content-Type: application/json' \

All API requests must be made over HTTPS. Calls made over plain HTTP will fail.


## Errors

The Alsoa API uses standard [HTTP response codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status). All successful requests will return a 200 status code and any errors will be in the range 400 (client) to 500 (server).

All failing requests will return the status code and a descriptive error message. 


## Resources

## Conversion Events

### Post a conversion to Ad Channel Ads API

#### URL

POST https://api.alsoa.com/api/events

#### Field Definitions

| Field key            | Field                          | Notes                                            |
| ---------------------|--------------------------------|--------------------------------------------------|
| `event`              | Alsoa's event name             | We handle the event name mappings                |
| `first_name`         | First name                     |                                                  |
| `last_name`          | Last name                      |                                                  |
| `email`              | Email address                  |                                                  |
| `country`            | Country                        |                                                  |
| `city`               | City                           |                                                  |
| `state`              | State (or Province)            |                                                  |
| `postal`             | Zip (or Postal Code)           |                                                  |
| `mobile`             | Phone #                        |                                                  |
| `time`               | Date converted                 | Date > JSON.stringify "2022-05-09T22:01:23.561Z" |
| `url`                | URL converted at               |                                                  |
| `ip`                 | With IP                        |                                                  |
| `uas`                | With user agent string         |                                                  |
| `external_id`        | External ID                    |                                                  |
| `currency`           | Currency                       |                                                  |
| `value`              | Value                          |                                                  |
| `content_category`   | Content category               |                                                  |
| `content_name`       | Content name                   |                                                  |
| `fbclid`             | Facebook CLID                  | (alternative key)                                |
| `sclid`              | Snapchat CLID                  | (alternative key)                                |
| `ttclid`             | Tiktok CLID                    | (alternative key)                                |
| `gclid`              | Google Ads CLID                | (alternative key)                                |
| `clientId`           | Google Ads Client Id           | ** Needed only with gclid parameter              |
| `customerId`         | Google Ads Customer Id         | ** Needed only with gclid parameter              |
| `conversionActionId` | Google Ads Conversion Action Id| ** Needed only with gclid parameter              |

> For firing Google conversions it's needed to onboard the specific clientId to Alsoa providing also the corresponding values for clientSecret, mccCustomerId, refreshToken and devToken

## Event mappings

| Alsoa's event name       | Facebook's event name               | Snapchat's event name          | Tiktok's event name         |
| -------------------------|--------------------------------|-------------------------------------|-----------------------------|
| `AddPaymentInfo`         | AddPaymentInfo                 | ADD_BILLING                         |AddPaymentInfo               |
| `AddToCart`              | AddToCart                      | ADD_CART                            |AddToCart                    |
| `AddToWishlist`          | AddToWishlist                  | ADD_TO_WISHLIST                     |AddToWishlist                |
| `CompleteRegistration`   | CompleteRegistration           | SIGN_UP                             |CompleteRegistration         |
| `Contact`                | Contact                        | undefined                           |Contact                      |
| `CustomizeProduct`       | CustomizeProduct               | undefined                           |undefined                    |
| `Donate`                 | Donate                         | undefined                           |undefined                    |
| `FindLocation`           | FindLocation                   | undefined                           |undefined                    |
| `InitiateCheckout`       | InitiateCheckout               | START_CHECKOUT                      |InitiateCheckout             |
| `Lead`                   | Lead                           | undefined                           |SubmitForm                   |
| `Purchase`               | Purchase                       | PURCHASE                            |PlaceAnOrder                 |
| `Schedule`               | Schedule                       | undefined                           |undefined                    |
| `Search`                 | Search                         | SEARCH                              |Search                       |
| `StartTrial`             | StartTrial                     | START_TRIAL                         |undefined                    |
| `SubmitApplication`      | SubmitApplication              | undefined                           |undefined                    |
| `Subscribe`              | Subscribe                      | SUBSCRIBE                           |Subscribe                    |
| `ViewContent`            | ViewContent                    | VIEW_CONTENT                        |ViewContent                  |
| `ClickButton`            | undefined                      | undefined                           |ClickButton                  |
| `CompletePayment`        | undefined                      | undefined                           |CompletePayment              |
| `Download`               | undefined                      | undefined                           |Download                     |
| `SAVE`                   | undefined                      | SAVE                                |undefined                    |
| `PAGE_VIEW`              | undefined                      | PAGE_VIEW                           |undefined                    |
| `AD_CLICK`               | undefined                      | AD_CLICK                            |undefined                    |
| `AD_VIEW`                | undefined                      | AD_VIEW                             |undefined                    |
| `COMPLETE_TUTORIAL`      | undefined                      | COMPLETE_TUTORIAL                   |undefined                    |
| `LEVEL_COMPLETE`         | undefined                      | LEVEL_COMPLETE                      |undefined                    |
| `INVITE`                 | undefined                      | INVITE                              |undefined                    |
| `LOGIN`                  | undefined                      | LOGIN                               |undefined                    |
| `SHARE`                  | undefined                      | SHARE                               |undefined                    |
| `RESERVE`                | undefined                      | RESERVE                             |undefined                    |
| `ACHIEVEMENT_UNLOCKED`   | undefined                      | ACHIEVEMENT_UNLOCKED                |undefined                    |
| `SPENT_CREDITS`          | undefined                      | SPENT_CREDITS                       |undefined                    |
| `RATE`                   | undefined                      | RATE                                |undefined                    |
| `LIST_VIEW`              | undefined                      | LIST_VIEW                           |undefined                    |
| `APP_INSTALL`            | undefined                      | APP_INSTALL                         |undefined                    |
| `APP_OPEN`               | undefined                      | APP_OPEN                            |undefined                    |
| `CUSTOM_EVENT_1`         | undefined                      | CUSTOM_EVENT_1                      |undefined                    |
| `CUSTOM_EVENT_2`         | undefined                      | CUSTOM_EVENT_2                      |undefined                    |
| `CUSTOM_EVENT_3`         | undefined                      | CUSTOM_EVENT_3                      |undefined                    |
| `CUSTOM_EVENT_4`         | undefined                      | CUSTOM_EVENT_4                      |undefined                    |
| `CUSTOM_EVENT_5`         | undefined                      | CUSTOM_EVENT_5                      |undefined                    |
