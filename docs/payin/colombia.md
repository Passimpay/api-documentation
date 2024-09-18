# Payin Colombia

Charge customers in Colombia using pse payment method

## Request sample

```json
{
    "platformId": "your Platform Id",
    "orderId": "your-transaction-identifier",
    "paymentId": "602",
    "amount": "100.00",
    "firstName": "Jhon",
    "lastName": "Doe",
    "docNumber": "71713839113",
    "address": "customer-address",
}
```
## Create Pay-in
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
| `paymentId` | integer| 602 - Colombia COP |
| `amount` | string | The transaction amount. Format should have 2 decimals "100.00". |
| `docNumber` | string | Customer's document identifier/number |
| `firstName` | string | Customer name |
| `lastName` | string | Customer lastname |
| `address` | string | Customer address |

## Body of successful response
```json
{
    "result": 1,
    "id": "80dcd085-c0af-4071-a38c-0e0e33acba98",
    "operationId": "1713835230672",
    "transactionId": "41d6c0a2-76d2-4be0-85a4-e55a4948e6ac",
    "paymentLink": "https://publicexample.com/?id=41d6c0a2-76d2-4be0-85a4-e55a4948e6ac&method=pse&token=eyJ..."
}
```

## Body in case of error
```json
{
    "result": 0,
    "message": "BAD-REQUEST",
}
```

