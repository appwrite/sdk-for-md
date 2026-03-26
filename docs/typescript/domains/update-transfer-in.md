# updateTransferIn

Description: Finalize a domain transfer-in initiated with Create Transfer In. Verifies that any required 3D Secure authentication is complete, submits the transfer with the authorization code, captures the payment, and sends a confirmation email. Returns a 402 error if authentication is still pending.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domainId` | `string` | ✅ | Domain ID to confirm transfer for. |
| `organizationId` | `string` | ✅ | Team ID that owns the domain. |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DomainPurchase = await domains.updateTransferIn({
  domainId: '<DOMAIN_ID>',
  organizationId: '<ORGANIZATION_ID>',
});
```

## Response Model

Returns a `Models.DomainPurchase` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Purchase/invoice ID. |
| `createdAt` | `string` | Purchase creation time in ISO 8601 format. |
| `updatedAt` | `string` | Purchase update date in ISO 8601 format. |
| `domainId` | `string` | Domain document ID. |
| `domain` | `string` | Domain name. |
| `organizationId` | `string` | Team ID that owns the domain. |
| `status` | `DomainPurchaseStatus` | Domain purchase status. |
| `clientSecret` | `string` | Stripe client secret for 3DS; empty when not applicable. |
| `amount` | `number` | Purchase amount. |
| `currency` | `string` | Currency code. |
