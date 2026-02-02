# getFile

Description: Get a file by its unique ID. This endpoint response returns a JSON object with the file metadata.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Storage bucket unique ID. You can create a new storage bucket using the Storage service [server integration](https://appwrite.io/docs/server/storage#createBucket). |
| `fileId` | `string` | ✅ | File ID. |

## Usage

```typescript
import { Client, Storage, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result: Models.File = await storage.getFile({
  bucketId: '<BUCKET_ID>',
  fileId: '<FILE_ID>',
});
```

## Response Model

Returns a `Models.File` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | File ID. |
| `bucketId` | `string` | Bucket ID. |
| `createdAt` | `string` | File creation date in ISO 8601 format. |
| `updatedAt` | `string` | File update date in ISO 8601 format. |
| `permissions` | `string[]` | File permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `name` | `string` | File name. |
| `signature` | `string` | File MD5 signature. |
| `mimeType` | `string` | File mime type. |
| `sizeOriginal` | `number` | File original size in bytes. |
| `chunksTotal` | `number` | Total number of chunks available |
| `chunksUploaded` | `number` | Total number of chunks uploaded |
| `encryption` | `boolean` | Whether file contents are encrypted at rest. |
| `compression` | `string` | Compression algorithm used for the file. Will be one of none, [gzip](https://en.wikipedia.org/wiki/Gzip), or [zstd](https://en.wikipedia.org/wiki/Zstd). |
