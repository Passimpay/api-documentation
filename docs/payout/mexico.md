# Payout Mexico

Pay customers in Mexico using the PUSH payment method

With this payment method the customer will get a push notification within their mobile banking app.

## Request sample

```json
{
    "platformId": "your Platform Id",
    "paymentId": "603",
    "amount": "100.00",
    "firstName": "customer-name",
    "lastName": "customer-lastname",
    "bank": "90646",
    "accountType": "40",
    "account": "646180110400000007",
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
| `paymentId` | integer| 603 - Mexico MXM |
| `amount` | string | The transaction amount. Format should have 2 decimals "100.00". |
| `bank` | string | Customer's bank |
| `accountType` | string | Customer's account type |
| `account` | string | Customer's account |
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

