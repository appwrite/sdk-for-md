# get

Description: Get a webhook by its unique ID. This endpoint returns details about a specific webhook configured for a project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `webhookId` | `string` | ✅ | Webhook ID. |

## Usage

```typescript
import { Client, Webhooks, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const webhooks = new Webhooks(client);
const result: Models.Webhook = await webhooks.get({
  webhookId: '<WEBHOOK_ID>',
});
```

## Response Model

Returns a `Models.Webhook` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Webhook ID. |
| `createdAt` | `string` | Webhook creation date in ISO 8601 format. |
| `updatedAt` | `string` | Webhook update date in ISO 8601 format. |
| `name` | `string` | Webhook name. |
| `url` | `string` | Webhook URL endpoint. |
| `events` | `string[]` | Webhook trigger events. |
| `security` | `boolean` | Indicated if SSL / TLS Certificate verification is enabled. |
| `httpUser` | `string` | HTTP basic authentication username. |
| `httpPass` | `string` | HTTP basic authentication password. |
| `signatureKey` | `string` | Signature key which can be used to validated incoming |
| `enabled` | `boolean` | Indicates if this webhook is enabled. |
| `logs` | `string` | Webhook error logs from the most recent failure. |
| `attempts` | `number` | Number of consecutive failed webhook attempts. |
