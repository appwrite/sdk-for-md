# getRepository

Description: Get detailed information about a specific GitHub repository from your installation. This endpoint returns repository details including its ID, name, visibility status, organization, and latest push date. The GitHub installation must be properly configured and have access to the requested repository for this endpoint to work.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `installationId` | `string` | ✅ | Installation Id |
| `providerRepositoryId` | `string` | ✅ | Repository Id |

## Usage

```typescript
import { Client, Vcs, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vcs = new Vcs(client);
const result: Models.ProviderRepository = await vcs.getRepository({
  installationId: '<INSTALLATION_ID>',
  providerRepositoryId: '<PROVIDER_REPOSITORY_ID>',
});
```

## Response Model

Returns a `Models.ProviderRepository` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | VCS (Version Control System) repository ID. |
| `name` | `string` | VCS (Version Control System) repository name. |
| `organization` | `string` | VCS (Version Control System) organization name |
| `provider` | `string` | VCS (Version Control System) provider name. |
| `private` | `boolean` | Is VCS (Version Control System) repository private? |
| `defaultBranch` | `string` | VCS (Version Control System) repository&#039;s default branch name. |
| `pushedAt` | `string` | Last commit date in ISO 8601 format. |
| `variables` | `string[]` | Environment variables found in .env files |
