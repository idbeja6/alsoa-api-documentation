<img style="height:75px;" src="https://uploads-ssl.webflow.com/623a2959e59eff1a0bd13e2e/6241ddc3b23ac92b63730870_alsoa.svg"/>

alsoa is a (S2S) Server-To-Server conversion tracking API for desktop, web and mobile. It transacts conversion data and acts as a conduit from event origionator to ad-channel while encapsulating functional requirements, and simplifying payloads.

Passing our API as dense of an object allows for conversion tracking with higher match rates across one, or multiple ad channels (S2S) Server-To-Server. Data and events routing's are based on the retention of ad CLID's (click-id’s).

# Ad Channel Support

- [Meta](meta.md)
- [Google Ads](google.md)
- [Snapchat Ads](snapchat.md)
- [TikTok Ads](tiktok.md)
- [Pinterest](pinterest.md)

# Development Resources

### Postman Collections

Our [Postman collection](alsoa.postman_collection.json) has conversion API examples across single, or multi-channel attribution scenarios.

### Developer Support

ryan@e1even.com

# Getting Started & Authentication

To start use our API you will need to correctly authenticate all requests. There are two inputs required for authentication and authorization regardless of which ad channel the conversion will be redirected to: token and pixel id.

**token** - you're ad channels respective authorization token \
**pixel** - The pixel ID the token is authorized to post to

> Pixel & Token can be provided as headers, query tring values or as body parameters. \
> Note: Providing them as headers is the recommended approach.

### cURL

curl --location 'https://api.alsoa.com/api/events' \
--header 'token:<<PASTE_YOUR_TOKEN_HERE>>' \
--header 'pixel: <<PASTE_YOUR_PIXEL_ID_HERE>>' \
--header 'Content-Type: application/json'

Note: All API requests must be made over HTTPS.

## Conversion Events

### Post conversion to Ad Channel Ads API

POST https://api.alsoa.com/api/events

# Field Definitions

| Field key            | Field                           | Notes                                            |
| -------------------- | ------------------------------- | ------------------------------------------------ |
| `event`              | alsoa's event name              | We handle the event name mappings                |
| `first_name`         | First name                      |                                                  |
| `last_name`          | Last name                       |                                                  |
| `email`              | Email address                   |                                                  |
| `country`            | Country                         |                                                  |
| `city`               | City                            |                                                  |
| `state`              | State (or Province)             |                                                  |
| `postal`             | Zip (or Postal Code)            |                                                  |
| `mobile`             | Phone #                         |                                                  |
| `time`               | Date converted                  | Date > JSON.stringify "2022-05-09T22:01:23.561Z" |
| `url`                | URL converted at                |                                                  |
| `ip`                 | User IP                         |                                                  |
| `uas`                | User agent string               |                                                  |
| `external_id`        | External ID                     |                                                  |
| `currency`           | Currency                        |                                                  |
| `value`              | Value                           |                                                  |
| `content_category`   | Content category                |                                                  |
| `content_name`       | Content name                    |                                                  |
| `fbclid`             | Facebook CLID                   | (alternative key)                                |
| `sclid`              | Snapchat CLID                   | (alternative key)                                |
| `ttclid`             | Tiktok CLID                     | (alternative key)                                |
| `gclid`              | Google Ads CLID                 | (alternative key)                                |
| `clientId`           | Google Ads Client Id            | \*\* Needed only with gclid parameter            |
| `customerId`         | Google Ads Customer Id          | \*\* Needed only with gclid parameter            |
| `conversionActionId` | Google Ads Conversion Action Id | \*\* Needed only with gclid parameter            |
| `epik`               | Pinterest CLID                  |                                                  |

# Event mappings

| Alsoa's event name     | Facebook's event name | Snapchat's event name | Tiktok's event name  | Pinterest's event name |
| ---------------------- | --------------------- | --------------------- | -------------------- | ---------------------- |
| `AddPaymentInfo`       | AddPaymentInfo        | ADD_BILLING           | AddPaymentInfo       |                        |
| `AddToCart`            | AddToCart             | ADD_CART              | AddToCart            | add_to_cart            |
| `AddToWishlist`        | AddToWishlist         | ADD_TO_WISHLIST       | AddToWishlist        |                        |
| `CompleteRegistration` | CompleteRegistration  | SIGN_UP               | CompleteRegistration | signup                 |
| `Contact`              | Contact               |                       | Contact              |                        |
| `CustomizeProduct`     | CustomizeProduct      |                       |                      |                        |
| `Donate`               | Donate                |                       |                      |                        |
| `FindLocation`         | FindLocation          |                       |                      |                        |
| `InitiateCheckout`     | InitiateCheckout      | START_CHECKOUT        | InitiateCheckout     | checkout               |
| `Lead`                 | Lead                  |                       | SubmitForm           | lead                   |
| `Purchase`             | Purchase              | PURCHASE              | PlaceAnOrder         |                        |
| `Schedule`             | Schedule              |                       |                      |                        |
| `Search`               | Search                | SEARCH                | Search               | search                 |
| `StartTrial`           | StartTrial            | START_TRIAL           |                      |                        |
| `SubmitApplication`    | SubmitApplication     |                       |                      |                        |
| `Subscribe`            | Subscribe             | SUBSCRIBE             | Subscribe            |                        |
| `ViewContent`          | ViewContent           | VIEW_CONTENT          | ViewContent          | page_visit             |
| `ClickButton`          |                       |                       | ClickButton          |                        |
| `CompletePayment`      |                       |                       | CompletePayment      |                        |
| `Download`             |                       |                       | Download             |                        |
| `SAVE`                 |                       | SAVE                  |                      |                        |
| `PAGE_VIEW`            |                       | PAGE_VIEW             |                      |                        |
| `AD_CLICK`             |                       | AD_CLICK              |                      |                        |
| `AD_VIEW`              |                       | AD_VIEW               |                      |                        |
| `COMPLETE_TUTORIAL`    |                       | COMPLETE_TUTORIAL     |                      |                        |
| `LEVEL_COMPLETE`       |                       | LEVEL_COMPLETE        |                      |                        |
| `INVITE`               |                       | INVITE                |                      |                        |
| `LOGIN`                |                       | LOGIN                 |                      |                        |
| `SHARE`                |                       | SHARE                 |                      |                        |
| `RESERVE`              |                       | RESERVE               |                      |                        |
| `ACHIEVEMENT_UNLOCKED` |                       | ACHIEVEMENT_UNLOCKED  |                      |                        |
| `SPENT_CREDITS`        |                       | SPENT_CREDITS         |                      |                        |
| `RATE`                 |                       | RATE                  |                      |                        |
| `LIST_VIEW`            |                       | LIST_VIEW             |                      |                        |
| `APP_INSTALL`          |                       | APP_INSTALL           |                      |                        |
| `APP_OPEN`             |                       | APP_OPEN              |                      |                        |
| `CUSTOM_EVENT_1`       |                       | CUSTOM_EVENT_1        |                      |                        |
| `CUSTOM_EVENT_2`       |                       | CUSTOM_EVENT_2        |                      |                        |
| `CUSTOM_EVENT_3`       |                       | CUSTOM_EVENT_3        |                      |                        |
| `CUSTOM_EVENT_4`       |                       | CUSTOM_EVENT_4        |                      |                        |
| `CUSTOM_EVENT_5`       |                       | CUSTOM_EVENT_5        |                      |                        |

# Error Handling

The alsoa API uses standard [HTTP response codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status). \
All successful requests will return a 200 status code and any errors will be in the range 400 (client) to 500 (server).

All failing requests will return the status code and a descriptive error message.
