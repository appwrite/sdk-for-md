# updateVariable

Description: Update variable by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `functionId` | `string` | ✅ | Function unique ID. |
| `variableId` | `string` | ✅ | Variable unique ID. |
| `key` | `string` | ✅ | Variable key. Max length: 255 chars. |
| `value` | `string` | ❌ | Variable value. Max length: 8192 chars. |
| `secret` | `boolean` | ❌ | Secret variables can be updated or deleted, but only functions can read them during build and runtime. |

## Usage

```typescript
import { Client, Functions, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const functions = new Functions(client);
const result: Models.Variable = await functions.updateVariable({
  functionId: '<FUNCTION_ID>',
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
