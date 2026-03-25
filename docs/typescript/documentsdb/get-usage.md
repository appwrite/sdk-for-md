# getUsage

Description: Get usage metrics and statistics for a database. You can view the total number of collections, documents, and storage usage. The response includes both current totals and historical data over time. Use the optional range parameter to specify the time window for historical data: 24h (last 24 hours), 30d (last 30 days), or 90d (last 90 days). If not specified, range defaults to 30 days.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, DocumentsDB, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const documentsDB = new DocumentsDB(client);
const result: Models.UsageDocumentsDB = await documentsDB.getUsage({
  databaseId: '<DATABASE_ID>',
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageDocumentsDB` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | Time range of the usage stats. |
| `collectionsTotal` | `number` | Total aggregated number of collections. |
| `documentsTotal` | `number` | Total aggregated number of documents. |
| `storageTotal` | `number` | Total aggregated storage used in bytes. |
| `databaseReadsTotal` | `number` | Total number of database reads. |
| `databaseWritesTotal` | `number` | Total number of database writes. |
| `collections` | `object[]` | Aggregated number of collections per period. |
| `documents` | `object[]` | Aggregated number of documents per period. |
| `storage` | `object[]` | Aggregated storage used in bytes per period. |
| `databaseReads` | `object[]` | An array of aggregated number of database reads. |
| `databaseWrites` | `object[]` | An array of aggregated number of database writes. |
