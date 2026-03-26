# validatePayment

Description: Validate payment for team after creation or upgrade.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |
| `invites` | `string[]` | ❌ | Additional member invites (Default: `[]`) |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.Organization = await organizations.validatePayment({
  organizationId: '<ORGANIZATION_ID>',
  invites: [],
});
```

## Response Model

Returns a `Models.Organization` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Team ID. |
| `createdAt` | `string` | Team creation date in ISO 8601 format. |
| `updatedAt` | `string` | Team update date in ISO 8601 format. |
| `name` | `string` | Team name. |
| `total` | `number` | Total number of team members. |
| `prefs` | `object` | Team preferences as a key-value object |
| `billingBudget` | `number` | Project budget limit |
| `budgetAlerts` | `number[]` | Project budget limit |
| `billingPlan` | `string` | Organization&#039;s billing plan ID. |
| `billingPlanId` | `string` | Organization&#039;s billing plan ID. |
| `billingPlanDetails` | `object` | Organization&#039;s billing plan. |
| `billingEmail` | `string` | Billing email set for the organization. |
| `billingStartDate` | `string` | Billing cycle start date. |
| `billingCurrentInvoiceDate` | `string` | Current invoice cycle start date. |
| `billingNextInvoiceDate` | `string` | Next invoice cycle start date. |
| `billingTrialStartDate` | `string` | Start date of trial. |
| `billingTrialDays` | `number` | Number of trial days. |
| `billingAggregationId` | `string` | Current active aggregation id. |
| `billingInvoiceId` | `string` | Current active aggregation id. |
| `paymentMethodId` | `string` | Default payment method. |
| `billingAddressId` | `string` | Default payment method. |
| `backupPaymentMethodId` | `string` | Backup payment method. |
| `status` | `string` | Team status. |
| `remarks` | `string` | Remarks on team status. |
| `agreementBAA` | `string` | Organization agreements |
| `programManagerName` | `string` | Program manager&#039;s name. |
| `programManagerCalendar` | `string` | Program manager&#039;s calendar link. |
| `programDiscordChannelName` | `string` | Program&#039;s discord channel name. |
| `programDiscordChannelUrl` | `string` | Program&#039;s discord channel URL. |
| `billingLimits` | `object` | Billing limits reached |
| `billingPlanDowngrade` | `string` | Billing plan selected for downgrade. |
| `billingTaxId` | `string` | Tax Id |
| `markedForDeletion` | `boolean` | Marked for deletion |
| `platform` | `string` | Product with which the organization is associated (appwrite or imagine) |
| `projects` | `string[]` | Selected projects |
