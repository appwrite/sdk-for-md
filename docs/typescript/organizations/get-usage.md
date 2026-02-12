# getUsage

Description: Get the usage data for an organization.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |
| `startDate` | `string` | ❌ | Starting date for the usage |
| `endDate` | `string` | ❌ | End date for the usage |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.UsageOrganization = await organizations.getUsage({
  organizationId: '<ORGANIZATION_ID>',
  startDate: '',
  endDate: '',
});
```

## Response Model

Returns a `Models.UsageOrganization` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `bandwidth` | `object[]` | Aggregated stats for number of requests. |
| `users` | `object[]` | Aggregated stats for consumed bandwidth. |
| `executions` | `object[]` | Aggregated stats for function executions. |
| `databasesReads` | `object[]` | Aggregated stats for database reads. |
| `databasesWrites` | `object[]` | Aggregated stats for database writes. |
| `imageTransformations` | `object[]` | Aggregated stats for file transformations. |
| `imageTransformationsTotal` | `number` | Aggregated stats for total file transformations. |
| `screenshotsGenerated` | `object[]` | Aggregated stats for file transformations. |
| `screenshotsGeneratedTotal` | `number` | Aggregated stats for total file transformations. |
| `imagineCredits` | `object[]` | Aggregated stats for imagine credits. |
| `imagineCreditsTotal` | `number` | Aggregated stats for total imagine credits. |
| `usersTotal` | `number` | Aggregated stats for total users. |
| `executionsTotal` | `number` | Aggregated stats for total executions. |
| `executionsMBSecondsTotal` | `number` | Aggregated stats for function executions in mb seconds. |
| `buildsMBSecondsTotal` | `number` | Aggregated stats for function builds in mb seconds. |
| `filesStorageTotal` | `number` | Aggregated stats for total file storage. |
| `buildsStorageTotal` | `number` | Aggregated stats for total builds storage. |
| `deploymentsStorageTotal` | `number` | Aggregated stats for total deployments storage. |
| `databasesStorageTotal` | `number` | Aggregated stats for total databases storage. |
| `databasesReadsTotal` | `number` | Aggregated stats for total databases  reads. |
| `databasesWritesTotal` | `number` | Aggregated stats for total databases  writes. |
| `backupsStorageTotal` | `number` | Aggregated stats for total backups storage. |
| `storageTotal` | `number` | Aggregated stats for total storage. |
| `authPhoneTotal` | `number` | Aggregated stats for total auth phone. |
| `authPhoneEstimate` | `number` | Aggregated stats for total auth phone estimation. |
| `projects` | `object[]` | Aggregated stats for each projects. |
