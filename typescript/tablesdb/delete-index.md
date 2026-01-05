# deleteIndex

Description: Delete an index.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. You can create a new table using the TablesDB service [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable). |
| `key` | `string` | ✅ | Index Key. |

## Usage

```typescript
import { Client, TablesDB } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result = await tablesDB.deleteIndex({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  key: '',
});
```
