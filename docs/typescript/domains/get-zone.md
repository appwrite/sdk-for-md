# getZone

Description: Retrieve the DNS zone file for the given domain. This endpoint will return the DNS
    zone file in a standardized format that can be used to configure DNS servers.

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
const result = await domains.getZone({
  domainId: '<DOMAIN_ID>',
});
```
