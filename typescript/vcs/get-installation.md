# getInstallation

Description: Get a VCS installation by its unique ID. This endpoint returns the installation&#039;s details including its provider, organization, and configuration.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `installationId` | `string` | ✅ | Installation Id |

## Usage

```typescript
import { Client, Vcs, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vcs = new Vcs(client);
const result: Models.Installation = await vcs.getInstallation({
  installationId: '<INSTALLATION_ID>',
});
```

## Response Model

Returns a `Models.Installation` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Function ID. |
| `createdAt` | `string` | Function creation date in ISO 8601 format. |
| `updatedAt` | `string` | Function update date in ISO 8601 format. |
| `provider` | `string` | VCS (Version Control System) provider name. |
| `organization` | `string` | VCS (Version Control System) organization name. |
| `providerInstallationId` | `string` | VCS (Version Control System) installation ID. |
