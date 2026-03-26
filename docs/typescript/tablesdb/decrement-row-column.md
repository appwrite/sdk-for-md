# decrementRowColumn

Description: Decrement a specific column of a row by a given value.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |
| `rowId` | `string` | ✅ | Row ID. |
| `column` | `string` | ✅ | Column key. |
| `value` | `number` | ❌ | Value to increment the column by. The value must be a number. (Default: `1`) |
| `min` | `number` | ❌ | Minimum value for the column. If the current value is lesser than this value, an exception will be thrown. |
| `transactionId` | `string` | ❌ | Transaction ID for staging the operation. |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.Row = await tablesDB.decrementRowColumn({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  rowId: '<ROW_ID>',
  column: '',
  value: 0,
  min: 0,
  transactionId: '<TRANSACTION_ID>',
});
```

## Response Model

Returns a `Models.Row` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Row ID. |
| `sequence` | `string` | Row sequence ID. |
| `tableId` | `string` | Table ID. |
| `databaseId` | `string` | Database ID. |
| `createdAt` | `string` | Row creation date in ISO 8601 format. |
| `updatedAt` | `string` | Row update date in ISO 8601 format. |
| `permissions` | `string[]` | Row permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
