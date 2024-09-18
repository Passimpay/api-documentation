# Security
How to generate signatures?

###Security
All the communication against and from our API will be signed and the signature must be included as header. This signature allows us to certificate data integrity within the communication.

##Prerequisites
```
const merchantId= 'your-mid';
const secret= 'your-secret';
const body = {
                        "operationId": "your-transaction-identifier",
                        "paymentMethod": "your-payment-method",
                        "amount": "100.00",
                        "merchantId": "your-mid",
                        "firstName": "John",
                        ......
                        ......
                        ......
                        "address": "your-user-address",
                        "ipAddress": "your-user-ip"
                    }
```
####Note: The previous body is an example, since it is dynamic and the signature can change according to the body of the request or response.

####Step 1 - Sorts the json of your request, response or callback payload alphabetically.

```
function sortObject(obj) {
      if (Array.isArray(obj)) {
        return obj.map(sortObject);
    } else if (obj !== null && typeof obj === 'object') {
        const sortedObj = {};
        const keys = Object.keys(obj).sort();
        for (const key of keys) {
            sortedObj[key] = sortObject(obj[key]);
        }
        return sortedObj;
    }
    return obj;
}
```

####Step 2 - Create signature.

```
const signatureContract =`${merchantId};${JSON.stringify(sortObject(body))};${secret}`
const signature = CryptoJS.HmacSHA256(signatureContract, secret).toString();
```

####Signature use cases:

1.When you call us, you should send the `x-signature` header, so we can validate the payload data integrity.
2.When you receive a response, you must validate the `x-signature` header presence and validate that it is valid.
3.When you receive a callback, you must validate the `x-signature` header presence and validate that it is valid.