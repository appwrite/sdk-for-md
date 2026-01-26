# createDeployment

Description: Create a new site code deployment. Use this endpoint to upload a new version of your site code. To activate your newly uploaded code, you&#039;ll need to update the site&#039;s deployment to use your new deployment ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site ID. |
| `code` | `File` | ✅ | Gzip file with your code package. When used with the Appwrite CLI, pass the path to your code directory, and the CLI will automatically package your code. Use a path that is within the current directory. |
| `activate` | `boolean` | ✅ | Automatically activate the deployment when it is finished building. |
| `installCommand` | `string` | ❌ | Install Commands. |
| `buildCommand` | `string` | ❌ | Build Commands. |
| `outputDirectory` | `string` | ❌ | Output Directory. |

## Usage

```typescript
import { Client, Sites, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.Deployment = await sites.createDeployment({
  siteId: '<SITE_ID>',
  code: file,
  activate: false,
  installCommand: '<INSTALL_COMMAND>',
  buildCommand: '<BUILD_COMMAND>',
  outputDirectory: '<OUTPUT_DIRECTORY>',
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
| `status` | `DeploymentStatus` | The deployment status. Possible values are &quot;waiting&quot;, &quot;processing&quot;, &quot;building&quot;, &quot;ready&quot;, and &quot;failed&quot;. |
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
