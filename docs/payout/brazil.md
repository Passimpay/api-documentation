# Payout Brazil

Pay customers in Brazil using the PIX payment method

## Request sample

```json
{
    "platformId": "your Platform Id",
    "paymentId": "600",
    "amount": "100.00",
    "pixKey": "customer-pix-key",
    "pixKeyType": "customer-pix-key-type",
    "docNumber": "71713839113",
    "email": "name@domain.com",
    "phone": "customer-phone-number",
    "address": "customer-address",
    "ipAddress": "customer-ip-address"
}
```
## Request a payout
```http
POST /payout

Content-Type: application/json
x-signature: signature
```
## Request Body
| Name | Type | Description |
|-------------|--------|-------------------------------|
| `platformId` | string | Platform Id |
| `paymentId` | integer| 600 - Brazil BRL |
| `amount` | string | The transaction amount. Format should have 2 decimals "100.00". |
| `docNumber` | string | Customer's document identifier/number |
| `pixKey` | string | Reference to customer's bank account. Could be customer's email, CPF, UUID or phone number. |
| `pixKeyType` | string | Type of banking account reference. Could be: "CPF", "PHONE", "EMAIL", "EVP". |
| `email` | string | Customer's email |
| `phone` | string | Customer phone number |
| `address` | string | Customer address |
| `ipAddress` | string | Customer IP address |

## Body of successful response
```json
{
    "result": 1,
    "transactionId": "2b750518-5e5e-4d44-a685-9733465a5a32"
}
```

## Body in case of error
```json
{
    "result": 0,
    "message": "BAD-REQUEST"
}
```

