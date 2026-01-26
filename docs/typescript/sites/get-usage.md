# getUsage

Description: Get usage metrics and statistics for a for a specific site. View statistics including total deployments, builds, executions, storage usage, and compute time. The response includes both current totals and historical data for each metric. Use the optional range parameter to specify the time window for historical data: 24h (last 24 hours), 30d (last 30 days), or 90d (last 90 days). If not specified, defaults to 30 days.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site ID. |
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, Sites, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.UsageSite = await sites.getUsage({
  siteId: '<SITE_ID>',
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageSite` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | The time range of the usage stats. |
| `deploymentsTotal` | `number` | Total aggregated number of function deployments. |
| `deploymentsStorageTotal` | `number` | Total aggregated sum of function deployments storage. |
| `buildsTotal` | `number` | Total aggregated number of function builds. |
| `buildsSuccessTotal` | `number` | Total aggregated number of successful function builds. |
| `buildsFailedTotal` | `number` | Total aggregated number of failed function builds. |
| `buildsStorageTotal` | `number` | total aggregated sum of function builds storage. |
| `buildsTimeTotal` | `number` | Total aggregated sum of function builds compute time. |
| `buildsTimeAverage` | `number` | Average builds compute time. |
| `buildsMbSecondsTotal` | `number` | Total aggregated sum of function builds mbSeconds. |
| `executionsTotal` | `number` | Total  aggregated number of function executions. |
| `executionsTimeTotal` | `number` | Total aggregated sum of function  executions compute time. |
| `executionsMbSecondsTotal` | `number` | Total aggregated sum of function executions mbSeconds. |
| `deployments` | `object[]` | Aggregated number of function deployments per period. |
| `deploymentsStorage` | `object[]` | Aggregated number of  function deployments storage per period. |
| `builds` | `object[]` | Aggregated number of function builds per period. |
| `buildsStorage` | `object[]` | Aggregated sum of function builds storage per period. |
| `buildsTime` | `object[]` | Aggregated sum of function builds compute time per period. |
| `buildsMbSeconds` | `object[]` | Aggregated number of function builds mbSeconds per period. |
| `executions` | `object[]` | Aggregated number of function executions per period. |
| `executionsTime` | `object[]` | Aggregated number of function executions compute time per period. |
| `executionsMbSeconds` | `object[]` | Aggregated number of function mbSeconds per period. |
| `buildsSuccess` | `object[]` | Aggregated number of successful builds per period. |
| `buildsFailed` | `object[]` | Aggregated number of failed builds per period. |
| `requestsTotal` | `number` | Total aggregated number of requests. |
| `requests` | `object[]` | Aggregated number of requests per period. |
| `inboundTotal` | `number` | Total aggregated inbound bandwidth. |
| `inbound` | `object[]` | Aggregated number of inbound bandwidth per period. |
| `outboundTotal` | `number` | Total aggregated outbound bandwidth. |
| `outbound` | `object[]` | Aggregated number of outbound bandwidth per period. |
