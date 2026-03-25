# delete

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |

## Usage

```typescript
import { Client, VectorsDB } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result = await vectorsDB.delete({
  databaseId: '<DATABASE_ID>',
});
```
