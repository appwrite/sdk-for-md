# deleteTransaction

Description: Delete a transaction by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `transactionId` | `string` | ✅ | Transaction ID. |

## Usage

```typescript
import { Client, Databases } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result = await databases.deleteTransaction({
  transactionId: '<TRANSACTION_ID>',
});
```
