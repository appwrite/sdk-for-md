# updateConsoleAccess

Description: Record console access to a project. This endpoint updates the last accessed timestamp for the project to track console activity.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project ID |

## Usage

```typescript
import { Client, Projects } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result = await projects.updateConsoleAccess({
  projectId: '<PROJECT_ID>',
});
```
