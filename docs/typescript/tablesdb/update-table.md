# updateTable

Description: Update a table by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |
| `name` | `string` | ❌ | Table name. Max length: 128 chars. |
| `permissions` | `string[]` | ❌ | An array of permission strings. By default, the current permissions are inherited. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `rowSecurity` | `boolean` | ❌ | Enables configuring permissions for individual rows. A user needs one of row or table-level permissions to access a row. [Learn more about permissions](https://appwrite.io/docs/permissions). |
| `enabled` | `boolean` | ❌ | Is table enabled? When set to &#039;disabled&#039;, users cannot access the table but Server SDKs with and API key can still read and write to the table. No data is lost when this is toggled. (Default: `1`) |

## Usage

```typescript
import { Client, TablesDB, Models, Permission, Role } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.Table = await tablesDB.updateTable({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
  name: '<NAME>',
  permissions: [Permission.Read(Role.Any())],
  rowSecurity: false,
  enabled: false,
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
