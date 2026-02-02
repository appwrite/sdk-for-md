# createVarcharColumn

Description: Create a varchar column.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. You can create a new table using the Database service [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable). |
| `key` | `string` | ✅ | Column Key. |
| `size` | `number` | ✅ | Column size for varchar columns, in number of characters. Maximum size is 16381. |
| `required` | `boolean` | ✅ | Is column required? |
| `default` | `string` | ❌ | Default value for column when not provided. Cannot be set when column is required. |
| `array` | `boolean` | ❌ | Is column an array? |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.ColumnVarchar = await tablesDB.createVarcharColumn({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  key: '',
  size: 1,
  required: false,
  default: '<DEFAULT>',
  array: false,
});
```

## Response Model

Returns a `Models.ColumnVarchar` object with the following properties:

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
