# getSupabaseReport

Description: Generate a report of the data in a Supabase project before migrating. This endpoint analyzes the source project and returns information about the resources that can be migrated.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `resources` | `SupabaseMigrationResource` | ✅ | List of resources to migrate<br>**Allowed:** `user`, `database`, `table`, `column`, `index`, `row`, `document`, `attribute`, `collection`, `bucket`, `file` |
| `endpoint` | `string` | ✅ | Source&#039;s Supabase Endpoint. |
| `apiKey` | `string` | ✅ | Source&#039;s API Key. |
| `databaseHost` | `string` | ✅ | Source&#039;s Database Host. |
| `username` | `string` | ✅ | Source&#039;s Database Username. |
| `password` | `string` | ✅ | Source&#039;s Database Password. |
| `port` | `number` | ❌ | Source&#039;s Database Port. (Default: `5432`) |

## Usage

```typescript
import { Client, Migrations, SupabaseMigrationResource, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const migrations = new Migrations(client);
const result: Models.MigrationReport = await migrations.getSupabaseReport({
  resources: SupabaseMigrationResource.User,
  endpoint: 'https://example.com',
  apiKey: '<API_KEY>',
  databaseHost: '<DATABASE_HOST>',
  username: '<USERNAME>',
  password: '<PASSWORD>',
  port: 0,
});
```

## Response Model

Returns a `Models.MigrationReport` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `user` | `number` | Number of users to be migrated. |
| `team` | `number` | Number of teams to be migrated. |
| `database` | `number` | Number of databases to be migrated. |
| `row` | `number` | Number of rows to be migrated. |
| `file` | `number` | Number of files to be migrated. |
| `bucket` | `number` | Number of buckets to be migrated. |
| `function` | `number` | Number of functions to be migrated. |
| `site` | `number` | Number of sites to be migrated. |
| `size` | `number` | Size of files to be migrated in mb. |
| `version` | `string` | Version of the Appwrite instance to be migrated. |
