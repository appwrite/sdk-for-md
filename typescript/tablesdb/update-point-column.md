# updatePointColumn

Description: Update a point column. Changing the `default` value will not update already existing rows.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. You can create a new table using the TablesDB service [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable). |
| `key` | `string` | ✅ | Column Key. |
| `required` | `boolean` | ✅ | Is column required? |
| `default` | `any[]` | ❌ | Default value for column when not provided, array of two numbers [longitude, latitude], representing a single coordinate. Cannot be set when column is required. |
| `newKey` | `string` | ❌ | New Column Key. |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.ColumnPoint = await tablesDB.updatePointColumn({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  key: '',
  required: false,
  default: [1, 2],
  newKey: '',
});
```

## Response Model

Returns a `Models.ColumnPoint` object with the following properties:

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
| `default` | `any[]` | Default value for column when not provided. Cannot be set when column is required. |
