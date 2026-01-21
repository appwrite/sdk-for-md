# listRepositories

Description: Get a list of GitHub repositories available through your installation. This endpoint returns repositories with their basic information, detected runtime environments, and latest push dates. You can optionally filter repositories using a search term. Each repository&#039;s runtime is automatically detected based on its contents and language statistics. The GitHub installation must be properly configured for this endpoint to work.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `installationId` | `string` | ✅ | Installation Id |
| `type` | `VCSDetectionType` | ✅ | Detector type. Must be one of the following: runtime, framework<br>**Allowed:** `runtime`, `framework` |
| `search` | `string` | ❌ | Search term to filter your list results. Max length: 256 chars. |
| `queries` | `string[]` | ❌ | Array of query strings generated using the Query class provided by the SDK. [Learn more about queries](https://appwrite.io/docs/queries). Only supported methods are limit and offset (Default: `[]`) |

## Usage

```typescript
import { Client, Vcs, VCSDetectionType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vcs = new Vcs(client);
const result: Models.ProviderRepositoryFrameworkList = await vcs.listRepositories({
  installationId: '<INSTALLATION_ID>',
  type: VCSDetectionType.Runtime,
  search: '<SEARCH>',
  queries: [],
});
```

## Response Model

Returns a `Models.ProviderRepositoryFrameworkList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of frameworkProviderRepositories that matched your query. |
| `frameworkProviderRepositories` | `object[]` | List of frameworkProviderRepositories. |
