# deleteIndex

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.deleteIndex` instead

Description: Delete an index.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. You can create a new collection using the Database service [server integration](https://appwrite.io/docs/server/databases#databasesCreateCollection). |
| `key` | `string` | ✅ | Index Key. |

## Usage

```typescript
import { Client, Databases } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result = await databases.deleteIndex({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  key: '',
});
```
