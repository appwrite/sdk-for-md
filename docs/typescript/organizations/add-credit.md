# addCredit

Description: Add credit to an organization using a coupon.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |
| `couponId` | `string` | ✅ | ID of the coupon |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.Credit = await organizations.addCredit({
  organizationId: '<ORGANIZATION_ID>',
  couponId: '<COUPON_ID>',
});
```

## Response Model

Returns a `Models.Credit` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Credit ID. |
| `createdAt` | `string` | Credit creation time in ISO 8601 format. |
| `updatedAt` | `string` | Credit update date in ISO 8601 format. |
| `permissions` | `string[]` | Credit permissions. [Learn more about permissions](/docs/permissions). |
| `couponId` | `string` | coupon ID |
| `userId` | `string` | ID of the User. |
| `teamId` | `string` | ID of the Team. |
| `credits` | `number` | Provided credit amount |
| `total` | `number` | Provided credit amount |
| `expiration` | `string` | Credit expiration time in ISO 8601 format. |
| `status` | `string` | Status of the credit. Can be one of `disabled`, `active` or `expired`. |
