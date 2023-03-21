## Sample request (Facebook conversion)
curl --location 'https://api.alsoa.com/api/events' \
--header 'token:<<PASTE_YOUR_TOKEN_HERE>>' \
--header 'pixel: <<PASTE_YOUR_PIXEL_ID_HERE>>' \
--header 'Content-Type: application/json'
```yaml
{
  "fbclid": "IwAR1TeejVM0hGBUN0vi0VLo634dvllqrRzyapDrUG5xFTGIiH9rcNzgsrOZE",
  "first_name": "John",
  "last_name": "Doe",
  "email": "email@domain.com",
  "city": "Timbcuk",
  "state": "TU",
  "postal": 92024,
  "mobile": "+15555555555",
  "time": "2023-03-17T16:45:58.516Z",
  "url": "https://domain.com/pages/contact",
  "ip": "198.168.1.1",
  "uas": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/109.0.0.0 Safari/537.36",
  "external_id": 45676587,
  "country": "US",
  "event": "Lead",
  "content_category": "grocery",
  "content_name": "lettuce",
  "currency": "usd",
  "value": 142.5
}
```

## Sample response (200 OK)
```yaml
{
  "results": [
    {
      "tracker": "Facebook",
      "response": {
        "_events_received": 1,
        "_messages": [],
        "_fbtrace_id": "A8nqeT1fyz6pgKHH3oBzZwD"
      }
    }
  ]
}
```
