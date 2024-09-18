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
```
Content-Type: application/json
x-signature: signature
```
