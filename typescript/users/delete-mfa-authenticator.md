# deleteMFAAuthenticator

Description: Delete an authenticator app.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. |
| `type` | `AuthenticatorType` | ✅ | Type of authenticator.<br>**Allowed:** `totp` |

## Usage

```typescript
import { Client, Users, AuthenticatorType } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result = await users.deleteMFAAuthenticator({
  userId: '<USER_ID>',
  type: AuthenticatorType.Totp,
});
```
