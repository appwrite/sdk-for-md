# get

Description: Get a site by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site ID. |

## Usage

```typescript
import { Client, Sites, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.Site = await sites.get({
  siteId: '<SITE_ID>',
});
```

## Response Model

Returns a `Models.Site` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Site ID. |
| `createdAt` | `string` | Site creation date in ISO 8601 format. |
| `updatedAt` | `string` | Site update date in ISO 8601 format. |
| `name` | `string` | Site name. |
| `enabled` | `boolean` | Site enabled. |
| `live` | `boolean` | Is the site deployed with the latest configuration? This is set to false if you&#039;ve changed an environment variables, entrypoint, commands, or other settings that needs redeploy to be applied. When the value is false, redeploy the site to update it with the latest configuration. |
| `logging` | `boolean` | When disabled, request logs will exclude logs and errors, and site responses will be slightly faster. |
| `framework` | `string` | Site framework. |
| `deploymentRetention` | `number` | How many days to keep the non-active deployments before they will be automatically deleted. |
| `deploymentId` | `string` | Site&#039;s active deployment ID. |
| `deploymentCreatedAt` | `string` | Active deployment creation date in ISO 8601 format. |
| `deploymentScreenshotLight` | `string` | Screenshot of active deployment with light theme preference file ID. |
| `deploymentScreenshotDark` | `string` | Screenshot of active deployment with dark theme preference file ID. |
| `latestDeploymentId` | `string` | Site&#039;s latest deployment ID. |
| `latestDeploymentCreatedAt` | `string` | Latest deployment creation date in ISO 8601 format. |
| `latestDeploymentStatus` | `string` | Status of latest deployment. Possible values are &quot;waiting&quot;, &quot;processing&quot;, &quot;building&quot;, &quot;ready&quot;, and &quot;failed&quot;. |
| `vars` | `object[]` | Site variables. |
| `timeout` | `number` | Site request timeout in seconds. |
| `installCommand` | `string` | The install command used to install the site dependencies. |
| `buildCommand` | `string` | The build command used to build the site. |
| `startCommand` | `string` | Custom command to use when starting site runtime. |
| `outputDirectory` | `string` | The directory where the site build output is located. |
| `installationId` | `string` | Site VCS (Version Control System) installation id. |
| `providerRepositoryId` | `string` | VCS (Version Control System) Repository ID |
| `providerBranch` | `string` | VCS (Version Control System) branch name |
| `providerRootDirectory` | `string` | Path to site in VCS (Version Control System) repository |
| `providerSilentMode` | `boolean` | Is VCS (Version Control System) connection is in silent mode? When in silence mode, no comments will be posted on the repository pull or merge requests |
| `buildSpecification` | `string` | Machine specification for deployment builds. |
| `runtimeSpecification` | `string` | Machine specification for SSR executions. |
| `buildRuntime` | `string` | Site build runtime. |
| `adapter` | `string` | Site framework adapter. |
| `fallbackFile` | `string` | Name of fallback file to use instead of 404 page. If null, Appwrite 404 page will be displayed. |
