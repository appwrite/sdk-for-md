# updateTwilioProvider

Description: Update a Twilio provider by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `providerId` | `string` | ✅ | Provider ID. |
| `name` | `string` | ❌ | Provider name. |
| `enabled` | `boolean` | ❌ | Set as enabled. |
| `accountSid` | `string` | ❌ | Twilio account secret ID. |
| `authToken` | `string` | ❌ | Twilio authentication token. |
| `from` | `string` | ❌ | Sender number. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Provider = await messaging.updateTwilioProvider({
  providerId: '<PROVIDER_ID>',
  name: '<NAME>',
  enabled: false,
  accountSid: '<ACCOUNT_SID>',
  authToken: '<AUTH_TOKEN>',
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
