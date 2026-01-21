# listUsage

Description: List usage metrics and statistics for all databases in the project. You can view the total number of databases, tables, rows, and storage usage. The response includes both current totals and historical data over time. Use the optional range parameter to specify the time window for historical data: 24h (last 24 hours), 30d (last 30 days), or 90d (last 90 days). If not specified, range defaults to 30 days.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, TablesDB, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const tablesDB = new TablesDB(client);
const result: Models.UsageDatabases = await tablesDB.listUsage({
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageDatabases` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | Time range of the usage stats. |
| `databasesTotal` | `number` | Total aggregated number of databases. |
| `collectionsTotal` | `number` | Total aggregated number  of collections. |
| `tablesTotal` | `number` | Total aggregated number  of tables. |
| `documentsTotal` | `number` | Total aggregated number of documents. |
| `rowsTotal` | `number` | Total aggregated number of rows. |
| `storageTotal` | `number` | Total aggregated number of total databases storage in bytes. |
| `databasesReadsTotal` | `number` | Total number of databases reads. |
| `databasesWritesTotal` | `number` | Total number of databases writes. |
| `databases` | `object[]` | Aggregated number of databases per period. |
| `collections` | `object[]` | Aggregated number of collections per period. |
| `tables` | `object[]` | Aggregated number of tables per period. |
| `documents` | `object[]` | Aggregated number of documents per period. |
| `rows` | `object[]` | Aggregated number of rows per period. |
| `storage` | `object[]` | An array of the aggregated number of databases storage in bytes per period. |
| `databasesReads` | `object[]` | An array of aggregated number of database reads. |
| `databasesWrites` | `object[]` | An array of aggregated number of database writes. |
