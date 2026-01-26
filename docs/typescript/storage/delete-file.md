# deleteFile

Description: Delete a file by its unique ID. Only users with write permissions have access to delete this resource.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Storage bucket unique ID. You can create a new storage bucket using the Storage service [server integration](https://appwrite.io/docs/server/storage#createBucket). |
| `fileId` | `string` | ✅ | File ID. |

## Usage

```typescript
import { Client, Storage } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result = await storage.deleteFile({
  bucketId: '<BUCKET_ID>',
  fileId: '<FILE_ID>',
});
```
