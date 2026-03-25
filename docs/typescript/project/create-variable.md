# createVariable

Description: Create a new project environment variable. These variables can be accessed by all functions and sites in the project.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `variableId` | `string` | ✅ | Variable ID. Choose a custom ID or generate a random ID with `ID.unique()`. Valid chars are a-z, A-Z, 0-9, period, hyphen, and underscore. Can&#039;t start with a special char. Max length is 36 chars. |
| `key` | `string` | ✅ | Variable key. Max length: 255 chars. |
| `value` | `string` | ✅ | Variable value. Max length: 8192 chars. |
| `secret` | `boolean` | ❌ | Secret variables can be updated or deleted, but only projects can read them during build and runtime. (Default: `1`) |

## Usage

```typescript
import { Client, Project, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const project = new Project(client);
const result: Models.Variable = await project.createVariable({
  variableId: '<VARIABLE_ID>',
  key: '<KEY>',
  value: '<VALUE>',
  secret: false,
});
```

## Response Model

Returns a `Models.Variable` object with the following properties:

| Property | Type | Description |
|----------|------|-------------|
| `id` | `string` | Variable ID. |
| `createdAt` | `string` | Variable creation date in ISO 8601 format. |
| `updatedAt` | `string` | Variable creation date in ISO 8601 format. |
| `key` | `string` | Variable key. |
| `value` | `string` | Variable value. |
| `secret` | `boolean` | Variable secret flag. Secret variables can only be updated or deleted, but never read. |
| `resourceType` | `string` | Service to which the variable belongs. Possible values are &quot;project&quot;, &quot;function&quot; |
| `resourceId` | `string` | ID of resource to which the variable belongs. If resourceType is &quot;project&quot;, it is empty. If resourceType is &quot;function&quot;, it is ID of the function. |
