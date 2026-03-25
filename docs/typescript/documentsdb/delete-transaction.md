# deleteTransaction

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `transactionId` | `string` | ✅ | Transaction ID. |

## Usage

```typescript
import { Client, DocumentsDB } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const documentsDB = new DocumentsDB(client);
const result = await documentsDB.deleteTransaction({
  transactionId: '<TRANSACTION_ID>',
});
```
