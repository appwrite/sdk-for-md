# getUsage

Description: Get usage metrics and statistics for all buckets in the project. You can view the total number of buckets, files, storage usage. The response includes both current totals and historical data over time. Use the optional range parameter to specify the time window for historical data: 24h (last 24 hours), 30d (last 30 days), or 90d (last 90 days). If not specified, range defaults to 30 days.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, Storage, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result: Models.UsageStorage = await storage.getUsage({
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageStorage` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | Time range of the usage stats. |
| `bucketsTotal` | `number` | Total aggregated number of buckets |
| `filesTotal` | `number` | Total aggregated number of files. |
| `filesStorageTotal` | `number` | Total aggregated number of files storage (in bytes). |
| `buckets` | `object[]` | Aggregated number of buckets per period. |
| `files` | `object[]` | Aggregated number of files per period. |
| `storage` | `object[]` | Aggregated number of files storage (in bytes) per period . |
