# createJWT

Description: Use this endpoint to create a JSON Web Token for user by its unique ID. You can use the resulting JWT to authenticate on behalf of the user. The JWT secret will become invalid if the session it uses gets deleted.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. |
| `sessionId` | `string` | ❌ | Session ID. Use the string &#039;recent&#039; to use the most recent session. Defaults to the most recent session. |
| `duration` | `number` | ❌ | Time in seconds before JWT expires. Default duration is 900 seconds, and maximum is 3600 seconds. (Default: `900`) |

## Usage

```typescript
import { Client, Users, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result: Models.Jwt = await users.createJWT({
  userId: '<USER_ID>',
  sessionId: '<SESSION_ID>',
  duration: 0,
});
```

## Response Model

Returns a `Models.Jwt` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `jwt` | `string` | JWT encoded string. |
