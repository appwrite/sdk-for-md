# listUsage

Description: Get usage metrics and statistics for all sites in the project. View statistics including total deployments, builds, logs, storage usage, and compute time. The response includes both current totals and historical data for each metric. Use the optional range parameter to specify the time window for historical data: 24h (last 24 hours), 30d (last 30 days), or 90d (last 90 days). If not specified, defaults to 30 days.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, Sites, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.UsageSites = await sites.listUsage({
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageSites` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | Time range of the usage stats. |
| `sitesTotal` | `number` | Total aggregated number of sites. |
| `sites` | `object[]` | Aggregated number of sites per period. |
| `deploymentsTotal` | `number` | Total aggregated number of sites deployments. |
| `deploymentsStorageTotal` | `number` | Total aggregated sum of sites deployment storage. |
| `buildsTotal` | `number` | Total aggregated number of sites build. |
| `buildsStorageTotal` | `number` | total aggregated sum of sites build storage. |
| `buildsTimeTotal` | `number` | Total aggregated sum of sites build compute time. |
| `buildsMbSecondsTotal` | `number` | Total aggregated sum of sites build mbSeconds. |
| `executionsTotal` | `number` | Total  aggregated number of sites execution. |
| `executionsTimeTotal` | `number` | Total aggregated sum of sites  execution compute time. |
| `executionsMbSecondsTotal` | `number` | Total aggregated sum of sites execution mbSeconds. |
| `requestsTotal` | `number` | Total aggregated number of requests. |
| `requests` | `object[]` | Aggregated number of requests per period. |
| `inboundTotal` | `number` | Total aggregated inbound bandwidth. |
| `inbound` | `object[]` | Aggregated number of inbound bandwidth per period. |
| `outboundTotal` | `number` | Total aggregated outbound bandwidth. |
| `outbound` | `object[]` | Aggregated number of outbound bandwidth per period. |
| `deployments` | `object[]` | Aggregated number of sites deployment per period. |
| `deploymentsStorage` | `object[]` | Aggregated number of  sites deployment storage per period. |
| `buildsSuccessTotal` | `number` | Total aggregated number of successful site builds. |
| `buildsFailedTotal` | `number` | Total aggregated number of failed site builds. |
| `builds` | `object[]` | Aggregated number of sites build per period. |
| `buildsStorage` | `object[]` | Aggregated sum of sites build storage per period. |
| `buildsTime` | `object[]` | Aggregated sum of  sites build compute time per period. |
| `buildsMbSeconds` | `object[]` | Aggregated sum of sites build mbSeconds per period. |
| `executions` | `object[]` | Aggregated number of  sites execution per period. |
| `executionsTime` | `object[]` | Aggregated number of sites execution compute time per period. |
| `executionsMbSeconds` | `object[]` | Aggregated number of sites mbSeconds per period. |
| `buildsSuccess` | `object[]` | Aggregated number of successful site builds per period. |
| `buildsFailed` | `object[]` | Aggregated number of failed site builds per period. |
