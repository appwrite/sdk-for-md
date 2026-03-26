# getPlans

Description: Return a list of all available plans.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `platform` | `Platform` | ❌ | Platform type (Default: `appwrite`)<br>**Allowed:** `appwrite`, `imagine` |

## Usage

```typescript
import { Client, Console, Platform, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const console = new Console(client);
const result: Models.BillingPlanList = await console.getPlans({
  platform: Platform.Appwrite,
});
```

## Response Model

Returns a `Models.BillingPlanList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of plans that matched your query. |
| `plans` | `object[]` | List of plans. |
