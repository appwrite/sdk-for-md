# createPurchase

Description: Initiate a domain purchase by providing registrant details and a payment method. Authorizes the payment and returns a `clientSecret`. If 3D Secure is required, use the `clientSecret` on the client to complete the authentication challenge. Once authentication is complete (or if none is needed), call the Update Purchase endpoint to capture the payment and finalize the purchase.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `domain` | `string` | ✅ | Fully qualified domain name to purchase (for example, example.com). |
| `organizationId` | `string` | ✅ | Team ID that will own the domain. |
| `firstName` | `string` | ✅ | Registrant first name used for domain registration. |
| `lastName` | `string` | ✅ | Registrant last name used for domain registration. |
| `email` | `string` | ✅ | Registrant email address for registration and notices. |
| `phone` | `string` | ✅ | Registrant phone number in E.164 format (for example, +15555551234). |
| `billingAddressId` | `string` | ✅ | Billing address ID used for registration contact details. |
| `paymentMethodId` | `string` | ✅ | Payment method ID to authorize and capture the purchase. |
| `addressLine3` | `string` | ❌ | Additional address line for the registrant (line 3). |
| `companyName` | `string` | ❌ | Company or organization name for the registrant. |
| `periodYears` | `number` | ❌ | Registration term in years (1-10). (Default: `1`) |
| `autoRenewal` | `boolean` | ❌ | Whether the domain should renew automatically after purchase. (Default: `1`) |

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.DomainPurchase = await domains.createPurchase({
  domain: '',
  organizationId: '<ORGANIZATION_ID>',
  firstName: '<FIRST_NAME>',
  lastName: '<LAST_NAME>',
  email: 'email@example.com',
  phone: '+12065550100',
  billingAddressId: '<BILLING_ADDRESS_ID>',
  paymentMethodId: '<PAYMENT_METHOD_ID>',
  addressLine3: '<ADDRESS_LINE3>',
  companyName: '<COMPANY_NAME>',
  periodYears: 1,
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
