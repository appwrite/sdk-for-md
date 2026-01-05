# get

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.get` instead

Description: Get a database by its unique ID. This endpoint response returns a JSON object with the database metadata.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |

## Usage

```typescript
import { Client, Databases, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.Database = await databases.get({
  databaseId: '<DATABASE_ID>',
});
```

## Response Model

Returns a `Models.Database` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Database ID. |
| `name` | `string` | Database name. |
| `createdAt` | `string` | Database creation date in ISO 8601 format. |
| `updatedAt` | `string` | Database update date in ISO 8601 format. |
| `enabled` | `boolean` | If database is enabled. Can be &#039;enabled&#039; or &#039;disabled&#039;. When disabled, the database is inaccessible to users, but remains accessible to Server SDKs using API keys. |
| `type` | `DatabaseType` | Database type. |
