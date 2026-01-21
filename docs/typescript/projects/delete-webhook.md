# deleteWebhook

Description: Delete a webhook by its unique ID. Once deleted, the webhook will no longer receive project events.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `webhookId` | `string` | ✅ | Webhook unique ID. |

## Usage

```typescript
import { Client, Projects } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result = await projects.deleteWebhook({
  projectId: '<PROJECT_ID>',
  webhookId: '<WEBHOOK_ID>',
});
```
