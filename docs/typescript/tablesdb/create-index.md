# createIndex

Description: Creates an index on the columns listed. Your index should include all the columns you will query in a single request.
Type can be `key`, `fulltext`, or `unique`.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. You can create a new table using the Database service [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable). |
| `key` | `string` | ✅ | Index Key. |
| `type` | `TablesDBIndexType` | ✅ | Index type.<br>**Allowed:** `key`, `fulltext`, `unique`, `spatial` |
| `columns` | `string[]` | ✅ | Array of columns to index. Maximum of 100 columns are allowed, each 32 characters long. |
| `orders` | `OrderBy` | ❌ | Array of index orders. Maximum of 100 orders are allowed. (Default: `[]`)<br>**Allowed:** `asc`, `desc` |
| `lengths` | `number[]` | ❌ | Length of index. Maximum of 100 (Default: `[]`) |

## Usage

```typescript
import { Client, TablesDB, TablesDBIndexType, OrderBy, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.ColumnIndex = await tablesDB.createIndex({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  key: '',
  type: TablesDBIndexType.Key,
  columns: [],
  orders: OrderBy.Asc,
  lengths: [],
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
