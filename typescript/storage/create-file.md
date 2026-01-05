# createFile

Description: Create a new file. Before using this route, you should create a new bucket resource using either a [server integration](https://appwrite.io/docs/server/storage#storageCreateBucket) API or directly from your Appwrite console.

Larger files should be uploaded using multiple requests with the [content-range](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Range) header to send a partial request with a maximum supported chunk of `5MB`. The `content-range` header values should always be in bytes.

When the first request is sent, the server will return the **File** object, and the subsequent part request must include the file&#039;s **id** in `x-appwrite-id` header to allow the server to know that the partial upload is for the existing file and not for a new one.

If you&#039;re creating a new file using one of the Appwrite SDKs, all the chunking logic will be managed by the SDK internally.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Storage bucket unique ID. You can create a new storage bucket using the Storage service [server integration](https://appwrite.io/docs/server/storage#createBucket). |
| `fileId` | `string` | ✅ | File ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `file` | `File` | ✅ | Binary file. Appwrite SDKs provide helpers to handle file input. [Learn about file input](https://appwrite.io/docs/products/storage/upload-download#input-file). |
| `permissions` | `string[]` | ❌ | An array of permission strings. By default, only the current user is granted all permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |

## Usage

```typescript
import { Client, Storage, Models, Permission, Role } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result: Models.File = await storage.createFile({
  bucketId: '<BUCKET_ID>',
  fileId: '<FILE_ID>',
  file: file,
  permissions: [Permission.Read(Role.Any())],
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
