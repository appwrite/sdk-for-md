# getVariable

Description: Get a variable by its unique ID.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site unique ID. |
| `variableId` | `string` | ✅ | Variable unique ID. |

## Usage

```typescript
import { Client, Sites, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.Variable = await sites.getVariable({
  siteId: '<SITE_ID>',
  variableId: '<VARIABLE_ID>',
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
