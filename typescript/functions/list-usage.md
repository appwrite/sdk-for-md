# listUsage

Description: Get usage metrics and statistics for all functions in the project. View statistics including total deployments, builds, logs, storage usage, and compute time. The response includes both current totals and historical data for each metric. Use the optional range parameter to specify the time window for historical data: 24h (last 24 hours), 30d (last 30 days), or 90d (last 90 days). If not specified, defaults to 30 days.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, Functions, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.UsageFunctions = await functions.listUsage({
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageFunctions` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | Time range of the usage stats. |
| `functionsTotal` | `number` | Total aggregated number of functions. |
| `deploymentsTotal` | `number` | Total aggregated number of functions deployments. |
| `deploymentsStorageTotal` | `number` | Total aggregated sum of functions deployment storage. |
| `buildsTotal` | `number` | Total aggregated number of functions build. |
| `buildsStorageTotal` | `number` | total aggregated sum of functions build storage. |
| `buildsTimeTotal` | `number` | Total aggregated sum of functions build compute time. |
| `buildsMbSecondsTotal` | `number` | Total aggregated sum of functions build mbSeconds. |
| `executionsTotal` | `number` | Total  aggregated number of functions execution. |
| `executionsTimeTotal` | `number` | Total aggregated sum of functions  execution compute time. |
| `executionsMbSecondsTotal` | `number` | Total aggregated sum of functions execution mbSeconds. |
| `functions` | `object[]` | Aggregated number of functions per period. |
| `deployments` | `object[]` | Aggregated number of functions deployment per period. |
| `deploymentsStorage` | `object[]` | Aggregated number of  functions deployment storage per period. |
| `buildsSuccessTotal` | `number` | Total aggregated number of successful function builds. |
| `buildsFailedTotal` | `number` | Total aggregated number of failed function builds. |
| `builds` | `object[]` | Aggregated number of functions build per period. |
| `buildsStorage` | `object[]` | Aggregated sum of functions build storage per period. |
| `buildsTime` | `object[]` | Aggregated sum of  functions build compute time per period. |
| `buildsMbSeconds` | `object[]` | Aggregated sum of functions build mbSeconds per period. |
| `executions` | `object[]` | Aggregated number of  functions execution per period. |
| `executionsTime` | `object[]` | Aggregated number of functions execution compute time per period. |
| `executionsMbSeconds` | `object[]` | Aggregated number of functions mbSeconds per period. |
| `buildsSuccess` | `object[]` | Aggregated number of successful function builds per period. |
| `buildsFailed` | `object[]` | Aggregated number of failed function builds per period. |
