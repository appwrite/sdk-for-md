# deleteIdentity

Description: Delete an identity by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `identityId` | `string` | ✅ | Identity ID. |

## Usage

```typescript
import { Client, Account } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result = await account.deleteIdentity({
  identityId: '<IDENTITY_ID>',
});
```
