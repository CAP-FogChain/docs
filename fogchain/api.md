# API for Fogchain Project

## Admin Portal

### Fetch Current System Orders

Command-Line

```
curl --location --request GET 'api.fogchain.ntu-cap.org/v1/opalrt/get-orders' \
--header 'Authorization: c29f57ea-853b-4240-b006-c03c3a2c2bcc'
```

Response Example:

```
{
    "bids": [
      {
          "_id": "61c2edc072c96b01408d68a0",
          "tradingDate": "1640164800006",
          "mgLabel": "2",
          "mgPublicKey": "0x06a80f103b2f2c2355addf2ae9970f942d5c022a",
          "userPublicKey": "9840a2ba-1acf-4624-909f-972440b1da2c",
          "bidOrOffer": "Bid",
          "amount": 84.04933285938512,
          "price": -83.29160007227841,
          "group": "demo",
          "__v": 0
        },
    ],
    "offers": [
        {
            "_id": "61c2edc072c96b01408d68a3",
            "tradingDate": "1640164800006",
            "mgLabel": "1",
            "mgPublicKey": "0x65f56c0bfa6a7c1c52640fe1792f66e3493703e5",
            "userPublicKey": "2ab6c3c1-f2f0-4eca-9e6d-b988c306d46a",
            "bidOrOffer": "Offer",
            "amount": 84.04933285938512,
            "price": 27.77405137031881,
            "group": "demo",
            "__v": 0
        },
        
    ]
}
```

### Get Current Transactions

```
curl --location --request GET 'api.fogchain.ntu-cap.org/v2/order/getMatchedTransactions' \
--header 'Authorization: c29f57ea-853b-4240-b006-c03c3a2c2bcc'
```

Response

```
```