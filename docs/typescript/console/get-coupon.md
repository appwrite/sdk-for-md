# getCoupon

Description: Get the details of a coupon using it&#039;s coupon ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `couponId` | `string` | ✅ | ID of the coupon |

## Usage

```typescript
import { Client, Console, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const console = new Console(client);
const result: Models.Coupon = await console.getCoupon({
  couponId: '<COUPON_ID>',
});
```

## Response Model

Returns a `Models.Coupon` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | coupon ID |
| `code` | `string` | coupon ID |
| `credits` | `number` | Provided credit amount |
| `expiration` | `string` | Coupon expiration time in ISO 8601 format. |
| `validity` | `number` | Credit validity in days. |
| `campaign` | `string` | Campaign the coupon is associated with`. |
| `status` | `string` | Status of the coupon. Can be one of `disabled`, `active` or `expired`. |
| `onlyNewOrgs` | `boolean` | If the coupon is only valid for new organizations or not. |
