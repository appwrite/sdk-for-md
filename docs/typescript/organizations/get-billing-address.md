# getBillingAddress

Description: Get a billing address using it&#039;s ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |
| `billingAddressId` | `string` | ✅ | Unique ID of billing address |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.BillingAddress = await organizations.getBillingAddress({
  organizationId: '<ORGANIZATION_ID>',
  billingAddressId: '<BILLING_ADDRESS_ID>',
});
```

## Response Model

Returns a `Models.BillingAddress` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Region ID |
| `userId` | `string` | User ID |
| `streetAddress` | `string` | Street address |
| `addressLine2` | `string` | Address line 2 |
| `country` | `string` | Address country |
| `city` | `string` | city |
| `state` | `string` | state |
| `postalCode` | `string` | postal code |
