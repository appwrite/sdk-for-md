# listInstallations

Description: List all VCS installations configured for the current project. This endpoint returns a list of installations including their provider, organization, and other configuration details.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Maximum of 100 queries are allowed, each 4096 characters long. You may filter on the following attributes: provider, organization (Default: `[]`) |
| `search` | `string` | ❌ | Search term to filter your list results. Max length: 256 chars. |
| `total` | `boolean` | ❌ | When set to false, the total count returned will be 0 and will not be calculated. (Default: `1`) |

## Usage

```typescript
import { Client, Vcs, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vcs = new Vcs(client);
const result: Models.InstallationList = await vcs.listInstallations({
  queries: [],
  search: '<SEARCH>',
  total: false,
});
```

## Response Model

Returns a `Models.InstallationList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of installations that matched your query. |
| `installations` | `object[]` | List of installations. |
