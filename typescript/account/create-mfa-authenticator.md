# createMFAAuthenticator

Description: Add an authenticator app to be used as an MFA factor. Verify the authenticator using the [verify authenticator](/docs/references/cloud/client-web/account#updateMfaAuthenticator) method.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `type` | `AuthenticatorType` | ✅ | Type of authenticator. Must be `totp`<br>**Allowed:** `totp` |

## Usage

```typescript
import { Client, Account, AuthenticatorType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.MfaType = await account.createMFAAuthenticator({
  type: AuthenticatorType.Totp,
});
```

## Response Model

Returns a `Models.MfaType` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `secret` | `string` | Secret token used for TOTP factor. |
| `uri` | `string` | URI for authenticator apps. |
