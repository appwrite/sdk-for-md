# updatePushTarget

Description: Update the currently logged in user&#039;s push notification target. You can modify the target&#039;s identifier (device token) and provider ID (token, email, phone etc.). The target must exist and belong to the current user. If you change the provider ID, notifications will be sent through the new messaging provider instead.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `targetId` | `string` | ✅ | Target ID. |
| `identifier` | `string` | ✅ | The target identifier (token, email, phone etc.) |

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.Target = await account.updatePushTarget({
  targetId: '<TARGET_ID>',
  identifier: '<IDENTIFIER>',
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
