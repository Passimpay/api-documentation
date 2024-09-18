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



