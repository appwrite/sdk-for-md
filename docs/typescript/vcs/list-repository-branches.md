# listRepositoryBranches

Description: Get a list of all branches from a GitHub repository in your installation. This endpoint returns the names of all branches in the repository and their total count. The GitHub installation must be properly configured and have access to the requested repository for this endpoint to work.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `installationId` | `string` | ✅ | Installation Id |
| `providerRepositoryId` | `string` | ✅ | Repository Id |

## Usage

```typescript
import { Client, Vcs, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vcs = new Vcs(client);
const result: Models.BranchList = await vcs.listRepositoryBranches({
  installationId: '<INSTALLATION_ID>',
  providerRepositoryId: '<PROVIDER_REPOSITORY_ID>',
});
```

## Response Model

Returns a `Models.BranchList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of branches that matched your query. |
| `branches` | `object[]` | List of branches. |
