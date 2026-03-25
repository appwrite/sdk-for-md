# getCollection

Description: Get a collection by its unique ID. This endpoint response returns a JSON object with the collection metadata.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |

## Usage

```typescript
import { Client, DocumentsDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const documentsDB = new DocumentsDB(client);
const result: Models.Collection = await documentsDB.getCollection({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
});
```

## Response Model

Returns a `Models.Collection` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Collection ID. |
| `createdAt` | `string` | Collection creation date in ISO 8601 format. |
| `updatedAt` | `string` | Collection update date in ISO 8601 format. |
| `permissions` | `string[]` | Collection permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `databaseId` | `string` | Database ID. |
| `name` | `string` | Collection name. |
| `enabled` | `boolean` | Collection enabled. Can be &#039;enabled&#039; or &#039;disabled&#039;. When disabled, the collection is inaccessible to users, but remains accessible to Server SDKs using API keys. |
| `documentSecurity` | `boolean` | Whether document-level permissions are enabled. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `attributes` | `any[]` | Collection attributes. |
| `indexes` | `object[]` | Collection indexes. |
| `bytesMax` | `number` | Maximum document size in bytes. Returns 0 when no limit applies. |
| `bytesUsed` | `number` | Currently used document size in bytes based on defined attributes. |
