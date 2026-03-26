# createDowngradeFeedback

Description: Submit feedback about downgrading from a paid plan to a lower tier. This helps the team understand user experience and improve the platform.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization Unique ID |
| `reason` | `string` | ✅ | Feedback reason |
| `message` | `string` | ✅ | Feedback message |
| `fromPlanId` | `string` | ✅ | Plan downgrading from |
| `toPlanId` | `string` | ✅ | Plan downgrading to |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.DowngradeFeedback = await organizations.createDowngradeFeedback({
  organizationId: '<ORGANIZATION_ID>',
  reason: '<REASON>',
  message: '<MESSAGE>',
  fromPlanId: '<FROM_PLAN_ID>',
  toPlanId: '<TO_PLAN_ID>',
});
```

## Response Model

Returns a `Models.DowngradeFeedback` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Feedback ID. |
| `createdAt` | `string` | Feedback creation date in ISO 8601 format. |
| `updatedAt` | `string` | Feedback update date in ISO 8601 format. |
| `title` | `string` | Feedback reason |
| `message` | `string` | Feedback message |
| `fromPlanId` | `string` | Plan ID downgrading from |
| `toPlanId` | `string` | Plan ID downgrading to |
| `teamId` | `string` | Organization ID |
| `userId` | `string` | User ID who submitted feedback |
| `version` | `string` | Console version |
