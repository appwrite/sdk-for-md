# getUsage

⚠️ **DEPRECATED** since 1.8.0 - Use `tablesDB.getUsage` instead

Description: Get usage metrics and statistics for a database. You can view the total number of collections, documents, and storage usage. The response includes both current totals and historical data over time. Use the optional range parameter to specify the time window for historical data: 24h (last 24 hours), 30d (last 30 days), or 90d (last 90 days). If not specified, range defaults to 30 days.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, Databases, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const databases = new Databases(client);
const result: Models.UsageDatabase = await databases.getUsage({
  databaseId: '<DATABASE_ID>',
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageDatabase` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | Time range of the usage stats. |
| `collectionsTotal` | `number` | Total aggregated number of collections. |
| `tablesTotal` | `number` | Total aggregated number of tables. |
| `documentsTotal` | `number` | Total aggregated number of documents. |
| `rowsTotal` | `number` | Total aggregated number of rows. |
| `storageTotal` | `number` | Total aggregated number of total storage used in bytes. |
| `databaseReadsTotal` | `number` | Total number of databases reads. |
| `databaseWritesTotal` | `number` | Total number of databases writes. |
| `collections` | `object[]` | Aggregated  number of collections per period. |
| `tables` | `object[]` | Aggregated  number of tables per period. |
| `documents` | `object[]` | Aggregated  number of documents per period. |
| `rows` | `object[]` | Aggregated  number of rows per period. |
| `storage` | `object[]` | Aggregated storage used in bytes per period. |
| `databaseReads` | `object[]` | An array of aggregated number of database reads. |
| `databaseWrites` | `object[]` | An array of aggregated number of database writes. |
