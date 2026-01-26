# createMFAChallenge

Description: Begin the process of MFA verification after sign-in. Finish the flow with [updateMfaChallenge](/docs/references/cloud/client-web/account#updateMfaChallenge) method.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `factor` | `AuthenticationFactor` | ✅ | Factor used for verification. Must be one of following: `email`, `phone`, `totp`, `recoveryCode`.<br>**Allowed:** `email`, `phone`, `totp`, `recoverycode` |

## Usage

```typescript
import { Client, Account, AuthenticationFactor, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.MfaChallenge = await account.createMFAChallenge({
  factor: AuthenticationFactor.Email,
});
```

## Response Model

Returns a `Models.MfaChallenge` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Token ID. |
| `createdAt` | `string` | Token creation date in ISO 8601 format. |
| `userId` | `string` | User ID. |
| `expire` | `string` | Token expiration date in ISO 8601 format. |
