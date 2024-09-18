# API Documentation

## Base URL
`https://api.passimpay.io/`

## Authentication
All requests require an API key.

[Security](docs/security.md)

## Payin
Charge customers for goods and services

[Brazil](docs/payin/brazil.md)

[Argentina](docs/payin/argentina.md)

[Colombia](docs/payin/colombia.md)

[Mexico](docs/payin/mexico.md)

## Payout

[Brazil](docs/payut/brazil.md)

[Argentina](docs/payut/argentina.md)

[Colombia](docs/payut/colombia.md)

[Mexico](docs/payut/mexico.md)

## Check status

[Payin](docs/instatus.md)

[Payout](docs/outstatus.md)

## Webhook notification

The notification URL is specified in the platform settings in the personal account. 
The notification is sent only after a successful incoming transaction.

### Headers
| Name | Type | Description |
|-------------|--------|-------------------------------|
| `x-signature` | string | SHA-256 encrypted signature |

### Request Body
| Name | Type | Description |
|-------------|--------|-------------------------------|
| `platformId` | string | your Platform Id |
| `paymentId` | string | Currency code: 600 - Brazil BRL, 601 - Argentina ARS, 602 - Colombia COP, 603 - Mexico MXN |
| `orderId` | string | Merchant's transaction ID. Should be unique. |
| `amount` | string | The transaction amount |
| `transactionId` | string | Transaction ID |
