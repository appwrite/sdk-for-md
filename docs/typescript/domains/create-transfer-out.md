# createTransferOut

Description: Create a domain transfer out and return the authorization code.

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
