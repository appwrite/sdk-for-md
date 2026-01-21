# createIntegerColumn

Description: Create an integer column. Optionally, minimum and maximum values can be provided.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |
| `key` | `string` | ✅ | Column Key. |
| `required` | `boolean` | ✅ | Is column required? |
| `min` | `number` | ❌ | Minimum value |
| `max` | `number` | ❌ | Maximum value |
| `default` | `number` | ❌ | Default value. Cannot be set when column is required. |
| `array` | `boolean` | ❌ | Is column an array? |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.ColumnInteger = await tablesDB.createIntegerColumn({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  key: '',
  required: false,
  min: 0,
  max: 0,
  default: 0,
  array: false,
});
```

## Response Model

Returns a `Models.ColumnInteger` object with the following properties:

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
| `min` | `number` | Minimum value to enforce for new documents. |
| `max` | `number` | Maximum value to enforce for new documents. |
| `default` | `number` | Default value for column when not provided. Cannot be set when column is required. |
