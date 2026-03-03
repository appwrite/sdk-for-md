# createPurchase

Description: Create a domain purchase with registrant information.

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

## Usage

```typescript
import { Client, Domains, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const domains = new Domains(client);
const result: Models.Domain = await domains.createPurchase({
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
