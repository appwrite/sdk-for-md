# updateStatus

Description: Update the status of a project. Can be used to archive/restore projects, and to restore paused projects. When restoring a paused project, the console fingerprint header must be provided and the project must not be blocked for any reason other than inactivity.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project ID |
| `status` | `Status` | ✅ | New status for the project<br>**Allowed:** `active` |

## Usage

```typescript
import { Client, Projects, Status } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result = await projects.updateStatus({
  projectId: '<PROJECT_ID>',
  status: Status.Active,
});
```
