# create

Description: Create a new site.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `name` | `string` | ✅ | Site name. Max length: 128 chars. |
| `framework` | `Framework` | ✅ | Sites framework.<br>**Allowed:** `analog`, `angular`, `nextjs`, `react`, `nuxt`, `vue`, `sveltekit`, `astro`, `tanstack-start`, `remix`, `lynx`, `flutter`, `react-native`, `vite`, `other` |
| `buildRuntime` | `BuildRuntime` | ✅ | Runtime to use during build step.<br>**Allowed:** `node-14.5`, `node-16.0`, `node-18.0`, `node-19.0`, `node-20.0`, `node-21.0`, `node-22`, `node-23`, `node-24`, `node-25`, `php-8.0`, `php-8.1`, `php-8.2`, `php-8.3`, `php-8.4`, `ruby-3.0`, `ruby-3.1`, `ruby-3.2`, `ruby-3.3`, `ruby-3.4`, `ruby-4.0`, `python-3.8`, `python-3.9`, `python-3.10`, `python-3.11`, `python-3.12`, `python-3.13`, `python-3.14`, `python-ml-3.11`, `python-ml-3.12`, `python-ml-3.13`, `deno-1.40`, `deno-1.46`, `deno-2.0`, `deno-2.5`, `deno-2.6`, `dart-2.15`, `dart-2.16`, `dart-2.17`, `dart-2.18`, `dart-2.19`, `dart-3.0`, `dart-3.1`, `dart-3.3`, `dart-3.5`, `dart-3.8`, `dart-3.9`, `dart-3.10`, `dotnet-6.0`, `dotnet-7.0`, `dotnet-8.0`, `dotnet-10`, `java-8.0`, `java-11.0`, `java-17.0`, `java-18.0`, `java-21.0`, `java-22`, `java-25`, `swift-5.5`, `swift-5.8`, `swift-5.9`, `swift-5.10`, `swift-6.2`, `kotlin-1.6`, `kotlin-1.8`, `kotlin-1.9`, `kotlin-2.0`, `kotlin-2.3`, `cpp-17`, `cpp-20`, `bun-1.0`, `bun-1.1`, `bun-1.2`, `bun-1.3`, `go-1.23`, `go-1.24`, `go-1.25`, `go-1.26`, `static-1`, `flutter-3.24`, `flutter-3.27`, `flutter-3.29`, `flutter-3.32`, `flutter-3.35`, `flutter-3.38` |
| `enabled` | `boolean` | ❌ | Is site enabled? When set to &#039;disabled&#039;, users cannot access the site but Server SDKs with and API key can still access the site. No data is lost when this is toggled. (Default: `1`) |
| `logging` | `boolean` | ❌ | When disabled, request logs will exclude logs and errors, and site responses will be slightly faster. (Default: `1`) |
| `timeout` | `number` | ❌ | Maximum request time in seconds. (Default: `30`) |
| `installCommand` | `string` | ❌ | Install Command. |
| `buildCommand` | `string` | ❌ | Build Command. |
| `startCommand` | `string` | ❌ | Custom start command. Leave empty to use default. |
| `outputDirectory` | `string` | ❌ | Output Directory for site. |
| `adapter` | `Adapter` | ❌ | Framework adapter defining rendering strategy. Allowed values are: static, ssr<br>**Allowed:** `static`, `ssr` |
| `installationId` | `string` | ❌ | Appwrite Installation ID for VCS (Version Control System) deployment. |
| `fallbackFile` | `string` | ❌ | Fallback file for single page application sites. |
| `providerRepositoryId` | `string` | ❌ | Repository ID of the repo linked to the site. |
| `providerBranch` | `string` | ❌ | Production branch for the repo linked to the site. |
| `providerSilentMode` | `boolean` | ❌ | Is the VCS (Version Control System) connection in silent mode for the repo linked to the site? In silent mode, comments will not be made on commits and pull requests. |
| `providerRootDirectory` | `string` | ❌ | Path to site code in the linked repo. |
| `buildSpecification` | `string` | ❌ | Build specification for the site deployments. (Default: `[]`) |
| `runtimeSpecification` | `string` | ❌ | Runtime specification for the SSR executions. (Default: `[]`) |
| `deploymentRetention` | `number` | ❌ | Days to keep non-active deployments before deletion. Value 0 means all deployments will be kept. |

## Usage

```typescript
import { Client, Sites, Framework, BuildRuntime, Adapter, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.Site = await sites.create({
  siteId: '<SITE_ID>',
  name: '<NAME>',
  framework: Framework.Analog,
  buildRuntime: BuildRuntime.Node145,
  enabled: false,
  logging: false,
  timeout: 1,
  installCommand: '<INSTALL_COMMAND>',
  buildCommand: '<BUILD_COMMAND>',
  startCommand: '<START_COMMAND>',
  outputDirectory: '<OUTPUT_DIRECTORY>',
  adapter: Adapter.Static,
  installationId: '<INSTALLATION_ID>',
  fallbackFile: '<FALLBACK_FILE>',
  providerRepositoryId: '<PROVIDER_REPOSITORY_ID>',
  providerBranch: '<PROVIDER_BRANCH>',
  providerSilentMode: false,
  providerRootDirectory: '<PROVIDER_ROOT_DIRECTORY>',
  buildSpecification: '',
  runtimeSpecification: '',
  deploymentRetention: 0,
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
