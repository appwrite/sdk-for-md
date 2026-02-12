# update

Description: Update site by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site ID. |
| `name` | `string` | ✅ | Site name. Max length: 128 chars. |
| `framework` | `Framework` | ✅ | Sites framework.<br>**Allowed:** `analog`, `angular`, `nextjs`, `react`, `nuxt`, `vue`, `sveltekit`, `astro`, `tanstack-start`, `remix`, `lynx`, `flutter`, `react-native`, `vite`, `other` |
| `enabled` | `boolean` | ❌ | Is site enabled? When set to &#039;disabled&#039;, users cannot access the site but Server SDKs with and API key can still access the site. No data is lost when this is toggled. (Default: `1`) |
| `logging` | `boolean` | ❌ | When disabled, request logs will exclude logs and errors, and site responses will be slightly faster. (Default: `1`) |
| `timeout` | `number` | ❌ | Maximum request time in seconds. (Default: `30`) |
| `installCommand` | `string` | ❌ | Install Command. |
| `buildCommand` | `string` | ❌ | Build Command. |
| `outputDirectory` | `string` | ❌ | Output Directory for site. |
| `buildRuntime` | `BuildRuntime` | ❌ | Runtime to use during build step.<br>**Allowed:** `node-14.5`, `node-16.0`, `node-18.0`, `node-19.0`, `node-20.0`, `node-21.0`, `node-22`, `php-8.0`, `php-8.1`, `php-8.2`, `php-8.3`, `ruby-3.0`, `ruby-3.1`, `ruby-3.2`, `ruby-3.3`, `python-3.8`, `python-3.9`, `python-3.10`, `python-3.11`, `python-3.12`, `python-ml-3.11`, `python-ml-3.12`, `deno-1.21`, `deno-1.24`, `deno-1.35`, `deno-1.40`, `deno-1.46`, `deno-2.0`, `dart-2.15`, `dart-2.16`, `dart-2.17`, `dart-2.18`, `dart-2.19`, `dart-3.0`, `dart-3.1`, `dart-3.3`, `dart-3.5`, `dart-3.8`, `dart-3.9`, `dart-3.10`, `dotnet-6.0`, `dotnet-7.0`, `dotnet-8.0`, `java-8.0`, `java-11.0`, `java-17.0`, `java-18.0`, `java-21.0`, `java-22`, `swift-5.5`, `swift-5.8`, `swift-5.9`, `swift-5.10`, `kotlin-1.6`, `kotlin-1.8`, `kotlin-1.9`, `kotlin-2.0`, `cpp-17`, `cpp-20`, `bun-1.0`, `bun-1.1`, `go-1.23`, `static-1`, `flutter-3.24`, `flutter-3.27`, `flutter-3.29`, `flutter-3.32`, `flutter-3.35`, `flutter-3.38` |
| `adapter` | `Adapter` | ❌ | Framework adapter defining rendering strategy. Allowed values are: static, ssr<br>**Allowed:** `static`, `ssr` |
| `fallbackFile` | `string` | ❌ | Fallback file for single page application sites. |
| `installationId` | `string` | ❌ | Appwrite Installation ID for VCS (Version Control System) deployment. |
| `providerRepositoryId` | `string` | ❌ | Repository ID of the repo linked to the site. |
| `providerBranch` | `string` | ❌ | Production branch for the repo linked to the site. |
| `providerSilentMode` | `boolean` | ❌ | Is the VCS (Version Control System) connection in silent mode for the repo linked to the site? In silent mode, comments will not be made on commits and pull requests. |
| `providerRootDirectory` | `string` | ❌ | Path to site code in the linked repo. |
| `specification` | `string` | ❌ | Framework specification for the site and builds. (Default: `[]`) |

## Usage

```typescript
import { Client, Sites, Framework, BuildRuntime, Adapter, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.Site = await sites.update({
  siteId: '<SITE_ID>',
  name: '<NAME>',
  framework: Framework.Analog,
  enabled: false,
  logging: false,
  timeout: 1,
  installCommand: '<INSTALL_COMMAND>',
  buildCommand: '<BUILD_COMMAND>',
  outputDirectory: '<OUTPUT_DIRECTORY>',
  buildRuntime: BuildRuntime.Node145,
  adapter: Adapter.Static,
  fallbackFile: '<FALLBACK_FILE>',
  installationId: '<INSTALLATION_ID>',
  providerRepositoryId: '<PROVIDER_REPOSITORY_ID>',
  providerBranch: '<PROVIDER_BRANCH>',
  providerSilentMode: false,
  providerRootDirectory: '<PROVIDER_ROOT_DIRECTORY>',
  specification: '',
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
| `outputDirectory` | `string` | The directory where the site build output is located. |
| `installationId` | `string` | Site VCS (Version Control System) installation id. |
| `providerRepositoryId` | `string` | VCS (Version Control System) Repository ID |
| `providerBranch` | `string` | VCS (Version Control System) branch name |
| `providerRootDirectory` | `string` | Path to site in VCS (Version Control System) repository |
| `providerSilentMode` | `boolean` | Is VCS (Version Control System) connection is in silent mode? When in silence mode, no comments will be posted on the repository pull or merge requests |
| `specification` | `string` | Machine specification for builds and executions. |
| `buildRuntime` | `string` | Site build runtime. |
| `adapter` | `string` | Site framework adapter. |
| `fallbackFile` | `string` | Name of fallback file to use instead of 404 page. If null, Appwrite 404 page will be displayed. |
