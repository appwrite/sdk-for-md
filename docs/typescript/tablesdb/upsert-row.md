# upsertRow

Description: Create or update a Row. Before using this route, you should create a new table resource using either a [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable) API or directly from your database console.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |
| `rowId` | `string` | ✅ | Row ID. |
| `data` | `object` | ❌ | Row data as JSON object. Include all required columns of the row to be created or updated. (Default: `{}`) |
| `permissions` | `string[]` | ❌ | An array of permissions strings. By default, the current permissions are inherited. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, TablesDB, Models, Permission, Role } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.Row = await tablesDB.upsertRow({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  rowId: '<ROW_ID>',
  data: {
    "username": "walter.obrien",
    "email": "walter.obrien@example.com",
    "fullName": "Walter O'Brien",
    "age": 33,
    "isAdmin": false
},
  permissions: [Permission.Read(Role.Any())],
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
