# createInvoicePayment

Description: Initiate payment for failed invoice to pay live from console

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |
| `invoiceId` | `string` | ✅ | Invoice unique ID |
| `paymentMethodId` | `string` | ✅ | Payment method ID |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.Invoice = await organizations.createInvoicePayment({
  organizationId: '<ORGANIZATION_ID>',
  invoiceId: '<INVOICE_ID>',
  paymentMethodId: '<PAYMENT_METHOD_ID>',
});
```

## Response Model

Returns a `Models.Invoice` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Invoice ID. |
| `createdAt` | `string` | Invoice creation time in ISO 8601 format. |
| `updatedAt` | `string` | Invoice update date in ISO 8601 format. |
| `permissions` | `string[]` | Invoice permissions. [Learn more about permissions](/docs/permissions). |
| `teamId` | `string` | Project ID |
| `aggregationId` | `string` | Aggregation ID |
| `plan` | `string` | Billing plan selected. Can be one of `tier-0`, `tier-1` or `tier-2`. |
| `usage` | `object[]` | Usage breakdown per resource |
| `amount` | `number` | Invoice Amount |
| `tax` | `number` | Tax percentage |
| `taxAmount` | `number` | Tax amount |
| `vat` | `number` | VAT percentage |
| `vatAmount` | `number` | VAT amount |
| `grossAmount` | `number` | Gross amount after vat, tax, and discounts applied. |
| `creditsUsed` | `number` | Credits used. |
| `currency` | `string` | Currency the invoice is in |
| `clientSecret` | `string` | Client secret for processing failed payments in front-end |
| `status` | `string` | Invoice status |
| `lastError` | `string` | Last payment error associated with the invoice |
| `dueAt` | `string` | Invoice due date. |
| `from` | `string` | Beginning date of the invoice |
| `to` | `string` | End date of the invoice |
