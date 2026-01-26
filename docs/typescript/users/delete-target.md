# deleteTarget

Description: Delete a messaging target.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. |
| `targetId` | `string` | ✅ | Target ID. |

## Usage

```typescript
import { Client, Users } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result = await users.deleteTarget({
  userId: '<USER_ID>',
  targetId: '<TARGET_ID>',
});
```
