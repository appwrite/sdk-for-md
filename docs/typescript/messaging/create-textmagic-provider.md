# createTextmagicProvider

Description: Create a new Textmagic provider.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `providerId` | `string` | ✅ | Provider ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `name` | `string` | ✅ | Provider name. |
| `from` | `string` | ❌ | Sender Phone number. Format this number with a leading &#039;+&#039; and a country code, e.g., +16175551212. |
| `username` | `string` | ❌ | Textmagic username. |
| `apiKey` | `string` | ❌ | Textmagic apiKey. |
| `enabled` | `boolean` | ❌ | Set as enabled. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Provider = await messaging.createTextmagicProvider({
  providerId: '<PROVIDER_ID>',
  name: '<NAME>',
  from: '+12065550100',
  username: '<USERNAME>',
  apiKey: '<API_KEY>',
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
