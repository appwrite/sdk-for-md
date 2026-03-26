# estimationUpdatePlan

Description: Get estimation for updating the organization plan.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |
| `billingPlan` | `string` | ✅ | Organization billing plan chosen |
| `invites` | `string[]` | ❌ | Additional member invites (Default: `[]`) |
| `couponId` | `string` | ❌ | Coupon id |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.EstimationUpdatePlan = await organizations.estimationUpdatePlan({
  organizationId: '<ORGANIZATION_ID>',
  billingPlan: 'tier-0',
  invites: [],
  couponId: '<COUPON_ID>',
});
```

## Response Model

Returns a `Models.EstimationUpdatePlan` object with the following properties:

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
| `organizationCredits` | `number` | Organization&#039;s existing credits |
