# getInvoiceDownload

Description: Download invoice in PDF

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |
| `invoiceId` | `string` | ✅ | Invoice unique ID |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.PaymentMethod = await organizations.getInvoiceDownload({
  organizationId: '<ORGANIZATION_ID>',
  invoiceId: '<INVOICE_ID>',
});
```

## Response Model

Returns a `Models.PaymentMethod` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Payment Method ID. |
| `createdAt` | `string` | Payment method creation time in ISO 8601 format. |
| `updatedAt` | `string` | Payment method update date in ISO 8601 format. |
| `permissions` | `string[]` | Payment method permissions. [Learn more about permissions](/docs/permissions). |
| `providerMethodId` | `string` | Payment method ID from the payment provider |
| `clientSecret` | `string` | Client secret hash for payment setup |
| `providerUserId` | `string` | User ID from the payment provider. |
| `userId` | `string` | ID of the Team. |
| `expiryMonth` | `number` | Expiry month of the payment method. |
| `expiryYear` | `number` | Expiry year of the payment method. |
| `last4` | `string` | Last 4 digit of the payment method |
| `brand` | `string` | Payment method brand |
| `name` | `string` | Name of the owner |
| `mandateId` | `string` | Mandate ID of the payment method |
| `country` | `string` | Country of the payment method |
| `state` | `string` | State of the payment method |
| `lastError` | `string` | Last payment error associated with the payment method. |
| `default` | `boolean` | True when it&#039;s the default payment method. |
| `expired` | `boolean` | True when payment method has expired. |
| `failed` | `boolean` | True when payment method has failed to process multiple times. |
