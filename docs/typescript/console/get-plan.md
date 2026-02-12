# getPlan

Description: Get the details of a plan using its plan ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `planId` | `string` | ✅ | Plan id |

## Usage

```typescript
import { Client, Console, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const console = new Console(client);
const result: Models.BillingPlan = await console.getPlan({
  planId: '<PLAN_ID>',
});
```

## Response Model

Returns a `Models.BillingPlan` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Plan ID. |
| `name` | `string` | Plan name |
| `desc` | `string` | Plan description |
| `order` | `number` | Plan order |
| `price` | `number` | Price |
| `trial` | `number` | Trial days |
| `bandwidth` | `number` | Bandwidth |
| `storage` | `number` | Storage |
| `imageTransformations` | `number` | Image Transformations |
| `screenshotsGenerated` | `number` | Screenshots generated |
| `members` | `number` | Members |
| `webhooks` | `number` | Webhooks |
| `projects` | `number` | Projects |
| `platforms` | `number` | Platforms |
| `users` | `number` | Users |
| `teams` | `number` | Teams |
| `databases` | `number` | Databases |
| `databasesReads` | `number` | Database reads per month |
| `databasesWrites` | `number` | Database writes per month |
| `databasesBatchSize` | `number` | Database batch size limit |
| `buckets` | `number` | Buckets |
| `fileSize` | `number` | File size |
| `functions` | `number` | Functions |
| `sites` | `number` | Sites |
| `executions` | `number` | Function executions |
| `executionsRetentionCount` | `number` | Rolling max executions retained per function/site |
| `gBHours` | `number` | GB hours for functions |
| `realtime` | `number` | Realtime connections |
| `messages` | `number` | Messages per month |
| `topics` | `number` | Topics for messaging |
| `authPhone` | `number` | SMS authentications per month |
| `domains` | `number` | Custom domains |
| `logs` | `number` | Log days |
| `alertLimit` | `number` | Alert threshold percentage |
| `usage` | `object` | Additional resources |
| `addons` | `object` | Addons |
| `budgetCapEnabled` | `boolean` | Budget cap enabled or disabled. |
| `customSmtp` | `boolean` | Custom SMTP |
| `emailBranding` | `boolean` | Appwrite branding in email |
| `requiresPaymentMethod` | `boolean` | Does plan require payment method |
| `requiresBillingAddress` | `boolean` | Does plan require billing address |
| `isAvailable` | `boolean` | Is the billing plan available |
| `selfService` | `boolean` | Can user change the plan themselves |
| `premiumSupport` | `boolean` | Does plan enable premium support |
| `budgeting` | `boolean` | Does plan support budget cap |
| `supportsMockNumbers` | `boolean` | Does plan support mock numbers |
| `supportsOrganizationRoles` | `boolean` | Does plan support organization roles |
| `supportsCredits` | `boolean` | Does plan support credit |
| `backupsEnabled` | `boolean` | Does plan support backup policies. |
| `usagePerProject` | `boolean` | Whether usage addons are calculated per project. |
| `backupPolicies` | `number` | How many policies does plan support |
| `deploymentSize` | `number` | Maximum function and site deployment size in MB |
| `buildSize` | `number` | Maximum function and site deployment size in MB |
| `databasesAllowEncrypt` | `boolean` | Does the plan support encrypted string attributes or not. |
| `limits` | `object` | Plan specific limits |
| `group` | `BillingPlanGroup` | Group of this billing plan for variants |
| `program` | `object` | Details of the program this plan is a part of. |
