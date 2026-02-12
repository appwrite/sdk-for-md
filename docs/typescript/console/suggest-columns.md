# suggestColumns

Description: Suggests column names and their size limits based on the provided table name. The API will also analyze other tables in the same database to provide context-aware suggestions, ensuring consistency across schema design. Users may optionally provide custom context to further refine the suggestions.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |
| `context` | `string` | ❌ | Optional user provided context to refine suggestions. |
| `min` | `number` | ❌ | Minimum number of suggestions to generate. (Default: `3`) |
| `max` | `number` | ❌ | Maximum number of suggestions to generate. (Default: `7`) |

## Usage

```typescript
import { Client, Console, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const console = new Console(client);
const result: Models.ColumnList = await console.suggestColumns({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  context: '<CONTEXT>',
  min: 1,
  max: 1,
});
```

## Response Model

Returns a `Models.ColumnList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of columns in the given table. |
| `columns` | `any[]` | List of columns. |
