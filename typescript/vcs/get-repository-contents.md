# getRepositoryContents

Description: Get a list of files and directories from a GitHub repository connected to your project. This endpoint returns the contents of a specified repository path, including file names, sizes, and whether each item is a file or directory. The GitHub installation must be properly configured and the repository must be accessible through your installation for this endpoint to work.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `installationId` | `string` | ✅ | Installation Id |
| `providerRepositoryId` | `string` | ✅ | Repository Id |
| `providerRootDirectory` | `string` | ❌ | Path to get contents of nested directory |
| `providerReference` | `string` | ❌ | Git reference (branch, tag, commit) to get contents from |

## Usage

```typescript
import { Client, Vcs, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vcs = new Vcs(client);
const result: Models.VcsContentList = await vcs.getRepositoryContents({
  installationId: '<INSTALLATION_ID>',
  providerRepositoryId: '<PROVIDER_REPOSITORY_ID>',
  providerRootDirectory: '<PROVIDER_ROOT_DIRECTORY>',
  providerReference: '<PROVIDER_REFERENCE>',
});
```

## Response Model

Returns a `Models.VcsContentList` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `total` | `number` | Total number of contents that matched your query. |
| `contents` | `object[]` | List of contents. |
