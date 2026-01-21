# updateVonageProvider

Description: Update a Vonage provider by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `providerId` | `string` | ✅ | Provider ID. |
| `name` | `string` | ❌ | Provider name. |
| `enabled` | `boolean` | ❌ | Set as enabled. |
| `apiKey` | `string` | ❌ | Vonage API key. |
| `apiSecret` | `string` | ❌ | Vonage API secret. |
| `from` | `string` | ❌ | Sender number. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Provider = await messaging.updateVonageProvider({
  providerId: '<PROVIDER_ID>',
  name: '<NAME>',
  enabled: false,
  apiKey: '<API_KEY>',
  apiSecret: '<API_SECRET>',
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
