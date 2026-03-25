# createTransaction

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `ttl` | `number` | ❌ | Seconds before the transaction expires. (Default: `300`) |

## Usage

```typescript
import { Client, DocumentsDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const documentsDB = new DocumentsDB(client);
const result: Models.Transaction = await documentsDB.createTransaction({
  ttl: 60,
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
