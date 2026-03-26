# delete

Description: Delete a webhook by its unique ID. Once deleted, the webhook will no longer receive project events.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `webhookId` | `string` | ✅ | Webhook ID. |

## Usage

```typescript
import { Client, Webhooks } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const webhooks = new Webhooks(client);
const result = await webhooks.delete({
  webhookId: '<WEBHOOK_ID>',
});
```
