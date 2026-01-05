# getMFARecoveryCodes

Description: Get recovery codes that can be used as backup for MFA flow by User ID. Before getting codes, they must be generated using [createMfaRecoveryCodes](/docs/references/cloud/client-web/account#createMfaRecoveryCodes) method.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `userId` | `string` | ✅ | User ID. |

## Usage

```typescript
import { Client, Users, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const users = new Users(client);
const result: Models.MfaRecoveryCodes = await users.getMFARecoveryCodes({
  userId: '<USER_ID>',
});
```

## Response Model

Returns a `Models.MfaRecoveryCodes` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `recoveryCodes` | `string[]` | Recovery codes. |
