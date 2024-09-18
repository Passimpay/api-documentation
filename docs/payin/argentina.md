# Payin Argentina

Charge customers in Argentina using pagofacil payment method

## Request sample

```json
{
    "platformId": "your Platform Id",
    "orderId": "your-transaction-identifier",
    "paymentId": "601",
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
| `paymentId` | integer| 601 - Argentina ARS |
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
    "operationId": "11709823001149",
    "transactionId": "2b750518-5e5e-4d44-a685-9733465a5a32",
    "paymentLink": "https://public.com/v2/checkout?operationId=11709823001149&merchantId=1ad12cf0a-15e0-48da-b65a-06aa379f033d&signature=d4d6d..."
}
```

## Body in case of error
```json
{
    "result": 0,
    "message": "BAD-REQUEST",
}
```

