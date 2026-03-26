# estimationCreateOrganization

Description: Get estimation for creating an organization.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `billingPlan` | `string` | ✅ | Organization billing plan chosen |
| `paymentMethodId` | `string` | ❌ | Payment method ID. Required for pro plans when trial is not available and user doesn&#039;t have default payment method set. |
| `invites` | `string[]` | ❌ | Additional member invites (Default: `[]`) |
| `couponId` | `string` | ❌ | Coupon id |
| `platform` | `Platform` | ❌ | Platform type (Default: `appwrite`)<br>**Allowed:** `appwrite`, `imagine` |

## Usage

```typescript
import { Client, Organizations, Platform, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.Estimation = await organizations.estimationCreateOrganization({
  billingPlan: 'tier-0',
  paymentMethodId: '<PAYMENT_METHOD_ID>',
  invites: [],
  couponId: '<COUPON_ID>',
  platform: Platform.Appwrite,
});
```

## Response Model

Returns a `Models.Estimation` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `amount` | `number` | Total amount |
| `grossAmount` | `number` | Gross payable amount |
| `discount` | `number` | Discount amount |
| `credits` | `number` | Credits amount |
| `items` | `object[]` | Estimation items |
| `discounts` | `object[]` | Estimation discount items |
| `trialDays` | `number` | Trial days |
| `trialEndDate` | `string` | Trial end date |
