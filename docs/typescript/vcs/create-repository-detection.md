# createRepositoryDetection

Description: Analyze a GitHub repository to automatically detect the programming language and runtime environment. This endpoint scans the repository&#039;s files and language statistics to determine the appropriate runtime settings for your function. The GitHub installation must be properly configured and the repository must be accessible through your installation for this endpoint to work.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `installationId` | `string` | ✅ | Installation Id |
| `providerRepositoryId` | `string` | ✅ | Repository Id |
| `type` | `VCSDetectionType` | ✅ | Detector type. Must be one of the following: runtime, framework<br>**Allowed:** `runtime`, `framework` |
| `providerRootDirectory` | `string` | ❌ | Path to Root Directory |

## Usage

```typescript
import { Client, Vcs, VCSDetectionType, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vcs = new Vcs(client);
const result: Models.DetectionFramework = await vcs.createRepositoryDetection({
  installationId: '<INSTALLATION_ID>',
  providerRepositoryId: '<PROVIDER_REPOSITORY_ID>',
  type: VCSDetectionType.Runtime,
  providerRootDirectory: '<PROVIDER_ROOT_DIRECTORY>',
});
```

## Response Model

Returns a `Models.DetectionFramework` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `variables` | `object[]` | Environment variables found in .env files |
| `framework` | `string` | Framework |
| `installCommand` | `string` | Site Install Command |
| `buildCommand` | `string` | Site Build Command |
| `outputDirectory` | `string` | Site Output Directory |
