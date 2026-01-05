# deleteMFAAuthenticator

Description: Delete an authenticator for a user by ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `type` | `AuthenticatorType` | ✅ | Type of authenticator.<br>**Allowed:** `totp` |

## Usage

```typescript
import { Client, Account, AuthenticatorType } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result = await account.deleteMFAAuthenticator({
  type: AuthenticatorType.Totp,
});
```
