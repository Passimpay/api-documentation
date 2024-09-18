# Check payout status

```http
POST /withdrawstatus

Content-Type: application/json
x-signature: signature
```

## Request Body
| Name | Type | Description |
|-------------|--------|-------------------------------|
| `platformId` | string | Platform Id |
| `transactionId` | string | Transaction number received after the withdrawal request |

## Body of successful response
```json
{
    "result": 1,
    "approve": 1,
    "paymentId": 600,
    "amount": "100.00",
    "error": "error"
}
```

| Name | Description |
|------|-------------------------------|
| result | Request result |
| approve | Transaction result: 0 - pending, 1 - paid, 2 - error |
| paymentId | Currency code: 600 - Brazil BRL, 601 - Argentina ARS, 602 - Colombia COP, 603 - Mexico MXN |
| amount | Withdrawal amount |
| error | Error description if payment failed |

## Body in case of error
```json
{
    "result": 0,
    "message": "BAD-REQUEST"
}
```
