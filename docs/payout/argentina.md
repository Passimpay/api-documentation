# Payout Argentina

Pay customers in Argentina using the Rapipago payment method

It is an in-person payment services that provides solutions in Argentina through its physical network of terminals. When a customer selects this option, they will receive an email with the transaction amount and a unique payment reference number. It allows them to receive withdrawals in cash.

## Request sample

```json
{
    "platformId": "your Platform Id",
    "paymentId": "601",
    "amount": "100.00",
    "firstName": "customer-name",
    "lastName": "customer-lastname",
    "docType": "DNI",
    "docNumber": "71713839113",
    "email": "name@domain.com",
    "phone": "customer-phone-number",
    "address": "customer-address",
    "ipAddress": "customer-ip-address",
    "paymentMethod": "pagofacil"
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
| `paymentId` | integer| 601 - Argentina ARS |
| `amount` | string | The transaction amount. Format should have 2 decimals "100.00". |
| `docType` | string | Customer's document identifier type, only DNI is allowed |
| `docNumber` | string | Customer's document identifier/number |
| `firstName` | string | Customer name |
| `lastName` | string | Customer lastname |
| `email` | string | Customer's email |
| `phone` | string | Customer phone number |
| `address` | string | Customer address |
| `ipAddress` | string | Customer IP address |
| `paymentMethod` | string | pagofacil, rapipago, banktransfer. Default pagofacil |

## If paymentMethod == banktransfer
| Name | Type | Description |
|-------------|--------|-------------------------------|
| `accountType` | integer | Customer Account Type, 1 for CBU, 2 for CVU, 3 for ALIAS |
| `account` | string | Customer account |

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

