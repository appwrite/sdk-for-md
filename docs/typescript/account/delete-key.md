# deleteKey

Description: Delete a key by its unique ID. Once deleted, the key can no longer be used to authenticate API calls.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `keyId` | `string` | ✅ | Key unique ID. |

## Usage

```typescript
import { Client, Account } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result = await account.deleteKey({
  keyId: '<KEY_ID>',
});
```
