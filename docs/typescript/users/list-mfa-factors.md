# listMFAFactors

Description: List the factors available on the account to be used as a MFA challange.

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
const result: Models.MfaFactors = await users.listMFAFactors({
  userId: '<USER_ID>',
});
```

## Response Model

Returns a `Models.MfaFactors` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `totp` | `boolean` | Can TOTP be used for MFA challenge for this account. |
| `phone` | `boolean` | Can phone (SMS) be used for MFA challenge for this account. |
| `email` | `boolean` | Can email be used for MFA challenge for this account. |
| `recoveryCode` | `boolean` | Can recovery code be used for MFA challenge for this account. |
