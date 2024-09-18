# Check payin status

```http
POST /v2/orderstatus

Content-Type: application/json
x-signature: signature
```

## Request Body
| Name | Type | Description |
|-------------|--------|-------------------------------|
| `platformId` | string | Platform Id |
| `orderId` | string | Merchant's transaction ID. Should be unique. |

## Body of successful response
```json
{
    "result": 1,
    "status": "paid",
    "amountPaid": "100.00",
    "currency": "BRL",
}
```

## Possible account status types
| Type | Description |
|------|-------------------------------|
| wait | Invoice pending payment |
| paid | Invoice paid |
| error | Invoice canceled or expired |

## Body in case of error
```json
{
    "result": 0,
    "message": "BAD-REQUEST"
}
```
