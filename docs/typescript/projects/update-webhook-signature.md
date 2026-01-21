# updateWebhookSignature

Description: Update the webhook signature key. This endpoint can be used to regenerate the signature key used to sign and validate payload deliveries for a specific webhook.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `webhookId` | `string` | ✅ | Webhook unique ID. |

## Usage

```typescript
import { Client, Projects, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Webhook = await projects.updateWebhookSignature({
  projectId: '<PROJECT_ID>',
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
