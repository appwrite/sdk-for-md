# updateCollection

Description: Update a collection by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Collection ID. |
| `name` | `string` | ✅ | Collection name. Max length: 128 chars. |
| `permissions` | `string[]` | ❌ | An array of permission strings. By default, the current permissions are inherited. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `documentSecurity` | `boolean` | ❌ | Enables configuring permissions for individual documents. A user needs one of document or collection level permissions to access a document. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `enabled` | `boolean` | ❌ | Is collection enabled? When set to &#039;disabled&#039;, users cannot access the collection but Server SDKs with and API key can still read and write to the collection. No data is lost when this is toggled. (Default: `1`) |

## Usage

```typescript
import { Client, DocumentsDB, Models, Permission, Role } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const documentsDB = new DocumentsDB(client);
const result: Models.Collection = await documentsDB.updateCollection({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  name: '<NAME>',
  permissions: [Permission.Read(Role.Any())],
  documentSecurity: false,
  enabled: false,
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
