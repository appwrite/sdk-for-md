# updateStatus

Description: Update the status of a project

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project ID |
| `status` | `Status` | ✅ | New status for the project<br>**Allowed:** `active`, `archived` |

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
