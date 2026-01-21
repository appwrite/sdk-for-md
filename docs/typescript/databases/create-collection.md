# createCollection

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.createTable` instead

Description: Create a new Collection. Before using this route, you should create a new database resource using either a [server integration](https://appwrite.io/docs/server/databases#databasesCreateCollection) API or directly from your database console.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `collectionId` | `string` | ✅ | Unique Id. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `name` | `string` | ✅ | Collection name. Max length: 128 chars. |
| `permissions` | `string[]` | ❌ | An array of permissions strings. By default, no user is granted with any permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `documentSecurity` | `boolean` | ❌ | Enables configuring permissions for individual documents. A user needs one of document or collection level permissions to access a document. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `enabled` | `boolean` | ❌ | Is collection enabled? When set to &#039;disabled&#039;, users cannot access the collection but Server SDKs with and API key can still read and write to the collection. No data is lost when this is toggled. (Default: `1`) |
| `attributes` | `object[]` | ❌ | Array of attribute definitions to create. Each attribute should contain: key (string), type (string: string, integer, float, boolean, datetime), size (integer, required for string type), required (boolean, optional), default (mixed, optional), array (boolean, optional), and type-specific options. (Default: `[]`) |
| `indexes` | `object[]` | ❌ | Array of index definitions to create. Each index should contain: key (string), type (string: key, fulltext, unique, spatial), attributes (array of attribute keys), orders (array of ASC/DESC, optional), and lengths (array of integers, optional). (Default: `[]`) |

## Usage

```typescript
import { Client, Databases, Models, Permission, Role } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.Collection = await databases.createCollection({
  databaseId: '<DATABASE_ID>',
  collectionId: '<COLLECTION_ID>',
  name: '<NAME>',
  permissions: [Permission.Read(Role.Any())],
  documentSecurity: false,
  enabled: false,
  attributes: [],
  indexes: [],
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
