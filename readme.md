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

#### Generic body parameters
+ event (Required)
> We implemented a general event name mapping logic so that users will only care about Alsoa's event naming and we handle the mappings for them automatically.

+ time
> This parameter allows to specify the date at which the specific conversion occured. If this parameter is not present, the current time will be added to the payload.

+ first_name

+ last_name

+ email

+ city

+ state

+ postal

+ mobile

+ url

+ ip

+ uas

+ external_id

+ date_of_birth

+ gender

+ country

+ content_category

+ content_name

+ currency

+ value

#### Facebook specific body parameters
+ fbclid (Required)
> This is the only parameter which is specific for reporting Facebook conversions.

#### Snapchat specific body parameters
+ sclid (Required)
> This is the only parameter which is specific for reporting Snapchat conversions.

#### Tiktok specific body parameters
+ ttclid (Required)
> This is the only parameter which is specific for reporting Tiktok conversions.

#### Google specific body parameters
+ gclid (Required)
> This is the only parameter which is specific for reporting Google conversions.

For firing Google conversions it's needed to onboard the specific clientId to Alsoa providing also the corresponding values for clientSecret, mccCustomerId, refreshToken and devToken

+ clientId (Required)

+ customerId (Required)

+ conversionActionId (Required)

## Event mappings
> The first value corresponds to Alsoa's supported events. 

> The second value corresponds to Facebook's converted event names.

> The third value corresponds to Snapchat's converted event names.

> The fourth value corresponds to Tiktok's converted event names.

+ AddPaymentInfo : ['AddPaymentInfo','AddPaymentInfo', 'ADD_BILLING', 'AddPaymentInfo']

+ AddToCart : ['AddToCart', 'AddToCart', 'ADD_CART', 'AddToCart']

+ AddToWishlist : ['AddToWishlist', 'AddToWishlist','ADD_TO_WISHLIST', 'AddToWishlist']

+ CompleteRegistration : ['CompleteRegistration', 'CompleteRegistration', 'SIGN_UP', 'CompleteRegistration']

+ Contact : ['Contact', 'Contact', undefined, 'Contact']

+ CustomizeProduct : ['CustomizeProduct', 'CustomizeProduct', undefined, undefined]

+ Donate : ['Donate', 'Donate', undefined, undefined]

+ FindLocation : ['FindLocation', 'FindLocation', undefined, undefined]

+ InitiateCheckout : ['InitiateCheckout', 'InitiateCheckout', 'START_CHECKOUT', 'InitiateCheckout']

+ Lead : ['Lead', 'Lead', undefined, 'SubmitForm']

+ Purchase : ['Purchase', 'Purchase', 'PURCHASE', 'PlaceAnOrder']

+ Schedule : ['Schedule', 'Schedule', undefined, undefined]

+ Search : ['Search', 'Search', 'SEARCH', 'Search']

+ StartTrial : ['StartTrial', 'StartTrial', 'START_TRIAL', undefined]

+ SubmitApplication: ['SubmitApplication', 'SubmitApplication', undefined, undefined]

+ Subscribe : ['Subscribe', 'Subscribe', 'SUBSCRIBE', 'Subscribe']

+ ViewContent : ['ViewContent', 'ViewContent','VIEW_CONTENT', 'ViewContent'],

// Only in Tiktok
+ ClickButton: ['ClickButton', undefined, undefined, 'ClickButton']

+ CompletePayment: ['CompletePayment', undefined, undefined, 'CompletePayment']

+ Download : ['Download', undefined, undefined, 'Download']

// Only in Snapchat
+ SAVE : ['SAVE', undefined, 'SAVE', undefined]

+ PAGE_VIEW : ['PAGE_VIEW', undefined,'PAGE_VIEW', undefined]

+ AD_CLICK : ['AD_CLICK', undefined,'AD_CLICK', undefined]

+ AD_VIEW : ['AD_VIEW', undefined,'AD_VIEW', undefined]

+ COMPLETE_TUTORIAL : ['COMPLETE_TUTORIAL', undefined,'COMPLETE_TUTORIAL', undefined]

+ LEVEL_COMPLETE : ['LEVEL_COMPLETE', undefined,'LEVEL_COMPLETE', undefined]

+ INVITE : ['INVITE', undefined,'INVITE', undefined]

+ LOGIN : ['LOGIN', undefined,'LOGIN', undefined]

+ SHARE : ['SHARE', undefined,'SHARE', undefined]

+ RESERVE : ['RESERVE', undefined,'RESERVE', undefined]

+ ACHIEVEMENT_UNLOCKED : ['ACHIEVEMENT_UNLOCKED', undefined,'ACHIEVEMENT_UNLOCKED', undefined]

+ SPENT_CREDITS : ['SPENT_CREDITS', undefined,'SPENT_CREDITS', undefined]

+ RATE : ['RATE', undefined,'RATE', undefined]

+ LIST_VIEW : ['LIST_VIEW', undefined,'LIST_VIEW', undefined]

+ APP_INSTALL : ['APP_INSTALL', undefined,'APP_INSTALL', undefined]

+ APP_OPEN : ['APP_OPEN', undefined,'APP_OPEN', undefined]

+ CUSTOM_EVENT_1 : ['CUSTOM_EVENT_1', undefined,'CUSTOM_EVENT_1', undefined]

+ CUSTOM_EVENT_2 : ['CUSTOM_EVENT_2', undefined,'CUSTOM_EVENT_2', undefined]

+ CUSTOM_EVENT_3 : ['CUSTOM_EVENT_3', undefined,'CUSTOM_EVENT_3', undefined]

+ CUSTOM_EVENT_4 : ['CUSTOM_EVENT_4', undefined,'CUSTOM_EVENT_4', undefined]

+ CUSTOM_EVENT_5 : ['CUSTOM_EVENT_5', undefined,'CUSTOM_EVENT_5', undefined]
