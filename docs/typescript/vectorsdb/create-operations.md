# createOperations

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `transactionId` | `string` | ✅ | Transaction ID. |
| `operations` | `object[]` | ❌ | Array of staged operations. (Default: `[]`) |

## Usage

```typescript
import { Client, VectorsDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result: Models.Transaction = await vectorsDB.createOperations({
  transactionId: '<TRANSACTION_ID>',
  operations: [
	    {
	        "action": "create",
	        "databaseId": "<DATABASE_ID>",
	        "collectionId": "<COLLECTION_ID>",
	        "documentId": "<DOCUMENT_ID>",
	        "data": {
	            "name": "Walter O'Brien"
	        }
	    }
	],
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
