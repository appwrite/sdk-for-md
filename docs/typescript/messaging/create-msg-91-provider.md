# createMsg91Provider

Description: Create a new MSG91 provider.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `providerId` | `string` | ✅ | Provider ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `name` | `string` | ✅ | Provider name. |
| `templateId` | `string` | ❌ | Msg91 template ID |
| `senderId` | `string` | ❌ | Msg91 sender ID. |
| `authKey` | `string` | ❌ | Msg91 auth key. |
| `enabled` | `boolean` | ❌ | Set as enabled. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Provider = await messaging.createMsg91Provider({
  providerId: '<PROVIDER_ID>',
  name: '<NAME>',
  templateId: '<TEMPLATE_ID>',
  senderId: '<SENDER_ID>',
  authKey: '<AUTH_KEY>',
  enabled: false,
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
