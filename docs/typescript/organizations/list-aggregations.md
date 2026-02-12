# listAggregations

Description: Get a list of all aggregations for an organization.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `organizationId` | `string` | ✅ | Organization ID |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/databases#querying-documents). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: teamId, aggregationId, from, to (Default: `[]`) |

## Usage

```typescript
import { Client, Organizations, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const organizations = new Organizations(client);
const result: Models.AggregationTeamList = await organizations.listAggregations({
  organizationId: '<ORGANIZATION_ID>',
  queries: [],
});
```

## Response Model

Returns a `Models.AggregationTeamList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of aggregations that matched your query. |
| `aggregations` | `object[]` | List of aggregations. |
