# getUsage

Description: 

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `databaseId` | `string` | ✅ | Database ID. |
| `range` | `UsageRange` | ❌ | Date range. (Default: `30d`)<br>**Allowed:** `24h`, `30d`, `90d` |

## Usage

```typescript
import { Client, VectorsDB, UsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vectorsDB = new VectorsDB(client);
const result: Models.UsageVectorsDB = await vectorsDB.getUsage({
  databaseId: '<DATABASE_ID>',
  range: UsageRange.TwentyFourHours,
});
```

## Response Model

Returns a `Models.UsageVectorsDB` object with the following properties:

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
