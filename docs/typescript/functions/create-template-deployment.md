# createTemplateDeployment

Description: Create a deployment based on a template.

Use this endpoint with combination of [listTemplates](https://appwrite.io/docs/products/functions/templates) to find the template details.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function ID. |
| `repository` | `string` | ✅ | Repository name of the template. |
| `owner` | `string` | ✅ | The name of the owner of the template. |
| `rootDirectory` | `string` | ✅ | Path to function code in the template repo. |
| `type` | `TemplateReferenceType` | ✅ | Type for the reference provided. Can be commit, branch, or tag<br>**Allowed:** `commit`, `branch`, `tag` |
| `reference` | `string` | ✅ | Reference value, can be a commit hash, branch name, or release tag |
| `activate` | `boolean` | ❌ | Automatically activate the deployment when it is finished building. |

## Usage

```typescript
import { Client, Functions, TemplateReferenceType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.Deployment = await functions.createTemplateDeployment({
  functionId: '<FUNCTION_ID>',
  repository: '<REPOSITORY>',
  owner: '<OWNER>',
  rootDirectory: '<ROOT_DIRECTORY>',
  type: TemplateReferenceType.Commit,
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
