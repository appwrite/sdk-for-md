# createMFARecoveryCodes

Description: Generate recovery codes as backup for MFA flow. It&#039;s recommended to generate and show then immediately after user successfully adds their authehticator. Recovery codes can be used as a MFA verification type in [createMfaChallenge](/docs/references/cloud/client-web/account#createMfaChallenge) method.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.MfaRecoveryCodes = await account.createMFARecoveryCodes();
```

## Response Model

Returns a `Models.MfaRecoveryCodes` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `recoveryCodes` | `string[]` | Recovery codes. |
