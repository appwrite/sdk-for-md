# createEnumColumn

Description: Create an enumeration column. The `elements` param acts as a white-list of accepted values for this column.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |
| `key` | `string` | ✅ | Column Key. |
| `elements` | `string[]` | ✅ | Array of enum values. |
| `required` | `boolean` | ✅ | Is column required? |
| `default` | `string` | ❌ | Default value for column when not provided. Cannot be set when column is required. |
| `array` | `boolean` | ❌ | Is column an array? |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.ColumnEnum = await tablesDB.createEnumColumn({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  key: '',
  elements: [],
  required: false,
  default: '<DEFAULT>',
  array: false,
});
```

## Response Model

Returns a `Models.ColumnEnum` object with the following properties:

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
| `elements` | `string[]` | Array of elements in enumerated type. |
| `format` | `string` | String format. |
| `default` | `string` | Default value for column when not provided. Cannot be set when column is required. |
