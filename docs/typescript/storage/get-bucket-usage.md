# getBucketUsage

Description: Get usage metrics and statistics a specific bucket in the project. You can view the total number of files, storage usage. The response includes both current totals and historical data over time. Use the optional range parameter to specify the time window for historical data: 24h (last 24 hours), 30d (last 30 days), or 90d (last 90 days). If not specified, range defaults to 30 days.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `bucketId` | `string` | ✅ | Bucket ID. |
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, Storage, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const storage = new Storage(client);
const result: Models.UsageBuckets = await storage.getBucketUsage({
  bucketId: '<BUCKET_ID>',
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageBuckets` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | Time range of the usage stats. |
| `filesTotal` | `number` | Total aggregated number of bucket files. |
| `filesStorageTotal` | `number` | Total aggregated number of bucket files storage (in bytes). |
| `files` | `object[]` | Aggregated  number of bucket files per period. |
| `storage` | `object[]` | Aggregated  number of bucket storage files (in bytes) per period. |
| `imageTransformations` | `object[]` | Aggregated number of files transformations per period. |
| `imageTransformationsTotal` | `number` | Total aggregated number of files transformations. |
