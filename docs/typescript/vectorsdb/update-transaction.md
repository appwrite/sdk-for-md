# updateTransaction

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `transactionId` | `string` | ✅ | Transaction ID. |
| `commit` | `boolean` | ❌ | Commit transaction? |
| `rollback` | `boolean` | ❌ | Rollback transaction? |

## Usage

```typescript
import { Client, VectorsDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result: Models.Transaction = await vectorsDB.updateTransaction({
  transactionId: '<TRANSACTION_ID>',
  commit: false,
  rollback: false,
});
```

## Response Model

Returns a `Models.Transaction` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Transaction ID. |
| `createdAt` | `string` | Transaction creation time in ISO 8601 format. |
| `updatedAt` | `string` | Transaction update date in ISO 8601 format. |
| `status` | `string` | Current status of the transaction. One of: pending, committing, committed, rolled_back, failed. |
| `operations` | `number` | Number of operations in the transaction. |
| `expiresAt` | `string` | Expiration time in ISO 8601 format. |
