# getCollection

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.getTable` instead

Description: Get a collection by its unique ID. This endpoint response returns a JSON object with the collection metadata.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.Collection = await databases.getCollection({
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
