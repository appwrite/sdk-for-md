# createVariable

Description: Create a new site variable. These variables can be accessed during build and runtime (server-side rendering) as environment variables.

## Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `siteId` | `string` | ✅ | Site unique ID. |
| `key` | `string` | ✅ | Variable key. Max length: 255 chars. |
| `value` | `string` | ✅ | Variable value. Max length: 8192 chars. |
| `secret` | `boolean` | ❌ | Secret variables can be updated or deleted, but only sites can read them during build and runtime. (Default: `1`) |

## Usage

```typescript
import { Client, Sites, Models } from 'appwrite';

const client = new Client()
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1').setProject('<YOUR_PROJECT_ID>');

const sites = new Sites(client);
const result: Models.Variable = await sites.createVariable({
  siteId: '<SITE_ID>',
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
