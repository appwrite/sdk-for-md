# deleteSessions

Description: Delete all user&#039;s sessions by using the user&#039;s unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. |

## Usage

```typescript
import { Client, Users } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result = await users.deleteSessions({
  userId: '<USER_ID>',
});
```
