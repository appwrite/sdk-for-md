# updateNameservers

Description: Verify which NS records are used and update the domain accordingly. This will check the domain&#039;s
    nameservers and update the domain&#039;s status based on whether the nameservers match the expected
    Appwrite nameservers.

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
const result: Models.Domain = await domains.updateNameservers({
  domainId: '<DOMAIN_ID>',
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
| `renewalPrice` | `number` | Renewal price (in USD). |
| `teamId` | `string` | Team ID. |
| `dnsRecords` | `object[]` | Dns records |
