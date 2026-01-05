# updateMFARecoveryCodes

Description: Regenerate recovery codes that can be used as backup for MFA flow. Before regenerating codes, they must be first generated using [createMfaRecoveryCodes](/docs/references/cloud/client-web/account#createMfaRecoveryCodes) method. An OTP challenge is required to regenreate recovery codes.

## Parameters

This method does not accept any parameters.

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.MfaRecoveryCodes = await account.updateMFARecoveryCodes();
```

## Response Model

Returns a `Models.MfaRecoveryCodes` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `recoveryCodes` | `string[]` | Recovery codes. |
