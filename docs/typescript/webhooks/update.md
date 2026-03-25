# update

Description: Update a webhook by its unique ID. Use this endpoint to update the URL, events, or status of an existing webhook.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `webhookId` | `string` | ✅ | Webhook ID. |
| `name` | `string` | ✅ | Webhook name. Max length: 128 chars. |
| `url` | `string` | ✅ | Webhook URL. |
| `events` | `string[]` | ✅ | Events list. Maximum of 100 events are allowed. |
| `enabled` | `boolean` | ❌ | Enable or disable a webhook. (Default: `1`) |
| `security` | `boolean` | ❌ | Certificate verification, false for disabled or true for enabled. |
| `httpUser` | `string` | ❌ | Webhook HTTP user. Max length: 256 chars. |
| `httpPass` | `string` | ❌ | Webhook HTTP password. Max length: 256 chars. |

## Usage

```typescript
import { Client, Webhooks, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const webhooks = new Webhooks(client);
const result: Models.Webhook = await webhooks.update({
  webhookId: '<WEBHOOK_ID>',
  name: '<NAME>',
  url: '',
  events: [],
  enabled: false,
  security: false,
  httpUser: '<HTTP_USER>',
  httpPass: '<HTTP_PASS>',
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
