# createTarget

Description: Create a messaging target.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. |
| `targetId` | `string` | ✅ | Target ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `providerType` | `MessagingProviderType` | ✅ | The target provider type. Can be one of the following: `email`, `sms` or `push`.<br>**Allowed:** `email`, `sms`, `push` |
| `identifier` | `string` | ✅ | The target identifier (token, email, phone etc.) |
| `providerId` | `string` | ❌ | Provider ID. Message will be sent to this target from the specified provider ID. If no provider ID is set the first setup provider will be used. |
| `name` | `string` | ❌ | Target name. Max length: 128 chars. For example: My Awesome App Galaxy S23. |

## Usage

```typescript
import { Client, Users, MessagingProviderType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result: Models.Target = await users.createTarget({
  userId: '<USER_ID>',
  targetId: '<TARGET_ID>',
  providerType: MessagingProviderType.Email,
  identifier: '<IDENTIFIER>',
  providerId: '<PROVIDER_ID>',
  name: '<NAME>',
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
