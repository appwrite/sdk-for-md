# updateTeam

Description: Update the team ID for a specific domain. This endpoint requires admin access.
    
    Updating the team ID will transfer ownership and access control of the domain
    and all its DNS records to the new team.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |
| `teamId` | `string` | ✅ | New team unique ID. |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.Domain = await domains.updateTeam({
  domainId: '<DOMAIN_ID>',
  teamId: '<TEAM_ID>',
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
