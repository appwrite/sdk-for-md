# getTable

Description: Get a table by its unique ID. This endpoint response returns a JSON object with the table metadata.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `tableId` | `string` | ✅ | Table ID. |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.Table = await tablesDB.getTable({
  databaseId: '<DATABASE_ID>',
  tableId: '<TABLE_ID>',
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
