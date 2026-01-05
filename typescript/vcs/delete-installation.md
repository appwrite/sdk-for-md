# deleteInstallation

Description: Delete a VCS installation by its unique ID. This endpoint removes the installation and all its associated repositories from the project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `installationId` | `string` | ✅ | Installation Id |

## Usage

```typescript
import { Client, Vcs } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const vcs = new Vcs(client);
const result = await vcs.deleteInstallation({
  installationId: '<INSTALLATION_ID>',
});
```
