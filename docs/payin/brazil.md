# Payin Brazil

Charge customers in Brazil using the PIX payment method

## Request sample

```json
{
    "platformId": "your Platform Id",
    "orderId": "your-transaction-identifier",
    "paymentId": "600",
    "amount": "100.00",
    "docNumber": "71713839113",
    "email": "name@domain.com",
    "phone": "customer-phone-number",
    "address": "customer-address",
    "ipAddress": "customer-ip-address"
}
```
## Create Pix Pay-in
```http
POST /payin
Content-Type: application/json
x-signature: signature
```
## Request Body
| Name | Type | Description |
|-------------|--------|-------------------------------|
| `platformId` | string | Platform Id |
| `orderId` | string | Merchant's transaction ID. Should be unique. |
| `paymentId` | integer| 600 - Brazil BRL |
| `amount` | string | The transaction amount. Format should have 2 decimals "100.00". |
| `docNumber` | string | Customer's document identifier/number |
| `email` | string | Customer's email |
| `phone` | string | Customer phone number |
| `address` | string | Customer address |
| `ipAddress` | string | Customer IP address |

## Response Body
```json
{
    "result": 1,
    "operationId": "c1b482a8-96ef-4523-89d1-03133b4b1280",
    "transactionId": "982945b2-2edb-47ad-8ff5-8c175893c80d",
    "qrCode": "00020101021126510014BR.GOV.BCB.PIX...",
    "paymentLink": "https://publicexample.com/?id=982945b2-2edb-47ad-8ff5-8c175893c80d&method=pse&token=eyJr..."
}
```

## Response Error Body
```json
{
    "result": 0,
    "message": "BAD-REQUEST",
}
```

