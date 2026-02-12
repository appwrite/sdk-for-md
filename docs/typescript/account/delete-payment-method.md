# deletePaymentMethod

Description: Delete a specific payment method from a user&#039;s account.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `paymentMethodId` | `string` | ✅ | Unique ID of payment method |

## Usage

```typescript
import { Client, Account } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result = await account.deletePaymentMethod({
  paymentMethodId: '<PAYMENT_METHOD_ID>',
});
```
