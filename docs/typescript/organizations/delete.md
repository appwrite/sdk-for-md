# delete

Description: Delete an organization.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Team ID. |

## Usage

```typescript
import { Client, Organizations } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result = await organizations.delete({
  organizationId: '<ORGANIZATION_ID>',
});
```
