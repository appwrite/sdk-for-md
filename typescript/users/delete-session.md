# deleteSession

Description: Delete a user sessions by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. |
| `sessionId` | `string` | ✅ | Session ID. |

## Usage

```typescript
import { Client, Users } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result = await users.deleteSession({
  userId: '<USER_ID>',
  sessionId: '<SESSION_ID>',
});
```
