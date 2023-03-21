<img style="height:100px;" src="https://uploads-ssl.webflow.com/623a2959e59eff1a0bd13e2e/6241ddc3b23ac92b63730870_alsoa.svg"/>

Alsoa is a server-to-server conversion tracking API for desktop, web and mobile. By acting as conduit, we transact data from event source directly to ad-channels while encapsulating functional requirements, and simplifying event S2S payloads.

Passing our API as dense as possible of an object it allows for true server-to-server conversion tracking with higher match rates across one, or multiple ad channels. Data and events are routed based on the retention and inclusion of CLID’s (click-id’s).

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
| `Contact`                | Contact                        |                                     |Contact                      |
| `CustomizeProduct`       | CustomizeProduct               |                                     |                             |
| `Donate`                 | Donate                         |                                     |                             |
| `FindLocation`           | FindLocation                   |                                     |                             |
| `InitiateCheckout`       | InitiateCheckout               | START_CHECKOUT                      |InitiateCheckout             |
| `Lead`                   | Lead                           |                                     |SubmitForm                   |
| `Purchase`               | Purchase                       | PURCHASE                            |PlaceAnOrder                 |
| `Schedule`               | Schedule                       |                                     |                             |
| `Search`                 | Search                         | SEARCH                              |Search                       |
| `StartTrial`             | StartTrial                     | START_TRIAL                         |                             |
| `SubmitApplication`      | SubmitApplication              |                                     |                             |
| `Subscribe`              | Subscribe                      | SUBSCRIBE                           |Subscribe                    |
| `ViewContent`            | ViewContent                    | VIEW_CONTENT                        |ViewContent                  |
| `ClickButton`            |                                |                                     |ClickButton                  |
| `CompletePayment`        |                                |                                     |CompletePayment              |
| `Download`               |                                |                                     |Download                     |
| `SAVE`                   |                                | SAVE                                |                             |
| `PAGE_VIEW`              |                                | PAGE_VIEW                           |                             |
| `AD_CLICK`               |                                | AD_CLICK                            |                             |
| `AD_VIEW`                |                                | AD_VIEW                             |                             |
| `COMPLETE_TUTORIAL`      |                                | COMPLETE_TUTORIAL                   |                             |
| `LEVEL_COMPLETE`         |                                | LEVEL_COMPLETE                      |                             |
| `INVITE`                 |                                | INVITE                              |                             |
| `LOGIN`                  |                                | LOGIN                               |                             |
| `SHARE`                  |                                | SHARE                               |                             |
| `RESERVE`                |                                | RESERVE                             |                             |
| `ACHIEVEMENT_UNLOCKED`   |                                | ACHIEVEMENT_UNLOCKED                |                             |
| `SPENT_CREDITS`          |                                | SPENT_CREDITS                       |                             |
| `RATE`                   |                                | RATE                                |                             |
| `LIST_VIEW`              |                                | LIST_VIEW                           |                             |
| `APP_INSTALL`            |                                | APP_INSTALL                         |                             |
| `APP_OPEN`               |                                | APP_OPEN                            |                             |
| `CUSTOM_EVENT_1`         |                                | CUSTOM_EVENT_1                      |                             |
| `CUSTOM_EVENT_2`         |                                | CUSTOM_EVENT_2                      |                             |
| `CUSTOM_EVENT_3`         |                                | CUSTOM_EVENT_3                      |                             |
| `CUSTOM_EVENT_4`         |                                | CUSTOM_EVENT_4                      |                             |
| `CUSTOM_EVENT_5`         |                                | CUSTOM_EVENT_5                      |                             |
