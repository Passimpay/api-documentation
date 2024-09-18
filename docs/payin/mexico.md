# Payin Argentina

Charge customers in Mexico using direct bank transfers payment method.

With this payment method the customer will transfer the money directly from their bank account. They should send as concept an TOTP that will be provided by us as payment response.

## Request sample

```json
{
    "platformId": "your Platform Id",
    "orderId": "your-transaction-identifier",
    "paymentId": "603",
    "amount": "100.00",
    "firstName": "Jhon",
    "lastName": "Doe",
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
| `paymentId` | integer| 603 - Mexico MXN |
| `amount` | string | The transaction amount. Format should have 2 decimals "100.00". |
| `docNumber` | string | Customer's document identifier/number |
| `firstName` | string | Customer name |
| `lastName` | string | Customer lastname |
| `email` | string | Customer's email |
| `phone` | string | Customer phone number |
| `address` | string | Customer address |
| `ipAddress` | string | Customer IP address |

## Body of successful response
```json
{
    "result": 1,
    "operationId": "c1b482a8-96ef-4523-89d1-03133b4b1280",
    "transactionId": "982945b2-2edb-47ad-8ff5-8c175893c80d",
    "otp": "890765",
    "paymentLink": "https://checkout.rixsus.com/mx/details......."
}
```

## Body in case of error
```json
{
    "result": 0,
    "message": "BAD-REQUEST",
}
```

