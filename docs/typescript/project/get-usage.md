# getUsage

Description: Get comprehensive usage statistics for your project. View metrics including network requests, bandwidth, storage, function executions, database usage, and user activity. Specify a time range with startDate and endDate, and optionally set the data granularity with period (1h or 1d). The response includes both total counts and detailed breakdowns by resource, along with historical data over the specified period.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `startDate` | `string` | ✅ | Starting date for the usage |
| `endDate` | `string` | ✅ | End date for the usage |
| `period` | `ProjectUsageRange` | ❌ | Period used (Default: `1d`)<br>**Allowed:** `1h`, `1d` |

## Usage

```typescript
import { Client, Project, ProjectUsageRange, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const project = new Project(client);
const result: Models.UsageProject = await project.getUsage({
  startDate: '',
  endDate: '',
  period: ProjectUsageRange.OneHour,
});
```

## Response Model

Returns a `Models.UsageProject` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `executionsTotal` | `number` | Total aggregated number of function executions. |
| `documentsTotal` | `number` | Total aggregated  number of documents in legacy/tablesdb. |
| `documentsdbDocumentsTotal` | `number` | Total aggregated  number of documents in documentsdb. |
| `rowsTotal` | `number` | Total aggregated  number of rows. |
| `databasesTotal` | `number` | Total aggregated number of databases. |
| `documentsdbTotal` | `number` | Total aggregated number of documentsdb. |
| `databasesStorageTotal` | `number` | Total aggregated sum of databases storage size (in bytes). |
| `documentsdbDatabasesStorageTotal` | `number` | Total aggregated sum of documentsdb databases storage size (in bytes). |
| `usersTotal` | `number` | Total aggregated number of users. |
| `filesStorageTotal` | `number` | Total aggregated sum of files storage size (in bytes). |
| `functionsStorageTotal` | `number` | Total aggregated sum of functions storage size (in bytes). |
| `buildsStorageTotal` | `number` | Total aggregated sum of builds storage size (in bytes). |
| `deploymentsStorageTotal` | `number` | Total aggregated sum of deployments storage size (in bytes). |
| `bucketsTotal` | `number` | Total aggregated number of buckets. |
| `executionsMbSecondsTotal` | `number` | Total aggregated number of function executions mbSeconds. |
| `buildsMbSecondsTotal` | `number` | Total aggregated number of function builds mbSeconds. |
| `databasesReadsTotal` | `number` | Aggregated stats for total databases reads. |
| `databasesWritesTotal` | `number` | Aggregated stats for total databases writes. |
| `documentsdbDatabasesReadsTotal` | `number` | Total number of documentsdb databases reads. |
| `documentsdbDatabasesWritesTotal` | `number` | Total number of documentsdb databases writes. |
| `requests` | `object[]` | Aggregated  number of requests per period. |
| `network` | `object[]` | Aggregated number of consumed bandwidth per period. |
| `users` | `object[]` | Aggregated number of users per period. |
| `executions` | `object[]` | Aggregated number of executions per period. |
| `executionsBreakdown` | `object[]` | Aggregated breakdown in totals of executions by functions. |
| `bucketsBreakdown` | `object[]` | Aggregated breakdown in totals of usage by buckets. |
| `databasesStorageBreakdown` | `object[]` | An array of the aggregated breakdown of storage usage by databases. |
| `executionsMbSecondsBreakdown` | `object[]` | Aggregated breakdown in totals of execution mbSeconds by functions. |
| `buildsMbSecondsBreakdown` | `object[]` | Aggregated breakdown in totals of build mbSeconds by functions. |
| `functionsStorageBreakdown` | `object[]` | Aggregated breakdown in totals of functions storage size (in bytes). |
| `authPhoneTotal` | `number` | Aggregated stats for total auth phone. |
| `authPhoneEstimate` | `number` | Aggregated stats for total auth phone estimation. |
| `authPhoneCountryBreakdown` | `object[]` | Aggregated breakdown in totals of phone auth by country. |
| `databasesReads` | `object[]` | Aggregated stats for database reads. |
| `databasesWrites` | `object[]` | Aggregated stats for database writes. |
| `documentsdbDatabasesReads` | `object[]` | An array of aggregated number of documentsdb database reads. |
| `documentsdbDatabasesWrites` | `object[]` | An array of aggregated number of documentsdb database writes. |
| `documentsdbDatabasesStorage` | `object[]` | An array of aggregated sum of documentsdb databases storage size (in bytes) per period. |
| `imageTransformations` | `object[]` | An array of aggregated number of image transformations. |
| `imageTransformationsTotal` | `number` | Total aggregated number of image transformations. |
| `vectorsdbDatabasesTotal` | `number` | Total aggregated number of VectorsDB databases. |
| `vectorsdbCollectionsTotal` | `number` | Total aggregated number of VectorsDB collections. |
| `vectorsdbDocumentsTotal` | `number` | Total aggregated number of VectorsDB documents. |
| `vectorsdbDatabasesStorageTotal` | `number` | Total aggregated VectorsDB storage (bytes). |
| `vectorsdbDatabasesReadsTotal` | `number` | Total aggregated number of VectorsDB reads. |
| `vectorsdbDatabasesWritesTotal` | `number` | Total aggregated number of VectorsDB writes. |
| `vectorsdbDatabases` | `object[]` | Aggregated VectorsDB databases per period. |
| `vectorsdbCollections` | `object[]` | Aggregated VectorsDB collections per period. |
| `vectorsdbDocuments` | `object[]` | Aggregated VectorsDB documents per period. |
| `vectorsdbDatabasesStorage` | `object[]` | Aggregated VectorsDB storage per period. |
| `vectorsdbDatabasesReads` | `object[]` | Aggregated VectorsDB reads per period. |
| `vectorsdbDatabasesWrites` | `object[]` | Aggregated VectorsDB writes per period. |
| `embeddingsText` | `object` | Aggregated number of text embedding calls per period. |
| `embeddingsTextTokens` | `object` | Aggregated number of tokens processed by text embeddings per period. |
| `embeddingsTextDuration` | `object` | Aggregated duration spent generating text embeddings per period. |
| `embeddingsTextErrors` | `object` | Aggregated number of errors while generating text embeddings per period. |
| `embeddingsTextTotal` | `object` | Total aggregated number of text embedding calls. |
| `embeddingsTextTokensTotal` | `object` | Total aggregated number of tokens processed by text. |
| `embeddingsTextDurationTotal` | `object` | Total aggregated duration spent generating text embeddings. |
| `embeddingsTextErrorsTotal` | `object` | Total aggregated number of errors while generating text embeddings. |
| `functionsExecutions` | `object[]` | Aggregated number of function executions per period. |
| `functionsExecutionsTotal` | `number` | Total aggregated number of function executions. |
| `sitesExecutions` | `object[]` | Aggregated number of site executions per period. |
| `sitesExecutionsTotal` | `number` | Total aggregated number of site executions. |
| `networkTotal` | `number` | Aggregated stats for total network bandwidth. |
| `backupsStorageTotal` | `number` | Aggregated stats for total backups storage. |
| `screenshotsGenerated` | `object[]` | An array of aggregated number of screenshots generated. |
| `screenshotsGeneratedTotal` | `number` | Total aggregated number of screenshots generated. |
| `imagineCredits` | `object[]` | An array of aggregated number of Imagine credits in the given period. |
| `imagineCreditsTotal` | `number` | Total aggregated number of Imagine credits. |
| `realtimeConnectionsTotal` | `number` | Current aggregated number of open Realtime connections. |
| `realtimeMessagesTotal` | `number` | Total number of Realtime messages sent to clients. |
| `realtimeBandwidthTotal` | `number` | Total consumed Realtime bandwidth (in bytes). |
| `realtimeConnections` | `object[]` | Aggregated number of open Realtime connections per period. |
| `realtimeMessages` | `object[]` | Aggregated number of Realtime messages sent to clients per period. |
| `realtimeBandwidth` | `object[]` | Aggregated consumed Realtime bandwidth (in bytes) per period. |
