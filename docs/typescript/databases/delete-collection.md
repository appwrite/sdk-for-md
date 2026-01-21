# deleteCollection

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.deleteTable` instead

Description: Delete a collection by its unique ID. Only users with write permissions have access to delete this resource.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |

## Usage

```typescript
import { Client, Databases } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result = await databases.deleteCollection({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
});
```
