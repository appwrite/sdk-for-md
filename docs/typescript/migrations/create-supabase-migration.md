# createSupabaseMigration

Description: Migrate data from a Supabase project to your Appwrite project. This endpoint allows you to migrate resources like authentication, databases, and other supported services from a Supabase project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `resources` | `Resources` | ✅ | List of resources to migrate<br>**Allowed:** `user`, `database`, `table`, `column`, `index`, `row`, `document`, `attribute`, `collection`, `bucket`, `file` |
| `endpoint` | `string` | ✅ | Source&#039;s Supabase Endpoint |
| `apiKey` | `string` | ✅ | Source&#039;s API Key |
| `databaseHost` | `string` | ✅ | Source&#039;s Database Host |
| `username` | `string` | ✅ | Source&#039;s Database Username |
| `password` | `string` | ✅ | Source&#039;s Database Password |
| `port` | `number` | ❌ | Source&#039;s Database Port (Default: `5432`) |

## Usage

```typescript
import { Client, Migrations, Resources, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const migrations = new Migrations(client);
const result: Models.Migration = await migrations.createSupabaseMigration({
  resources: Resources.User,
  endpoint: 'https://example.com',
  apiKey: '<API_KEY>',
  databaseHost: '<DATABASE_HOST>',
  username: '<USERNAME>',
  password: '<PASSWORD>',
  port: 0,
});
```

## Response Model

Returns a `Models.Migration` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Migration ID. |
| `createdAt` | `string` | Migration creation date in ISO 8601 format. |
| `updatedAt` | `string` | Variable creation date in ISO 8601 format. |
| `status` | `string` | Migration status ( pending, processing, failed, completed )  |
| `stage` | `string` | Migration stage ( init, processing, source-check, destination-check, migrating, finished ) |
| `source` | `string` | A string containing the type of source of the migration. |
| `destination` | `string` | A string containing the type of destination of the migration. |
| `resources` | `string[]` | Resources to migrate. |
| `resourceId` | `string` | Id of the resource to migrate. |
| `statusCounters` | `object` | A group of counters that represent the total progress of the migration. |
| `resourceData` | `object` | An array of objects containing the report data of the resources that were migrated. |
| `errors` | `string[]` | All errors that occurred during the migration process. |
| `options` | `object` | Migration options used during the migration process. |
