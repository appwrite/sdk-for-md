# updateBucket

Description: Update a storage bucket by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Bucket unique ID. |
| `name` | `string` | ✅ | Bucket name |
| `permissions` | `string[]` | ❌ | An array of permission strings. By default, the current permissions are inherited. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `fileSecurity` | `boolean` | ❌ | Enables configuring permissions for individual file. A user needs one of file or bucket level permissions to access a file. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `enabled` | `boolean` | ❌ | Is bucket enabled? When set to &#039;disabled&#039;, users cannot access the files in this bucket but Server SDKs with and API key can still access the bucket. No files are lost when this is toggled. (Default: `1`) |
| `maximumFileSize` | `number` | ❌ | Maximum file size allowed in bytes. Maximum allowed value is 30MB. (Default: `[]`) |
| `allowedFileExtensions` | `string[]` | ❌ | Allowed file extensions. Maximum of 100 extensions are allowed, each 64 characters long. (Default: `[]`) |
| `compression` | `Compression` | ❌ | Compression algorithm choosen for compression. Can be one of none, [gzip](https://en.wikipedia.org/wiki/Gzip), or [zstd](https://en.wikipedia.org/wiki/Zstd), For file size above 20MB compression is skipped even if it&#039;s enabled (Default: `none`)<br>**Allowed:** `none`, `gzip`, `zstd` |
| `encryption` | `boolean` | ❌ | Is encryption enabled? For file size above 20MB encryption is skipped even if it&#039;s enabled (Default: `1`) |
| `antivirus` | `boolean` | ❌ | Is virus scanning enabled? For file size above 20MB AntiVirus scanning is skipped even if it&#039;s enabled (Default: `1`) |
| `transformations` | `boolean` | ❌ | Are image transformations enabled? (Default: `1`) |

## Usage

```typescript
import { Client, Storage, Compression, Models, Permission, Role } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result: Models.Bucket = await storage.updateBucket({
  bucketId: '<BUCKET_ID>',
  name: '<NAME>',
  permissions: [Permission.Read(Role.Any())],
  fileSecurity: false,
  enabled: false,
  maximumFileSize: 1,
  allowedFileExtensions: [],
  compression: Compression.None,
  encryption: false,
  antivirus: false,
  transformations: false,
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
| `compression` | `string` | Compression algorithm choosen for compression. Will be one of none, [gzip](https://en.wikipedia.org/wiki/Gzip), or [zstd](https://en.wikipedia.org/wiki/Zstd). |
| `encryption` | `boolean` | Bucket is encrypted. |
| `antivirus` | `boolean` | Virus scanning is enabled. |
| `transformations` | `boolean` | Image transformations are enabled. |
