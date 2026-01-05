# createOperations

Description: Create multiple operations in a single transaction.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `transactionId` | `string` | ✅ | Transaction ID. |
| `operations` | `object[]` | ❌ | Array of staged operations. (Default: `[]`) |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.Transaction = await tablesDB.createOperations({
  transactionId: '<TRANSACTION_ID>',
  operations: [
	    {
	        "action": "create",
	        "databaseId": "<DATABASE_ID>",
	        "tableId": "<TABLE_ID>",
	        "rowId": "<ROW_ID>",
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
