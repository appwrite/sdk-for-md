# createDeployment

Description: Create a new function code deployment. Use this endpoint to upload a new version of your code function. To execute your newly uploaded code, you&#039;ll need to update the function&#039;s deployment to use your new deployment UID.

This endpoint accepts a tar.gz file compressed with your code. Make sure to include any dependencies your code has within the compressed file. You can learn more about code packaging in the [Appwrite Cloud Functions tutorial](https://appwrite.io/docs/functions).

Use the &quot;command&quot; param to set the entrypoint used to execute your code.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function ID. |
| `code` | `File` | ✅ | Gzip file with your code package. When used with the Appwrite CLI, pass the path to your code directory, and the CLI will automatically package your code. Use a path that is within the current directory. |
| `activate` | `boolean` | ✅ | Automatically activate the deployment when it is finished building. |
| `entrypoint` | `string` | ❌ | Entrypoint File. |
| `commands` | `string` | ❌ | Build Commands. |

## Usage

```typescript
import { Client, Functions, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.Deployment = await functions.createDeployment({
  functionId: '<FUNCTION_ID>',
  code: file,
  activate: false,
  entrypoint: '<ENTRYPOINT>',
  commands: '<COMMANDS>',
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
