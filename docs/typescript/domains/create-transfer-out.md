# createTransferOut

Description: Initiate a domain transfer-out by generating an authorization code for the specified domain. The returned `authCode` should be provided to the gaining provider to complete the transfer. If the domain has auto-renewal enabled, it will be automatically disabled as part of this operation.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain unique ID. |
| `organizationId` | `string` | ✅ | Organization ID that this domain belongs to. |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DomainTransferOut = await domains.createTransferOut({
  domainId: '<DOMAIN_ID>',
  organizationId: '<ORGANIZATION_ID>',
});
```

## Response Model

Returns a `Models.DomainTransferOut` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `authCode` | `string` | Domain transfer authorization code. |
