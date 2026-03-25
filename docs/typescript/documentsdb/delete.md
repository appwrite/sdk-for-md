# delete

Description: Delete a database by its unique ID. Only API keys with with databases.write scope can delete a database.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |

## Usage

```typescript
import { Client, DocumentsDB } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const documentsDB = new DocumentsDB(client);
const result = await documentsDB.delete({
  databaseId: '<DATABASE_ID>',
});
```
