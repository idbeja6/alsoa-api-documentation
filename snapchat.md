## Sample request (Snapchat conversion)

curl --location 'https://api.alsoa.com/api/events' \
--header 'token:<<PASTE_YOUR_TOKEN_HERE>>' \
--header 'pixel: <<PASTE_YOUR_PIXEL_ID_HERE>>' \
--header 'Content-Type: application/json'

```yaml
{
  "sclid": "E.C.P.v3fQ2RHacdksKfofPmlyuStIIHJ4Af1tKYxF9zz2c2PLx1Oaw15oHpcfl5AH",
  "first_name": "John",
  "last_name": "Doe",
  "email": "email@domain.com",
  "city": "Timbcuk",
  "state": "TU",
  "postal": 92024,
  "mobile": "+15555555555",
  "time": "2023-03-21T16:45:58.516Z",
  "url": "https://domain.com/pages/contact",
  "ip": "198.168.1.1",
  "uas": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/109.0.0.0 Safari/537.36",
  "external_id": 45676587,
  "country": "US",
  "event": "AddPaymentInfo",
  "content_type": "product",
  "contents":
    [
      { "id": "ABC123", "quantity": 2, "item_price": 5.99 },
      {
        "id": "XYZ789",
        "quantity": 2,
        "item_price": 9.99,
        "delivery_category": "in_store",
      },
    ],
  "currency": "usd",
  "value": 142.5,
}
```

## Sample response (200 OK)

```yaml
{
  "results":
    [
      {
        "tracker": "SnapChat",
        "response": { "status": "SUCCESS", "reason": "All records processed" },
      },
    ],
}
```
