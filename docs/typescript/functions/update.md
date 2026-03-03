# update

Description: Update function by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function ID. |
| `name` | `string` | ✅ | Function name. Max length: 128 chars. |
| `runtime` | `Runtime` | ❌ | Execution runtime.<br>**Allowed:** `node-14.5`, `node-16.0`, `node-18.0`, `node-19.0`, `node-20.0`, `node-21.0`, `node-22`, `node-23`, `node-24`, `node-25`, `php-8.0`, `php-8.1`, `php-8.2`, `php-8.3`, `php-8.4`, `ruby-3.0`, `ruby-3.1`, `ruby-3.2`, `ruby-3.3`, `ruby-3.4`, `ruby-4.0`, `python-3.8`, `python-3.9`, `python-3.10`, `python-3.11`, `python-3.12`, `python-3.13`, `python-3.14`, `python-ml-3.11`, `python-ml-3.12`, `python-ml-3.13`, `deno-1.40`, `deno-1.46`, `deno-2.0`, `deno-2.5`, `deno-2.6`, `dart-2.15`, `dart-2.16`, `dart-2.17`, `dart-2.18`, `dart-2.19`, `dart-3.0`, `dart-3.1`, `dart-3.3`, `dart-3.5`, `dart-3.8`, `dart-3.9`, `dart-3.10`, `dotnet-6.0`, `dotnet-7.0`, `dotnet-8.0`, `dotnet-10`, `java-8.0`, `java-11.0`, `java-17.0`, `java-18.0`, `java-21.0`, `java-22`, `java-25`, `swift-5.5`, `swift-5.8`, `swift-5.9`, `swift-5.10`, `swift-6.2`, `kotlin-1.6`, `kotlin-1.8`, `kotlin-1.9`, `kotlin-2.0`, `kotlin-2.3`, `cpp-17`, `cpp-20`, `bun-1.0`, `bun-1.1`, `bun-1.2`, `bun-1.3`, `go-1.23`, `go-1.24`, `go-1.25`, `go-1.26`, `static-1`, `flutter-3.24`, `flutter-3.27`, `flutter-3.29`, `flutter-3.32`, `flutter-3.35`, `flutter-3.38` |
| `execute` | `string[]` | ❌ | An array of role strings with execution permissions. By default no user is granted with any execute permissions. [learn more about roles](https://appwrite.io/docs/permissions#permission-roles). Maximum of 100 roles are allowed, each 64 characters long. (Default: `[]`) |
| `events` | `string[]` | ❌ | Events list. Maximum of 100 events are allowed. (Default: `[]`) |
| `schedule` | `string` | ❌ | Schedule CRON syntax. |
| `timeout` | `number` | ❌ | Maximum execution time in seconds. (Default: `15`) |
| `enabled` | `boolean` | ❌ | Is function enabled? When set to &#039;disabled&#039;, users cannot access the function but Server SDKs with and API key can still access the function. No data is lost when this is toggled. (Default: `1`) |
| `logging` | `boolean` | ❌ | When disabled, executions will exclude logs and errors, and will be slightly faster. (Default: `1`) |
| `entrypoint` | `string` | ❌ | Entrypoint File. This path is relative to the &quot;providerRootDirectory&quot;. |
| `commands` | `string` | ❌ | Build Commands. |
| `scopes` | `Scopes` | ❌ | List of scopes allowed for API Key auto-generated for every execution. Maximum of 100 scopes are allowed. (Default: `[]`)<br>**Allowed:** `sessions.write`, `users.read`, `users.write`, `teams.read`, `teams.write`, `databases.read`, `databases.write`, `collections.read`, `collections.write`, `tables.read`, `tables.write`, `attributes.read`, `attributes.write`, `columns.read`, `columns.write`, `indexes.read`, `indexes.write`, `documents.read`, `documents.write`, `rows.read`, `rows.write`, `files.read`, `files.write`, `buckets.read`, `buckets.write`, `functions.read`, `functions.write`, `sites.read`, `sites.write`, `log.read`, `log.write`, `execution.read`, `execution.write`, `locale.read`, `avatars.read`, `health.read`, `providers.read`, `providers.write`, `messages.read`, `messages.write`, `topics.read`, `topics.write`, `subscribers.read`, `subscribers.write`, `targets.read`, `targets.write`, `rules.read`, `rules.write`, `schedules.read`, `schedules.write`, `migrations.read`, `migrations.write`, `vcs.read`, `vcs.write`, `assistant.read`, `tokens.read`, `tokens.write`, `policies.write`, `policies.read`, `archives.read`, `archives.write`, `restorations.read`, `restorations.write`, `domains.read`, `domains.write`, `events.read` |
| `installationId` | `string` | ❌ | Appwrite Installation ID for VCS (Version Controle System) deployment. |
| `providerRepositoryId` | `string` | ❌ | Repository ID of the repo linked to the function |
| `providerBranch` | `string` | ❌ | Production branch for the repo linked to the function |
| `providerSilentMode` | `boolean` | ❌ | Is the VCS (Version Control System) connection in silent mode for the repo linked to the function? In silent mode, comments will not be made on commits and pull requests. |
| `providerRootDirectory` | `string` | ❌ | Path to function code in the linked repo. |
| `specification` | `string` | ❌ | Runtime specification for the function and builds. (Default: `[]`) |

## Usage

```typescript
import { Client, Functions, Runtime, Scopes, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.Function = await functions.update({
  functionId: '<FUNCTION_ID>',
  name: '<NAME>',
  runtime: Runtime.Node145,
  execute: ["any"],
  events: [],
  schedule: '',
  timeout: 1,
  enabled: false,
  logging: false,
  entrypoint: '<ENTRYPOINT>',
  commands: '<COMMANDS>',
  scopes: Scopes.SessionsWrite,
  installationId: '<INSTALLATION_ID>',
  providerRepositoryId: '<PROVIDER_REPOSITORY_ID>',
  providerBranch: '<PROVIDER_BRANCH>',
  providerSilentMode: false,
  providerRootDirectory: '<PROVIDER_ROOT_DIRECTORY>',
  specification: '',
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
