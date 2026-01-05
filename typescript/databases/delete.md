# delete

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.delete` instead

Description: Delete a database by its unique ID. Only API keys with with databases.write scope can delete a database.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |

## Usage

```typescript
import { Client, Databases } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result = await databases.delete({
  databaseId: '<DATABASE_ID>',
});
```
