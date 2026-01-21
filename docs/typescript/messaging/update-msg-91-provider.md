# updateMsg91Provider

Description: Update a MSG91 provider by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `providerId` | `string` | ✅ | Provider ID. |
| `name` | `string` | ❌ | Provider name. |
| `enabled` | `boolean` | ❌ | Set as enabled. |
| `templateId` | `string` | ❌ | Msg91 template ID. |
| `senderId` | `string` | ❌ | Msg91 sender ID. |
| `authKey` | `string` | ❌ | Msg91 auth key. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Provider = await messaging.updateMsg91Provider({
  providerId: '<PROVIDER_ID>',
  name: '<NAME>',
  enabled: false,
  templateId: '<TEMPLATE_ID>',
  senderId: '<SENDER_ID>',
  authKey: '<AUTH_KEY>',
});
```

## Response Model

Returns a `Models.Provider` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Provider ID. |
| `createdAt` | `string` | Provider creation time in ISO 8601 format. |
| `updatedAt` | `string` | Provider update date in ISO 8601 format. |
| `name` | `string` | The name for the provider instance. |
| `provider` | `string` | The name of the provider service. |
| `enabled` | `boolean` | Is provider enabled? |
| `type` | `string` | Type of provider. |
| `credentials` | `object` | Provider credentials. |
| `options` | `object` | Provider options. |
