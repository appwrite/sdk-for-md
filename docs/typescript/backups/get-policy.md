# getPolicy

Description: Get a backup policy using it&#039;s ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `policyId` | `string` | ✅ | Policy ID. Choose a custom ID`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |

## Usage

```typescript
import { Client, Backups, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const backups = new Backups(client);
const result: Models.BackupPolicy = await backups.getPolicy({
  policyId: '<POLICY_ID>',
});
```

## Response Model

Returns a `Models.BackupPolicy` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Backup policy ID. |
| `name` | `string` | Backup policy name. |
| `createdAt` | `string` | Policy creation date in ISO 8601 format. |
| `updatedAt` | `string` | Policy update date in ISO 8601 format. |
| `services` | `string[]` | The services that are backed up by this policy. |
| `resources` | `string[]` | The resources that are backed up by this policy. |
| `resourceId` | `string` | The resource ID to backup. Set only if this policy should backup a single resource. |
| `resourceType` | `string` | The resource type to backup. Set only if this policy should backup a single resource. |
| `retention` | `number` | How many days to keep the backup before it will be automatically deleted. |
| `schedule` | `string` | Policy backup schedule in CRON format. |
| `enabled` | `boolean` | Is this policy enabled. |
