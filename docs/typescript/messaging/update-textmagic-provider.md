# updateTextmagicProvider

Description: Update a Textmagic provider by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `providerId` | `string` | ✅ | Provider ID. |
| `name` | `string` | ❌ | Provider name. |
| `enabled` | `boolean` | ❌ | Set as enabled. |
| `username` | `string` | ❌ | Textmagic username. |
| `apiKey` | `string` | ❌ | Textmagic apiKey. |
| `from` | `string` | ❌ | Sender number. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Provider = await messaging.updateTextmagicProvider({
  providerId: '<PROVIDER_ID>',
  name: '<NAME>',
  enabled: false,
  username: '<USERNAME>',
  apiKey: '<API_KEY>',
  from: '<FROM>',
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
