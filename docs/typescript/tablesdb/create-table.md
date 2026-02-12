# createTable

Description: Create a new Table. Before using this route, you should create a new database resource using either a [server integration](https://appwrite.io/docs/references/cloud/server-dart/tablesDB#createTable) API or directly from your database console.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Unique Id. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `name` | `string` | ✅ | Table name. Max length: 128 chars. |
| `permissions` | `string[]` | ❌ | An array of permissions strings. By default, no user is granted with any permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `rowSecurity` | `boolean` | ❌ | Enables configuring permissions for individual rows. A user needs one of row or table level permissions to access a row. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `enabled` | `boolean` | ❌ | Is table enabled? When set to &#039;disabled&#039;, users cannot access the table but Server SDKs with and API key can still read and write to the table. No data is lost when this is toggled. (Default: `1`) |
| `columns` | `object[]` | ❌ | Array of column definitions to create. Each column should contain: key (string), type (string: string, integer, float, boolean, datetime, relationship), size (integer, required for string type), required (boolean, optional), default (mixed, optional), array (boolean, optional), and type-specific options. (Default: `[]`) |
| `indexes` | `object[]` | ❌ | Array of index definitions to create. Each index should contain: key (string), type (string: key, fulltext, unique, spatial), attributes (array of column keys), orders (array of ASC/DESC, optional), and lengths (array of integers, optional). (Default: `[]`) |

## Usage

```typescript
import { Client, TablesDB, Models, Permission, Role } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.Table = await tablesDB.createTable({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  name: '<NAME>',
  permissions: [Permission.Read(Role.Any())],
  rowSecurity: false,
  enabled: false,
  columns: [],
  indexes: [],
});
```

## Response Model

Returns a `Models.Table` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Table ID. |
| `createdAt` | `string` | Table creation date in ISO 8601 format. |
| `updatedAt` | `string` | Table update date in ISO 8601 format. |
| `permissions` | `string[]` | Table permissions. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `databaseId` | `string` | Database ID. |
| `name` | `string` | Table name. |
| `enabled` | `boolean` | Table enabled. Can be &#039;enabled&#039; or &#039;disabled&#039;. When disabled, the table is inaccessible to users, but remains accessible to Server SDKs using API keys. |
| `rowSecurity` | `boolean` | Whether row-level permissions are enabled. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `columns` | `any[]` | Table columns. |
| `indexes` | `object[]` | Table indexes. |
| `bytesMax` | `number` | Maximum row size in bytes. Returns 0 when no limit applies. |
| `bytesUsed` | `number` | Currently used row size in bytes based on defined columns. |
