# getRow

Description: Get a row by its unique ID. This endpoint response returns a JSON object with the row data.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. You can create a new table using the Database service [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable). |
| `rowId` | `string` | ✅ | Row ID. |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. (Default: `[]`) |
| `transactionId` | `string` | ❌ | Transaction ID to read uncommitted changes within the transaction. |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.Row = await tablesDB.getRow({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  rowId: '<ROW_ID>',
  queries: [],
  transactionId: '<TRANSACTION_ID>',
});
```

## Response Model

Returns a `Models.Row` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Row ID. |
| `sequence` | `number` | Row automatically incrementing ID. |
| `tableId` | `string` | Table ID. |
| `databaseId` | `string` | Database ID. |
| `createdAt` | `string` | Row creation date in ISO 8601 format. |
| `updatedAt` | `string` | Row update date in ISO 8601 format. |
| `permissions` | `string[]` | Row permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
