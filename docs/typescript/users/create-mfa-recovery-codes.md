# createMFARecoveryCodes

Description: Generate recovery codes used as backup for MFA flow for User ID. Recovery codes can be used as a MFA verification type in [createMfaChallenge](/docs/references/cloud/client-web/account#createMfaChallenge) method by client SDK.

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
const result: Models.MfaRecoveryCodes = await users.createMFARecoveryCodes({
  userId: '<USER_ID>',
});
```

## Response Model

Returns a `Models.MfaRecoveryCodes` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `recoveryCodes` | `string[]` | Recovery codes. |
