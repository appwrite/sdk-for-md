# createTransferIn

Description: Initiate a domain transfer-in by providing an authorization code, registrant details, and a payment method. Authorizes the payment and returns a `clientSecret`. If 3D Secure is required, use the `clientSecret` on the client to complete the authentication challenge. Once authentication is complete (or if none is needed), call the Update Transfer In endpoint to capture the payment and submit the transfer.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domain` | `string` | ✅ | Domain name to transfer in. |
| `organizationId` | `string` | ✅ | Organization ID that this domain will belong to. |
| `authCode` | `string` | ✅ | Authorization code for the domain transfer. |
| `paymentMethodId` | `string` | ✅ | Payment method ID to authorize and capture the transfer. |
| `autoRenewal` | `boolean` | ❌ | Whether the domain should renew automatically after transfer. (Default: `1`) |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DomainPurchase = await domains.createTransferIn({
  domain: '',
  organizationId: '<ORGANIZATION_ID>',
  authCode: '<AUTH_CODE>',
  paymentMethodId: '<PAYMENT_METHOD_ID>',
  autoRenewal: false,
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
