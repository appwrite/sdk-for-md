# updatePlatform

Description: Update a platform by its unique ID. Use this endpoint to update the platform&#039;s name, key, platform store ID, or hostname.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `platformId` | `string` | ✅ | Platform unique ID. |
| `name` | `string` | ✅ | Platform name. Max length: 128 chars. |
| `key` | `string` | ❌ | Package name for android or bundle ID for iOS. Max length: 256 chars. |
| `store` | `string` | ❌ | App store or Google Play store ID. Max length: 256 chars. |
| `hostname` | `string` | ❌ | Platform client URL. Max length: 256 chars. |

## Usage

```typescript
import { Client, Projects, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Platform = await projects.updatePlatform({
  projectId: '<PROJECT_ID>',
  platformId: '<PLATFORM_ID>',
  name: '<NAME>',
  key: '<KEY>',
  store: '<STORE>',
  hostname: '',
});
```

## Response Model

Returns a `Models.Platform` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Platform ID. |
| `createdAt` | `string` | Platform creation date in ISO 8601 format. |
| `updatedAt` | `string` | Platform update date in ISO 8601 format. |
| `name` | `string` | Platform name. |
| `type` | `PlatformType` | Platform type. Possible values are: web, flutter-web, flutter-ios, flutter-android, flutter-linux, flutter-macos, flutter-windows, apple-ios, apple-macos, apple-watchos, apple-tvos, android, unity, react-native-ios, react-native-android. |
| `key` | `string` | Platform Key. iOS bundle ID or Android package name.  Empty string for other platforms. |
| `store` | `string` | App store or Google Play store ID. |
| `hostname` | `string` | Web app hostname. Empty string for other platforms. |
| `httpUser` | `string` | HTTP basic authentication username. |
| `httpPass` | `string` | HTTP basic authentication password. |
