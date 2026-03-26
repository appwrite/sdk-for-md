# create

Description: Create a new Database.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Unique Id. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `name` | `string` | ✅ | Database name. Max length: 128 chars. |
| `enabled` | `boolean` | ❌ | Is the database enabled? When set to &#039;disabled&#039;, users cannot access the database but Server SDKs with an API key can still read and write to the database. No data is lost when this is toggled. (Default: `1`) |

## Usage

```typescript
import { Client, TablesDB, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.Database = await tablesDB.create({
  databaseId: '<DATABASE_ID>',
  name: '<NAME>',
  enabled: false,
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
| `policies` | `object[]` | Database backup policies. |
| `archives` | `object[]` | Database backup archives. |
