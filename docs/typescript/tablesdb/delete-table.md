# deleteTable

Description: Delete a table by its unique ID. Only users with write permissions have access to delete this resource.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |

## Usage

```typescript
import { Client, TablesDB } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result = await tablesDB.deleteTable({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
});
```
