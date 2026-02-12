# createRestoration

Description: Create and trigger a new restoration for a backup on a project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `archiveId` | `string` | ✅ | Backup archive ID to restore |
| `services` | `BackupServices` | ✅ | Array of services to restore<br>**Allowed:** `databases`, `functions`, `storage` |
| `newResourceId` | `string` | ❌ | Unique Id. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `newResourceName` | `string` | ❌ | Database name. Max length: 128 chars. |

## Usage

```typescript
import { Client, Backups, BackupServices, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const backups = new Backups(client);
const result: Models.BackupRestoration = await backups.createRestoration({
  archiveId: '<ARCHIVE_ID>',
  services: BackupServices.Databases,
  newResourceId: '<NEW_RESOURCE_ID>',
  newResourceName: '<NEW_RESOURCE_NAME>',
});
```

## Response Model

Returns a `Models.BackupRestoration` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Restoration ID. |
| `createdAt` | `string` | Restoration creation time in ISO 8601 format. |
| `updatedAt` | `string` | Restoration update date in ISO 8601 format. |
| `archiveId` | `string` | Backup archive ID. |
| `policyId` | `string` | Backup policy ID. |
| `status` | `string` | The status of the restoration. Possible values: pending, downloading, processing, completed, failed. |
| `startedAt` | `string` | The backup start time. |
| `migrationId` | `string` | Migration ID. |
| `services` | `string[]` | The services that are backed up by this policy. |
| `resources` | `string[]` | The resources that are backed up by this policy. |
| `options` | `string` | Optional data in key-value object.  |
