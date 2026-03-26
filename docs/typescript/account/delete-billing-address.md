# deleteBillingAddress

Description: Delete a specific billing address using it&#039;s ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `billingAddressId` | `string` | ✅ | Billing address unique ID |

## Usage

```typescript
import { Client, Account } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result = await account.deleteBillingAddress({
  billingAddressId: '<BILLING_ADDRESS_ID>',
});
```
