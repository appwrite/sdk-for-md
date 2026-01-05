# getFileDownload

Description: Get a file content by its unique ID. The endpoint response return with a &#039;Content-Disposition: attachment&#039; header that tells the browser to start downloading the file to user downloads directory.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Storage bucket ID. You can create a new storage bucket using the Storage service [server integration](https://appwrite.io/docs/server/storage#createBucket). |
| `fileId` | `string` | ✅ | File ID. |
| `token` | `string` | ❌ | File token for accessing this file. |

## Usage

```typescript
import { Client, Storage } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result = storage.getFileDownload({
  bucketId: '<BUCKET_ID>',
  fileId: '<FILE_ID>',
  token: '<TOKEN>',
});
```
