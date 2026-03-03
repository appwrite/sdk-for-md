# createRow

Description: Create a new Row. Before using this route, you should create a new table resource using either a [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable) API or directly from your database console.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. You can create a new table using the Database service [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable). Make sure to define columns before creating rows. |
| `rowId` | `string` | ✅ | Row ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `data` | `object` | ✅ | Row data as JSON object. (Default: `{}`) |
| `permissions` | `string[]` | ❌ | An array of permissions strings. By default, only the current user is granted all permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, TablesDB, Models, Permission, Role } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.Row = await tablesDB.createRow({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  rowId: '<ROW_ID>',
  data: {
    "username": "walter.obrien",
    "email": "walter.obrien@example.com",
    "fullName": "Walter O'Brien",
    "age": 30,
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
| `sequence` | `number` | Row sequence ID. |
| `tableId` | `string` | Table ID. |
| `databaseId` | `string` | Database ID. |
| `createdAt` | `string` | Row creation date in ISO 8601 format. |
| `updatedAt` | `string` | Row update date in ISO 8601 format. |
| `permissions` | `string[]` | Row permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
