# createVcsDeployment

Description: Create a deployment when a function is connected to VCS.

This endpoint lets you create deployment from a branch, commit, or a tag.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function ID. |
| `type` | `VCSReferenceType` | ✅ | Type of reference passed. Allowed values are: branch, commit<br>**Allowed:** `branch`, `commit` |
| `reference` | `string` | ✅ | VCS reference to create deployment from. Depending on type this can be: branch name, commit hash |
| `activate` | `boolean` | ❌ | Automatically activate the deployment when it is finished building. |

## Usage

```typescript
import { Client, Functions, VCSReferenceType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.Deployment = await functions.createVcsDeployment({
  functionId: '<FUNCTION_ID>',
  type: VCSReferenceType.Branch,
  reference: '<REFERENCE>',
  activate: false,
});
```

## Response Model

Returns a `Models.Deployment` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Deployment ID. |
| `createdAt` | `string` | Deployment creation date in ISO 8601 format. |
| `updatedAt` | `string` | Deployment update date in ISO 8601 format. |
| `type` | `string` | Type of deployment. |
| `resourceId` | `string` | Resource ID. |
| `resourceType` | `string` | Resource type. |
| `entrypoint` | `string` | The entrypoint file to use to execute the deployment code. |
| `sourceSize` | `number` | The code size in bytes. |
| `buildSize` | `number` | The build output size in bytes. |
| `totalSize` | `number` | The total size in bytes (source and build output). |
| `buildId` | `string` | The current build ID. |
| `activate` | `boolean` | Whether the deployment should be automatically activated. |
| `screenshotLight` | `string` | Screenshot with light theme preference file ID. |
| `screenshotDark` | `string` | Screenshot with dark theme preference file ID. |
| `status` | `DeploymentStatus` | The deployment status. Possible values are &quot;waiting&quot;, &quot;processing&quot;, &quot;building&quot;, &quot;ready&quot;, &quot;canceled&quot; and &quot;failed&quot;. |
| `buildLogs` | `string` | The build logs. |
| `buildDuration` | `number` | The current build time in seconds. |
| `providerRepositoryName` | `string` | The name of the vcs provider repository |
| `providerRepositoryOwner` | `string` | The name of the vcs provider repository owner |
| `providerRepositoryUrl` | `string` | The url of the vcs provider repository |
| `providerCommitHash` | `string` | The commit hash of the vcs commit |
| `providerCommitAuthorUrl` | `string` | The url of vcs commit author |
| `providerCommitAuthor` | `string` | The name of vcs commit author |
| `providerCommitMessage` | `string` | The commit message |
| `providerCommitUrl` | `string` | The url of the vcs commit |
| `providerBranch` | `string` | The branch of the vcs repository |
| `providerBranchUrl` | `string` | The branch of the vcs repository |
