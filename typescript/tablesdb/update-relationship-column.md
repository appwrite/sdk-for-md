# updateRelationshipColumn

Description: Update relationship column. [Learn more about relationship columns](https://appwrite.io/docs/databases-relationships#relationship-columns).

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |
| `key` | `string` | ✅ | Column Key. |
| `onDelete` | `RelationMutate` | ❌ | Constraints option<br>**Allowed:** `cascade`, `restrict`, `setNull` |
| `newKey` | `string` | ❌ | New Column Key. |

## Usage

```typescript
import { Client, TablesDB, RelationMutate, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.ColumnRelationship = await tablesDB.updateRelationshipColumn({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  key: '',
  onDelete: RelationMutate.Cascade,
  newKey: '',
});
```

## Response Model

Returns a `Models.ColumnRelationship` object with the following properties:

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
| `relatedTable` | `string` | The ID of the related table. |
| `relationType` | `string` | The type of the relationship. |
| `twoWay` | `boolean` | Is the relationship two-way? |
| `twoWayKey` | `string` | The key of the two-way relationship. |
| `onDelete` | `string` | How deleting the parent document will propagate to child documents. |
| `side` | `string` | Whether this is the parent or child side of the relationship |
