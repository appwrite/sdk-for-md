# getFailedJobs

Description: Returns the amount of failed jobs in a given queue.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `name` | `Name` | ✅ | The name of the queue<br>**Allowed:** `v1-database`, `v1-deletes`, `v1-audits`, `v1-mails`, `v1-functions`, `v1-stats-resources`, `v1-stats-usage`, `v1-webhooks`, `v1-certificates`, `v1-builds`, `v1-messaging`, `v1-migrations` |
| `threshold` | `number` | ❌ | Queue size threshold. When hit (equal or higher), endpoint returns server error. Default value is 5000. (Default: `5000`) |

## Usage

```typescript
import { Client, Health, Name, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const health = new Health(client);
const result: Models.HealthQueue = await health.getFailedJobs({
  name: Name.V1Database,
  threshold: 0,
});
```

## Response Model

Returns a `Models.HealthQueue` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `size` | `number` | Amount of actions in the queue. |
