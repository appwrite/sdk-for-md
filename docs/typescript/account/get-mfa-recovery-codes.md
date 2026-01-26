# getMFARecoveryCodes

Description: Get recovery codes that can be used as backup for MFA flow. Before getting codes, they must be generated using [createMfaRecoveryCodes](/docs/references/cloud/client-web/account#createMfaRecoveryCodes) method. An OTP challenge is required to read recovery codes.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.MfaRecoveryCodes = await account.getMFARecoveryCodes();
```

## Response Model

Returns a `Models.MfaRecoveryCodes` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `recoveryCodes` | `string[]` | Recovery codes. |
