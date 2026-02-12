# deleteBillingAddress

Description: Delete a team&#039;s billing address.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |

## Usage

```typescript
import { Client, Organizations } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result = await organizations.deleteBillingAddress({
  organizationId: '<ORGANIZATION_ID>',
});
```
