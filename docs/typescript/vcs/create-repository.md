# createRepository

Description: Create a new GitHub repository through your installation. This endpoint allows you to create either a public or private repository by specifying a name and visibility setting. The repository will be created under your GitHub user account or organization, depending on your installation type. The GitHub installation must be properly configured and have the necessary permissions for repository creation.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `installationId` | `string` | ✅ | Installation Id |
| `name` | `string` | ✅ | Repository name (slug) |
| `private` | `boolean` | ✅ | Mark repository public or private |

## Usage

```typescript
import { Client, Vcs, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vcs = new Vcs(client);
const result: Models.ProviderRepository = await vcs.createRepository({
  installationId: '<INSTALLATION_ID>',
  name: '<NAME>',
  private: false,
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
