# deletePlatform

Description: Delete a platform by its unique ID. This endpoint removes the platform and all its configurations from the project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `projectId` | `string` | ✅ | Project unique ID. |
| `platformId` | `string` | ✅ | Platform unique ID. |

## Usage

```typescript
import { Client, Projects } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const projects = new Projects(client);
const result = await projects.deletePlatform({
  projectId: '<PROJECT_ID>',
  platformId: '<PLATFORM_ID>',
});
```
