# listUsage

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, VectorsDB, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result: Models.UsageVectorsDBs = await vectorsDB.listUsage({
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageVectorsDBs` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `range` | `string` | Time range of the usage stats. |
| `databasesTotal` | `number` | Total aggregated number of VectorsDB databases. |
| `collectionsTotal` | `number` | Total aggregated number of collections. |
| `documentsTotal` | `number` | Total aggregated number of documents. |
| `storageTotal` | `number` | Total aggregated storage in bytes. |
| `databasesReadsTotal` | `number` | Total number of database reads. |
| `databasesWritesTotal` | `number` | Total number of database writes. |
| `databases` | `object[]` | Aggregated number of databases per period. |
| `collections` | `object[]` | Aggregated number of collections per period. |
| `documents` | `object[]` | Aggregated number of documents per period. |
| `storage` | `object[]` | Aggregated storage in bytes per period. |
| `databasesReads` | `object[]` | An array of aggregated number of database reads. |
| `databasesWrites` | `object[]` | An array of aggregated number of database writes. |
