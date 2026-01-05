# listDeployments

Description: Get a list of all the site&#039;s code deployments. You can use the query params to filter your results.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site ID. |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: buildSize, sourceSize, totalSize, buildDuration, status, activate, type (Default: `[]`) |
| `search` | `string` | ❌ | Search term to filter your list results. Max length: 256 chars. |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Sites, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.DeploymentList = await sites.listDeployments({
  siteId: '<SITE_ID>',
  queries: [],
  search: '<SEARCH>',
  total: false,
});
```

## Response Model

Returns a `Models.DeploymentList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of deployments that matched your query. |
| `deployments` | `object[]` | List of deployments. |
