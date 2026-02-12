# deleteRecord

Description: Delete a DNS record for the given domain. This endpoint allows you to delete an existing DNS record 
    from a specific domain.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |
| `recordId` | `string` | ✅ | DNS record unique ID. |

## Usage

```typescript
import { Client, Domains } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result = await domains.deleteRecord({
  domainId: '<DOMAIN_ID>',
  recordId: '<RECORD_ID>',
});
```
