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
[
 {
        "_id": "61a498e81af277001282724b",
        "matchId": "811deadf-6679-42ba-8d65-8c3512cb7103",
        "buyerId": "947adca7-cc55-452c-a265-35cbb03c89f6",
        "buyerLabel": "6",
        "buyerFognodeAccount": "0xba00dabc598c2edbec49168916ffc0406d04eb76",
        "sellerId": "6016ae37-ad0a-4e11-bce6-7ddf645badea",
        "sellerLabel": "3",
        "sellerFognodeAccount": "0x338495a6f5d739ef59091729c9d2cd576cb7b021",
        "amount": 87.13437341976838,
        "price": 58.778046175611365,
        "group": "demo",
        "__v": 0
    }
]
```

### Get Admin Portal Statistics

Get admin portal dashboard statistics

```
curl --location --request GET 'api.fogchain.ntu-cap.org/v1/user/statistics' \
--header 'Authorization: 07508077-f02a-4b83-a55a-8187ad45dbbf'
```

Response
```
{
    "_id": "61c406b8feb6c25bf46ac5f3",
    "email": "123@123.com",
    "avgPrice": 276.11,
    "avgMatchingRate": 63,
    "avgDemand": 378.29,
    "avgSupply": 278.99,
    "priceIncrease": 12.12,
    "matchingRateIncrease": 9.73,
    "tokenIncrease": 3.26,
    "demandIncrease": 8.39,
    "supplyIncrease": 7.65,
    "tradedDemand": 278.99,
    "matchedUtilization": 267.32,
    "potentialSupply": 192.33,
    "__v": 0
}
```

### Get Admin Portal Trading Statistics

```
curl --location --request GET 'localhost:3001/v1/user/trading-statistics' \
--header 'Authorization: 07508077-f02a-4b83-a55a-8187ad45dbbf'
```

Response

```
{
    "bids": [
        102,
        150,
        92,
        192,
        193,
        89,
        139
    ],
    "asks": [
        201,
        231,
        188,
        218,
        176,
        176,
        132
    ],
    "deals": [
        71,
        120,
        77,
        176,
        150,
        85,
        120
    ],
    "_id": "61c40e01feb6c25bf46ac5f4",
    "email": "123@123.com"
}
```

### Get Admin Portal Financial Statistics

```
curl --location --request GET 'localhost:3001/v1/user/financial-statistics' \
--header 'Authorization: 07508077-f02a-4b83-a55a-8187ad45dbbf'
```

Response

```
{
    "gain": [
        102,
        150,
        92,
        192,
        193,
        89,
        139
    ],
    "saving": [
        201,
        231,
        188,
        218,
        176,
        176,
        132
    ],
    "traded": [
        71,
        120,
        77,
        176,
        150,
        85,
        120
    ],
    "_id": "61c40e3efeb6c25bf46ac5f5",
    "email": "123@123.com"
}
```

### Digital Twin Similate Button

```
curl --location --request POST 'localhost:3001/v1/opalrt/line-loss-trading' \
--header 'Authorization: ACCESS_TOKEN' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'lossAware=0' \
--data-urlencode 'sameBids=0' \
--data-urlencode 'group=demo'
```

Response

```
{
    "lossTable": {
        "auctionTime": "1640240167041",
        "lossAware": 0,
        "totalLineLoss": 178.37942521081473,
        "totalSellerProfit": 4487.924651405666
    },
    "flowTable": [
        {
            "fromMg": "2",
            "toMg": "1",
            "amount": 72.36995744313228,
            "price": 25.05219651126583,
            "power": 2000,
            "duration": 0.03618497872156614
        },
        {
            "fromMg": "4",
            "toMg": "3",
            "amount": 57.36553217862348,
            "price": 25.05219651126583,
            "power": 2000,
            "duration": 0.02868276608931174
        },
        {
            "fromMg": "6",
            "toMg": "5",
            "amount": 49.40747093212106,
            "price": 25.05219651126583,
            "power": 2000,
            "duration": 0.024703735466060528
        }
    ]
}
```

