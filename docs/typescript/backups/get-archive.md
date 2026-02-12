# getArchive

Description: Get a backup archive using it&#039;s ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `archiveId` | `string` | ✅ | Archive ID. Choose a custom ID`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |

## Usage

```typescript
import { Client, Backups, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const backups = new Backups(client);
const result: Models.BackupArchive = await backups.getArchive({
  archiveId: '<ARCHIVE_ID>',
});
```

## Response Model

Returns a `Models.BackupArchive` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Archive ID. |
| `createdAt` | `string` | Archive creation time in ISO 8601 format. |
| `updatedAt` | `string` | Archive update date in ISO 8601 format. |
| `policyId` | `string` | Archive policy ID. |
| `size` | `number` | Archive size in bytes. |
| `status` | `string` | The status of the archive creation. Possible values: pending, processing, uploading, completed, failed. |
| `startedAt` | `string` | The backup start time. |
| `migrationId` | `string` | Migration ID. |
| `services` | `string[]` | The services that are backed up by this archive. |
| `resources` | `string[]` | The resources that are backed up by this archive. |
| `resourceId` | `string` | The resource ID to backup. Set only if this archive should backup a single resource. |
| `resourceType` | `string` | The resource type to backup. Set only if this archive should backup a single resource. |
