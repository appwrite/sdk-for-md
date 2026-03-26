# updateBillingAddress

Description: Update a specific billing address using it&#039;s ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `billingAddressId` | `string` | ✅ | Unique ID of billing address |
| `country` | `string` | ✅ | Country |
| `city` | `string` | ✅ | City |
| `streetAddress` | `string` | ✅ | Street address |
| `addressLine2` | `string` | ❌ | Address line 2 |
| `state` | `string` | ❌ | State or province |
| `postalCode` | `string` | ❌ | Postal code |

## Usage

```typescript
import { Client, Account, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const account = new Account(client);
const result: Models.BillingAddress = await account.updateBillingAddress({
  billingAddressId: '<BILLING_ADDRESS_ID>',
  country: '<COUNTRY>',
  city: '<CITY>',
  streetAddress: '<STREET_ADDRESS>',
  addressLine2: '<ADDRESS_LINE2>',
  state: '<STATE>',
  postalCode: '<POSTAL_CODE>',
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
