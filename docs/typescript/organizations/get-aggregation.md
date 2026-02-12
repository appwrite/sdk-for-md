# getAggregation

Description: Get a specific aggregation using it&#039;s aggregation ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |
| `aggregationId` | `string` | ✅ | Invoice unique ID |
| `limit` | `number` | ❌ | Maximum number of project aggregations to return in response. By default will return maximum 5 results. Maximum of 10 results allowed per request. (Default: `5`) |
| `offset` | `number` | ❌ | Offset value. The default value is 0. Use this param to manage pagination. |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.AggregationTeam = await organizations.getAggregation({
  organizationId: '<ORGANIZATION_ID>',
  aggregationId: '<AGGREGATION_ID>',
  limit: 0,
  offset: 0,
});
```

## Response Model

Returns a `Models.AggregationTeam` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Aggregation ID. |
| `createdAt` | `string` | Aggregation creation time in ISO 8601 format. |
| `updatedAt` | `string` | Aggregation update date in ISO 8601 format. |
| `permissions` | `string[]` | Aggregation permissions. [Learn more about permissions](/docs/permissions). |
| `from` | `string` | Beginning date of the invoice |
| `to` | `string` | End date of the invoice |
| `usageStorage` | `number` | Total storage usage |
| `usageTotalStorage` | `number` | Total storage usage with builds storage |
| `usageFilesStorage` | `number` | Total files storage usage |
| `usageDeploymentsStorage` | `number` | Total deployments storage usage |
| `usageBuildsStorage` | `number` | Total builds storage usage |
| `usageDatabasesStorage` | `number` | Total databases storage usage |
| `usageUsers` | `number` | Total active users for the billing period |
| `usageExecutions` | `number` | Total number of executions for the billing period |
| `usageBandwidth` | `number` | Total bandwidth usage for the billing period |
| `usageRealtime` | `number` | Total realtime usage for the billing period |
| `additionalMembers` | `number` | Additional members |
| `additionalMemberAmount` | `number` | Additional members cost |
| `additionalStorageAmount` | `number` | Additional storage usage cost |
| `additionalUsersAmount` | `number` | Additional users usage cost. |
| `additionalExecutionsAmount` | `number` | Additional executions usage cost |
| `additionalBandwidthAmount` | `number` | Additional bandwidth usage cost |
| `additionalRealtimeAmount` | `number` | Additional realtime usage cost |
| `plan` | `string` | Billing plan |
| `amount` | `number` | Aggregated amount |
| `breakdown` | `object[]` | Aggregation project breakdown |
| `resources` | `object[]` | Usage resources |
