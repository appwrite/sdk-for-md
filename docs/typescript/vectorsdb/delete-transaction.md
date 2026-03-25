# deleteTransaction

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `transactionId` | `string` | ✅ | Transaction ID. |

## Usage

```typescript
import { Client, VectorsDB } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result = await vectorsDB.deleteTransaction({
  transactionId: '<TRANSACTION_ID>',
});
```
