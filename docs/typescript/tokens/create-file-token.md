# createFileToken

Description: Create a new token. A token is linked to a file. Token can be passed as a request URL search parameter.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Storage bucket unique ID. You can create a new storage bucket using the Storage service [server integration](https://appwrite.io/docs/server/storage#createBucket). |
| `fileId` | `string` | ✅ | File unique ID. |
| `expire` | `string` | ❌ | Token expiry date |

## Usage

```typescript
import { Client, Tokens, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tokens = new Tokens(client);
const result: Models.ResourceToken = await tokens.createFileToken({
  bucketId: '<BUCKET_ID>',
  fileId: '<FILE_ID>',
  expire: '',
});
```

## Response Model

Returns a `Models.ResourceToken` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Token ID. |
| `createdAt` | `string` | Token creation date in ISO 8601 format. |
| `resourceId` | `string` | Resource ID. |
| `resourceType` | `string` | Resource type. |
| `expire` | `string` | Token expiration date in ISO 8601 format. |
| `secret` | `string` | JWT encoded string. |
| `accessedAt` | `string` | Most recent access date in ISO 8601 format. This attribute is only updated again after 24 hours. |
