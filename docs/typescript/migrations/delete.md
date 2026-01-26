# delete

Description: Delete a migration by its unique ID. This endpoint allows you to remove a migration from your project&#039;s migration history.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `migrationId` | `string` | ✅ | Migration ID. |

## Usage

```typescript
import { Client, Migrations } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const migrations = new Migrations(client);
const result = await migrations.delete({
  migrationId: '<MIGRATION_ID>',
});
```
