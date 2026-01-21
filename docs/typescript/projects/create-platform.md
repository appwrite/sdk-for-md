# createPlatform

Description: Create a new platform for your project. Use this endpoint to register a new platform where your users will run your application which will interact with the Appwrite API.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `type` | `PlatformType` | ✅ | Platform type. Possible values are: web, flutter-web, flutter-ios, flutter-android, flutter-linux, flutter-macos, flutter-windows, apple-ios, apple-macos, apple-watchos, apple-tvos, android, unity, react-native-ios, react-native-android.<br>**Allowed:** `web`, `flutter-web`, `flutter-ios`, `flutter-android`, `flutter-linux`, `flutter-macos`, `flutter-windows`, `apple-ios`, `apple-macos`, `apple-watchos`, `apple-tvos`, `android`, `unity`, `react-native-ios`, `react-native-android` |
| `name` | `string` | ✅ | Platform name. Max length: 128 chars. |
| `key` | `string` | ❌ | Package name for Android or bundle ID for iOS or macOS. Max length: 256 chars. |
| `store` | `string` | ❌ | App store or Google Play store ID. Max length: 256 chars. |
| `hostname` | `string` | ❌ | Platform client hostname. Max length: 256 chars. |

## Usage

```typescript
import { Client, Projects, PlatformType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result: Models.Platform = await projects.createPlatform({
  projectId: '<PROJECT_ID>',
  type: PlatformType.Web,
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
