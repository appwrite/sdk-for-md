# deleteVariable

Description: Delete a variable by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `variableId` | `string` | ✅ | Variable ID. |

## Usage

```typescript
import { Client, Project } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const project = new Project(client);
const result = await project.deleteVariable({
  variableId: '<VARIABLE_ID>',
});
```
