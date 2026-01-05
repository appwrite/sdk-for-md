# createPushTarget

Description: Use this endpoint to register a device for push notifications. Provide a target ID (custom or generated using ID.unique()), a device identifier (usually a device token), and optionally specify which provider should send notifications to this target. The target is automatically linked to the current session and includes device information like brand and model.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `targetId` | `string` | ✅ | Target ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `identifier` | `string` | ✅ | The target identifier (token, email, phone etc.) |
| `providerId` | `string` | ❌ | Provider ID. Message will be sent to this target from the specified provider ID. If no provider ID is set the first setup provider will be used. |

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.Target = await account.createPushTarget({
  targetId: '<TARGET_ID>',
  identifier: '<IDENTIFIER>',
  providerId: '<PROVIDER_ID>',
});
```

## Response Model

Returns a `Models.Target` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Target ID. |
| `createdAt` | `string` | Target creation time in ISO 8601 format. |
| `updatedAt` | `string` | Target update date in ISO 8601 format. |
| `name` | `string` | Target Name. |
| `userId` | `string` | User ID. |
| `providerId` | `string` | Provider ID. |
| `providerType` | `string` | The target provider type. Can be one of the following: `email`, `sms` or `push`. |
| `identifier` | `string` | The target identifier. |
| `expired` | `boolean` | Is the target expired. |
