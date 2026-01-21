# getQueueMails

Description: Get the number of mails that are waiting to be processed in the Appwrite internal queue server.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `threshold` | `number` | ❌ | Queue size threshold. When hit (equal or higher), endpoint returns server error. Default value is 5000. (Default: `5000`) |

## Usage

```typescript
import { Client, Health, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const health = new Health(client);
const result: Models.HealthQueue = await health.getQueueMails({
  threshold: 0,
});
```

## Response Model

Returns a `Models.HealthQueue` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `size` | `number` | Amount of actions in the queue. |
