# deleteDevKey

Description: Delete a project\&#039;s dev key by its unique ID. Once deleted, the key will no longer allow bypassing of rate limits and better logging of errors.

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
const result = await projects.deleteDevKey({
  projectId: '<PROJECT_ID>',
  keyId: '<KEY_ID>',
});
```
