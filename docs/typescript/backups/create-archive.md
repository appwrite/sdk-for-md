# createArchive

Description: Create a new archive asynchronously for a project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `services` | `BackupServices` | ✅ | Array of services to backup<br>**Allowed:** `databases`, `tablesdb`, `documentsdb`, `vectorsdb`, `functions`, `storage` |
| `resourceId` | `string` | ❌ | Resource ID. When set, only this single resource will be backed up. |

## Usage

```typescript
import { Client, Backups, BackupServices, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const backups = new Backups(client);
const result: Models.BackupArchive = await backups.createArchive({
  services: BackupServices.Databases,
  resourceId: '<RESOURCE_ID>',
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
