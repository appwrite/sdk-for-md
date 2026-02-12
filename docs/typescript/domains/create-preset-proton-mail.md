# createPresetProtonMail

Description: Add ProtonMail DNS records to the domain. This will create the required MX records
    for using ProtonMail with your custom domain.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DnsRecordsList = await domains.createPresetProtonMail({
  domainId: '<DOMAIN_ID>',
});
```

## Response Model

Returns a `Models.DnsRecordsList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of dnsRecords that matched your query. |
| `dnsRecords` | `object[]` | List of dnsRecords. |
