# updateExternalDeployments

Description: Authorize and create deployments for a GitHub pull request in your project. This endpoint allows external contributions by creating deployments from pull requests, enabling preview environments for code review. The pull request must be open and not previously authorized. The GitHub installation must be properly configured and have access to both the repository and pull request for this endpoint to work.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `installationId` | `string` | ✅ | Installation Id |
| `repositoryId` | `string` | ✅ | VCS Repository Id |
| `providerPullRequestId` | `string` | ✅ | GitHub Pull Request Id |

## Usage

```typescript
import { Client, Vcs } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vcs = new Vcs(client);
const result = await vcs.updateExternalDeployments({
  installationId: '<INSTALLATION_ID>',
  repositoryId: '<REPOSITORY_ID>',
  providerPullRequestId: '<PROVIDER_PULL_REQUEST_ID>',
});
```
