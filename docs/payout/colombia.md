# Payout Colombia

Pay customers in Colombia using the Efecty payment method

It is an in-person payment services that provides solutions in Colombia through its physical network of terminals. When a customer selects this option, they will receive an email with the transaction amount and a unique payment reference number. It allows them to receive withdrawals in cash.

## Request sample

```json
{
    "platformId": "your Platform Id",
    "orderId": "your-transaction-identifier",
    "paymentId": "602",
    "amount": "100.00",
    "firstName": "customer-name",
    "lastName": "customer-lastname",
    "docType": "CC",
    "docNumber": "71713839113",
    "email": "name@domain.com",
    "phone": "customer-phone-number",
    "address": "customer-address",
    "ipAddress": "customer-ip-address"
}
```
## Create Pix Pay-in
```http
POST /payout

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
| `docType` | string | Customer's document identifier type, CC for cedula |
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

