# updateAutoRenewal

Description: Enable or disable auto-renewal for a domain.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |
| `autoRenewal` | `boolean` | ✅ | Whether the domain should renew automatically. |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.Domain = await domains.updateAutoRenewal({
  domainId: '<DOMAIN_ID>',
  autoRenewal: false,
});
```

## Response Model

Returns a `Models.Domain` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Domain ID. |
| `createdAt` | `string` | Domain creation time in ISO 8601 format. |
| `updatedAt` | `string` | Domain update date in ISO 8601 format. |
| `domain` | `string` | Domain name. |
| `registrar` | `string` | Domain registrar (e.g. &quot;appwrite&quot; or &quot;third_party&quot;). |
| `nameservers` | `string` | Nameservers setting. &quot;Appwrite&quot; or empty string. |
| `expire` | `string` | Domain expiry date in ISO 8601 format. |
| `renewal` | `string` | Domain renewal date in ISO 8601 format. |
| `autoRenewal` | `boolean` | If set to true, the domain will automatically renew. |
| `renewalPrice` | `number` | Renewal price (in cents). |
| `transferStatus` | `DomainTransferStatusEnum` | Transfer status for domains being transferred in. |
| `teamId` | `string` | Team ID. |
| `dnsRecords` | `object[]` | Dns records |
