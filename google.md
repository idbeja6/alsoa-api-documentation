## Sample request (Google conversion)

curl --location 'https://api.alsoa.com/api/events' \
--header 'token:<<PASTE_YOUR_TOKEN_HERE>>' \
--header 'pixel: <<PASTE_YOUR_PIXEL_ID_HERE>>' \
--header 'Content-Type: application/json'

```yaml
{
  "gclid": "Cj0KCQiAutyfBhCMARIsAMgcRJSpN054E0bR_CN0eP_YRJX0O6KHhemlkshnX-h4FpxlptaPgYDJXK8aArX8EALw_wcB",
  "clientId": "900418781726-mak6es2u2hau97gnje0q9ae62kho5v11.apps.googleusercontent.com",
  "customerId": "1478027250",
  "conversionActionId": "977280137",
  "first_name": "John",
  "last_name": "Doe",
  "email": "email@domain.com",
  "city": "Timbcuk",
  "state": "TU",
  "postal": 92024,
  "mobile": "+15555555555",
  "time": "2023-03-21T16:45:58.516Z"
}
```
> To send a Google Ads conversions a clientId from the ad account is required by alsoa, and corresponding values for clientSecret, mccCustomerId, refreshToken and devToken

## Sample response (200 OK)

```yaml
{
    "results": [
        {
            "tracker": "Google",
            "response": {
                "success": true
            }
        }
    ]
}
```


