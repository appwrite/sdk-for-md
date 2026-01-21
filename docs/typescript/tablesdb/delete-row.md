# deleteRow

Description: Delete a row by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. You can create a new table using the Database service [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable). |
| `rowId` | `string` | ✅ | Row ID. |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, TablesDB } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result = await tablesDB.deleteRow({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  rowId: '<ROW_ID>',
  transactionId: '<TRANSACTION_ID>',
});
```
