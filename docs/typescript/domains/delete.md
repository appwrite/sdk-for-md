# delete

Description: Delete a domain by its unique ID. This endpoint can be used to delete a domain from your project.
Once deleted, the domain will no longer be available for use and all associated resources will be removed.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |

## Usage

```typescript
import { Client, Domains } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result = await domains.delete({
  domainId: '<DOMAIN_ID>',
});
```
