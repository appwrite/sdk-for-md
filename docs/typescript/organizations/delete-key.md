# deleteKey

Description: Delete a key by its unique ID. Once deleted, the key can no longer be used to authenticate API calls.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization Unique ID |
| `keyId` | `string` | ✅ | Key unique ID. |

## Usage

```typescript
import { Client, Organizations } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result = await organizations.deleteKey({
  organizationId: '<ORGANIZATION_ID>',
  keyId: '<KEY_ID>',
});
```
