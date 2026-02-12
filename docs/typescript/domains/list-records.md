# listRecords

Description: List DNS records for a given domain. You can use this endpoint to list all the DNS records
    associated with your domain.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. You may filter on attributes such as type, name, value, etc. Maximum of 100 queries are allowed, each 4096 characters long. (Default: `[]`) |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DnsRecordsList = await domains.listRecords({
  domainId: '<DOMAIN_ID>',
  queries: [],
});
```

## Response Model

Returns a `Models.DnsRecordsList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of dnsRecords that matched your query. |
| `dnsRecords` | `object[]` | List of dnsRecords. |
