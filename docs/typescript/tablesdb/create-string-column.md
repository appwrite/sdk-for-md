# createStringColumn

⚠️ **DEPRECATED** since 1.9.0 - Use `tablesDB.createTextColumn` instead

Description: Create a string column.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. You can create a new table using the Database service [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable). |
| `key` | `string` | ✅ | Column Key. |
| `size` | `number` | ✅ | Column size for text columns, in number of characters. |
| `required` | `boolean` | ✅ | Is column required? |
| `default` | `string` | ❌ | Default value for column when not provided. Cannot be set when column is required. |
| `array` | `boolean` | ❌ | Is column an array? |
| `encrypt` | `boolean` | ❌ | Toggle encryption for the column. Encryption enhances security by not storing any plain text values in the database. However, encrypted columns cannot be queried. |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.ColumnString = await tablesDB.createStringColumn({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  key: '',
  size: 1,
  required: false,
  default: '<DEFAULT>',
  array: false,
  encrypt: false,
});
```

## Response Model

Returns a `Models.ColumnString` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `key` | `string` | Column Key. |
| `type` | `string` | Column type. |
| `status` | `ColumnStatus` | Column status. Possible values: `available`, `processing`, `deleting`, `stuck`, or `failed` |
| `error` | `string` | Error message. Displays error generated on failure of creating or deleting an column. |
| `required` | `boolean` | Is column required? |
| `array` | `boolean` | Is column an array? |
| `createdAt` | `string` | Column creation date in ISO 8601 format. |
| `updatedAt` | `string` | Column update date in ISO 8601 format. |
| `size` | `number` | Column size. |
| `default` | `string` | Default value for column when not provided. Cannot be set when column is required. |
| `encrypt` | `boolean` | Defines whether this column is encrypted or not. |
