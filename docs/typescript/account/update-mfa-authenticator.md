# updateMFAAuthenticator

Description: Verify an authenticator app after adding it using the [add authenticator](/docs/references/cloud/client-web/account#createMfaAuthenticator) method.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `type` | `AuthenticatorType` | ✅ | Type of authenticator.<br>**Allowed:** `totp` |
| `otp` | `string` | ✅ | Valid verification token. |

## Usage

```typescript
import { Client, Account, AuthenticatorType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.User = await account.updateMFAAuthenticator({
  type: AuthenticatorType.Totp,
  otp: '<OTP>',
});
```

## Response Model

Returns a `Models.User` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | User ID. |
| `createdAt` | `string` | User creation date in ISO 8601 format. |
| `updatedAt` | `string` | User update date in ISO 8601 format. |
| `name` | `string` | User name. |
| `password` | `string` | Hashed user password. |
| `hash` | `string` | Password hashing algorithm. |
| `hashOptions` | `object` | Password hashing algorithm configuration. |
| `registration` | `string` | User registration date in ISO 8601 format. |
| `status` | `boolean` | User status. Pass `true` for enabled and `false` for disabled. |
| `labels` | `string[]` | Labels for the user. |
| `passwordUpdate` | `string` | Password update time in ISO 8601 format. |
| `email` | `string` | User email address. |
| `phone` | `string` | User phone number in E.164 format. |
| `emailVerification` | `boolean` | Email verification status. |
| `phoneVerification` | `boolean` | Phone verification status. |
| `mfa` | `boolean` | Multi factor authentication status. |
| `prefs` | `object` | User preferences as a key-value object |
| `targets` | `object[]` | A user-owned message receiver. A single user may have multiple e.g. emails, phones, and a browser. Each target is registered with a single provider. |
| `accessedAt` | `string` | Most recent access date in ISO 8601 format. This attribute is only updated again after 24 hours. |
| `impersonator` | `boolean` | Whether the user can impersonate other users. |
| `impersonatorUserId` | `string` | ID of the original actor performing the impersonation. Present only when the current request is impersonating another user. Internal audit logs attribute the action to this user, while the impersonated target is recorded only in internal audit payload data. |
