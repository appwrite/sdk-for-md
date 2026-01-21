# deleteKey

Description: Delete a key by its unique ID. Once deleted, the key can no longer be used to authenticate API calls.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `keyId` | `string` | ✅ | Key unique ID. |

## Usage

```typescript
import { Client, Projects } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result = await projects.deleteKey({
  projectId: '<PROJECT_ID>',
  keyId: '<KEY_ID>',
});
```
