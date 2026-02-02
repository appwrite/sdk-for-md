# createNHostMigration

Description: Migrate data from an NHost project to your Appwrite project. This endpoint allows you to migrate resources like authentication, databases, and other supported services from an NHost project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `resources` | `Resources` | ✅ | List of resources to migrate<br>**Allowed:** `user`, `database`, `table`, `column`, `index`, `row`, `document`, `attribute`, `collection`, `bucket`, `file` |
| `subdomain` | `string` | ✅ | Source&#039;s Subdomain |
| `region` | `string` | ✅ | Source&#039;s Region |
| `adminSecret` | `string` | ✅ | Source&#039;s Admin Secret |
| `database` | `string` | ✅ | Source&#039;s Database Name |
| `username` | `string` | ✅ | Source&#039;s Database Username |
| `password` | `string` | ✅ | Source&#039;s Database Password |
| `port` | `number` | ❌ | Source&#039;s Database Port (Default: `5432`) |

## Usage

```typescript
import { Client, Migrations, Resources, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const migrations = new Migrations(client);
const result: Models.Migration = await migrations.createNHostMigration({
  resources: Resources.User,
  subdomain: '<SUBDOMAIN>',
  region: '<REGION>',
  adminSecret: '<ADMIN_SECRET>',
  database: '<DATABASE>',
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
