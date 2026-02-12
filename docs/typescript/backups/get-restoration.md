# getRestoration

Description: Get the current status of a backup restoration.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `restorationId` | `string` | ✅ | Restoration ID. Choose a custom ID`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |

## Usage

```typescript
import { Client, Backups, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const backups = new Backups(client);
const result: Models.BackupRestoration = await backups.getRestoration({
  restorationId: '<RESTORATION_ID>',
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
