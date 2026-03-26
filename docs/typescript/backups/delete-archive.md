# deleteArchive

Description: Delete an existing archive for a project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `archiveId` | `string` | ✅ | Policy ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |

## Usage

```typescript
import { Client, Backups } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const backups = new Backups(client);
const result = await backups.deleteArchive({
  archiveId: '<ARCHIVE_ID>',
});
```
