# deletePushTarget

Description: Delete a push notification target for the currently logged in user. After deletion, the device will no longer receive push notifications. The target must exist and belong to the current user.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `targetId` | `string` | ✅ | Target ID. |

## Usage

```typescript
import { Client, Account } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result = await account.deletePushTarget({
  targetId: '<TARGET_ID>',
});
```
