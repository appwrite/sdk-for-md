# getIndex

Description: Get index by ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. You can create a new table using the Database service [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable). |
| `key` | `string` | ✅ | Index Key. |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.ColumnIndex = await tablesDB.getIndex({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  key: '',
});
```

## Response Model

Returns a `Models.ColumnIndex` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Index ID. |
| `createdAt` | `string` | Index creation date in ISO 8601 format. |
| `updatedAt` | `string` | Index update date in ISO 8601 format. |
| `key` | `string` | Index Key. |
| `type` | `string` | Index type. |
| `status` | `string` | Index status. Possible values: `available`, `processing`, `deleting`, `stuck`, or `failed` |
| `error` | `string` | Error message. Displays error generated on failure of creating or deleting an index. |
| `columns` | `string[]` | Index columns. |
| `lengths` | `number[]` | Index columns length. |
| `orders` | `string[]` | Index orders. |
