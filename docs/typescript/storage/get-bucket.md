# getBucket

Description: Get a storage bucket by its unique ID. This endpoint response returns a JSON object with the storage bucket metadata.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Bucket unique ID. |

## Usage

```typescript
import { Client, Storage, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result: Models.Bucket = await storage.getBucket({
  bucketId: '<BUCKET_ID>',
});
```

## Response Model

Returns a `Models.Bucket` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Bucket ID. |
| `createdAt` | `string` | Bucket creation time in ISO 8601 format. |
| `updatedAt` | `string` | Bucket update date in ISO 8601 format. |
| `permissions` | `string[]` | Bucket permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `fileSecurity` | `boolean` | Whether file-level security is enabled. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `name` | `string` | Bucket name. |
| `enabled` | `boolean` | Bucket enabled. |
| `maximumFileSize` | `number` | Maximum file size supported. |
| `allowedFileExtensions` | `string[]` | Allowed file extensions. |
| `compression` | `string` | Compression algorithm chosen for compression. Will be one of none, [gzip](https://en.wikipedia.org/wiki/Gzip), or [zstd](https://en.wikipedia.org/wiki/Zstd). |
| `encryption` | `boolean` | Bucket is encrypted. |
| `antivirus` | `boolean` | Virus scanning is enabled. |
| `transformations` | `boolean` | Image transformations are enabled. |
| `totalSize` | `number` | Total size of this bucket in bytes. |
