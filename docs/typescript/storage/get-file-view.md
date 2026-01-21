# getFileView

Description: Get a file content by its unique ID. This endpoint is similar to the download method but returns with no  &#039;Content-Disposition: attachment&#039; header.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Storage bucket unique ID. You can create a new storage bucket using the Storage service [server integration](https://appwrite.io/docs/server/storage#createBucket). |
| `fileId` | `string` | ✅ | File ID. |
| `token` | `string` | ❌ | File token for accessing this file. |

## Usage

```typescript
import { Client, Storage } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result = storage.getFileView({
  bucketId: '<BUCKET_ID>',
  fileId: '<FILE_ID>',
  token: '<TOKEN>',
});
```
