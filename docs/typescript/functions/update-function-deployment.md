# updateFunctionDeployment

Description: Update the function active deployment. Use this endpoint to switch the code deployment that should be used when visitor opens your function.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function ID. |
| `deploymentId` | `string` | ✅ | Deployment ID. |

## Usage

```typescript
import { Client, Functions, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.Function = await functions.updateFunctionDeployment({
  functionId: '<FUNCTION_ID>',
  deploymentId: '<DEPLOYMENT_ID>',
});
```

## Response Model

Returns a `Models.Function` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Function ID. |
| `createdAt` | `string` | Function creation date in ISO 8601 format. |
| `updatedAt` | `string` | Function update date in ISO 8601 format. |
| `execute` | `string[]` | Execution permissions. |
| `name` | `string` | Function name. |
| `enabled` | `boolean` | Function enabled. |
| `live` | `boolean` | Is the function deployed with the latest configuration? This is set to false if you&#039;ve changed an environment variables, entrypoint, commands, or other settings that needs redeploy to be applied. When the value is false, redeploy the function to update it with the latest configuration. |
| `logging` | `boolean` | When disabled, executions will exclude logs and errors, and will be slightly faster. |
| `runtime` | `string` | Function execution and build runtime. |
| `deploymentId` | `string` | Function&#039;s active deployment ID. |
| `deploymentCreatedAt` | `string` | Active deployment creation date in ISO 8601 format. |
| `latestDeploymentId` | `string` | Function&#039;s latest deployment ID. |
| `latestDeploymentCreatedAt` | `string` | Latest deployment creation date in ISO 8601 format. |
| `latestDeploymentStatus` | `string` | Status of latest deployment. Possible values are &quot;waiting&quot;, &quot;processing&quot;, &quot;building&quot;, &quot;ready&quot;, and &quot;failed&quot;. |
| `scopes` | `string[]` | Allowed permission scopes. |
| `vars` | `object[]` | Function variables. |
| `events` | `string[]` | Function trigger events. |
| `schedule` | `string` | Function execution schedule in CRON format. |
| `timeout` | `number` | Function execution timeout in seconds. |
| `entrypoint` | `string` | The entrypoint file used to execute the deployment. |
| `commands` | `string` | The build command used to build the deployment. |
| `version` | `string` | Version of Open Runtimes used for the function. |
| `installationId` | `string` | Function VCS (Version Control System) installation id. |
| `providerRepositoryId` | `string` | VCS (Version Control System) Repository ID |
| `providerBranch` | `string` | VCS (Version Control System) branch name |
| `providerRootDirectory` | `string` | Path to function in VCS (Version Control System) repository |
| `providerSilentMode` | `boolean` | Is VCS (Version Control System) connection is in silent mode? When in silence mode, no comments will be posted on the repository pull or merge requests |
| `specification` | `string` | Machine specification for builds and executions. |
