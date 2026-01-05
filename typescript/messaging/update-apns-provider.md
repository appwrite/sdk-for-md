# updateAPNSProvider

Description: Update a Apple Push Notification service provider by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `providerId` | `string` | ✅ | Provider ID. |
| `name` | `string` | ❌ | Provider name. |
| `enabled` | `boolean` | ❌ | Set as enabled. |
| `authKey` | `string` | ❌ | APNS authentication key. |
| `authKeyId` | `string` | ❌ | APNS authentication key ID. |
| `teamId` | `string` | ❌ | APNS team ID. |
| `bundleId` | `string` | ❌ | APNS bundle ID. |
| `sandbox` | `boolean` | ❌ | Use APNS sandbox environment. |

## Usage

```typescript
import { Client, Messaging, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const messaging = new Messaging(client);
const result: Models.Provider = await messaging.updateAPNSProvider({
  providerId: '<PROVIDER_ID>',
  name: '<NAME>',
  enabled: false,
  authKey: '<AUTH_KEY>',
  authKeyId: '<AUTH_KEY_ID>',
  teamId: '<TEAM_ID>',
  bundleId: '<BUNDLE_ID>',
  sandbox: false,
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
