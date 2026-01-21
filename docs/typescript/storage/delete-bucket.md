# deleteBucket

Description: Delete a storage bucket by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Bucket unique ID. |

## Usage

```typescript
import { Client, Storage } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result = await storage.deleteBucket({
  bucketId: '<BUCKET_ID>',
});
```
