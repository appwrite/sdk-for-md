# upsertRows

Description: Create or update Rows. Before using this route, you should create a new table resource using either a [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable) API or directly from your database console.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |
| `rows` | `object[]` | ✅ | Array of row data as JSON objects. May contain partial rows. |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.RowList = await tablesDB.upsertRows({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  rows: [],
  transactionId: '<TRANSACTION_ID>',
});
```

## Response Model

Returns a `Models.RowList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of rows that matched your query. |
| `rows` | `object[]` | List of rows. |
