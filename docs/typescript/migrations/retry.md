# retry

Description: Retry a failed migration. This endpoint allows you to retry a migration that has previously failed.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `migrationId` | `string` | ✅ | Migration unique ID. |

## Usage

```typescript
import { Client, Migrations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const migrations = new Migrations(client);
const result: Models.Migration = await migrations.retry({
  migrationId: '<MIGRATION_ID>',
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
