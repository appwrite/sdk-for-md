# createTransferIn

Description: Create a domain transfer in with authorization code and registrant information.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domain` | `string` | ✅ | Domain name to transfer in. |
| `organizationId` | `string` | ✅ | Organization ID that this domain will belong to. |
| `authCode` | `string` | ✅ | Authorization code for the domain transfer. |
| `paymentMethodId` | `string` | ✅ | Payment method ID to authorize and capture the transfer. |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.Domain = await domains.createTransferIn({
  domain: '',
  organizationId: '<ORGANIZATION_ID>',
  authCode: '<AUTH_CODE>',
  paymentMethodId: '<PAYMENT_METHOD_ID>',
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
| `paymentStatus` | `string` | Payment status for domain purchase. |
| `nameservers` | `string` | Nameservers setting. &quot;Appwrite&quot; or empty string. |
| `expire` | `string` | Domain expiry date in ISO 8601 format. |
| `renewal` | `string` | Domain renewal date in ISO 8601 format. |
| `autoRenewal` | `boolean` | If set to true, the domain will automatically renew. |
| `renewalPrice` | `number` | Renewal price (in cents). |
| `teamId` | `string` | Team ID. |
| `dnsRecords` | `object[]` | Dns records |
| `transferStatus` | `string` | Domain transfer status (e.g., &quot;pending&quot;, &quot;completed&quot;, &quot;failed&quot;). |
